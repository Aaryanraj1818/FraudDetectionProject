
# 🛡️ Fraud Detection System

This project is an end-to-end **fraud detection system** built using machine learning to analyze financial transactions and identify fraudulent behavior. Designed as part of a business case challenge, the system handles over 6.3 million records and demonstrates how predictive modeling can assist in reducing financial fraud.

---
## Dataset= https://www.kaggle.com/datasets/amanalisiddiqui/fraud-detection-dataset?resource=download

## 📊 Project Overview

- **Dataset**: `Fraud.csv` — 6,362,620 transactions, 10 features
- **Model**: Logistic Regression (interpretable, scalable)
- **Frameworks**: Python, Scikit-learn, Pandas, Seaborn
- **Extras**: Streamlit web app for real-time prediction
- **Evaluation**: Accuracy (94%), ROC AUC (0.99), PR AUC (0.55)

---

## 🧠 Methodology

### 1. 📦 Data Cleaning & Feature Engineering
- Removed identifiers (`nameOrig`, `nameDest`)
- No missing values, verified with `isnull().sum()`
- Created two engineered features:
  - `balanceDiffOrig = oldbalanceOrg - newbalanceOrig`
  - `balanceDiffDest = newbalanceDest - oldbalanceDest`

### 2. 📈 Exploratory Data Analysis (EDA)
- Pie chart for fraud distribution
- Bar charts for transaction types
- Box plots to visualize amount anomalies
- Correlation heatmap
- Investigation of zero-balance fraud patterns

### 3. 🏗️ Model Building
- Preprocessing:
  - `StandardScaler` for numeric features
  - `OneHotEncoder` for transaction type
- Stratified train-test split (70:30)
- Logistic Regression with `class_weight='balanced'` to address class imbalance
- Evaluation:
  - Confusion Matrix
  - Precision, Recall, F1-score
  - ROC-AUC and Precision-Recall curves
  - Feature importance via model coefficients

---

## 🔍 Evaluation Results

| Metric              | Value       |
|---------------------|-------------|
| Accuracy            | 94%         |
| ROC AUC             | 0.99        |
| PR Curve AUC        | 0.55        |
| Top Fraud Types     | TRANSFER, CASH_OUT |
| Key Fraud Indicators | Zeroing balance, large transactions |

---

## 🌐 Streamlit Web App

A lightweight frontend built using Streamlit lets you test the model on new data.

### ▶️ Run It Locally

```bash
pip install streamlit pandas scikit-learn joblib
streamlit run fraud_detection.py
```

---

## 📁 Repository Contents

| File                          | Description                               |
|-------------------------------|-------------------------------------------|
| `Fraud Detection Case.ipynb`  | Full notebook with EDA, modeling, insights |
| `fraud_detection.py`          | Streamlit app for interactive prediction   |
| `Fraud_detection_pipeline.pkl`| Trained model with pipeline                |
| `Fraud.csv`                   | Dataset of over 6 million transactions     |
| `README.md`                   | This project summary and instructions      |

---

## 💡 Business Impact

- Identifies key fraud patterns based on balance behavior and transaction types.
- Enables proactive fraud detection with over 90% accuracy.
- Interpretable model supports transparent audits and business rule refinement.

---

## 🙋‍♂️ Contact

For questions, suggestions or collaboration:
**Email**: [aaryanraj1818@gmail.com]

---

