# 🧠 Telco Customer Churn Prediction

A machine learning project to predict customer churn based on demographic and service usage data from a telecom company. The goal is to identify customers likely to leave, enabling proactive retention strategies.

---

## 📂 Project Structure

```
project/
│
├── data/               # Original and processed dataset(s)
├── images/             # Visualizations and plots
├── models/             # Saved trained model (joblib)
├── notebooks/
│   └── churn_prediction.ipynb
├── README.md           # You are here!
└── requirements.txt    # Python dependencies
```

---

## 📊 Dataset

**Source:** [IBM Sample Dataset - Telco Customer Churn](https://www.ibm.com/communities/analytics/watson-analytics-blog/guide-to-sample-datasets/)  
**Shape:** ~7,043 samples × 21 features  
**Target Variable:** `Churn` (Yes/No)

---

## 🔍 Features Used

- Demographics: `gender`, `SeniorCitizen`, `Partner`, `Dependents`
- Service usage: `PhoneService`, `InternetService`, `StreamingTV`, etc.
- Contract & payment: `Contract`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`
- **Engineered features** using one-hot encoding, normalization

---

## 🔧 Machine Learning Pipeline

1. **Data Preprocessing**
   - One-hot encoding
   - Null handling
   - Normalization of numeric values
2. **Class Imbalance Handling**
   - `class_weight='balanced'` for logistic regression
3. **Model Training**
   - Logistic Regression
   - XGBoost (with hyperparameter tuning using GridSearchCV)
4. **Evaluation Metrics**
   - Accuracy
   - F1-Score
   - Recall
   - ROC-AUC
   - Confusion Matrix
5. **Model Saving**
   - `joblib.dump()` for deployment-ready storage

---

## 📈 Results

| Model                  | Accuracy | Recall | F1-Score | ROC AUC |
|------------------------|----------|--------|----------|---------|
| Logistic Regression    | 0.7477   | 0.7486 | 0.6120   | 0.8339  |
| XGBoost (tuned)        | 0.7910   | 0.5310 | 0.5800   | 0.8400  |

➡️ **Final model selected:** `XGBoost` (based on AUC score)

---

## 🚀 Getting Started

### 1. Clone this repository

```bash
git clone https://github.com/yunusarslans/telco-churn-prediction.git
cd telco-churn-prediction
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run Jupyter Notebook

```bash
jupyter notebook notebooks/churn_prediction.ipynb
```

---

## 💡 Future Improvements

- Deploy model as a REST API (e.g., Flask or FastAPI)
- Add SHAP interpretability for model explainability
- Integrate real-time prediction from user input
- Monitor model drift and update periodically

---

## 👨‍💻 Author

**GitHub:** [@yunusarslans](https://github.com/yunusarslans)

---

## 📜 License

This project is open-source and available under the MIT License.
