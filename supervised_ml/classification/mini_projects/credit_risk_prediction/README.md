# Credit Risk Prediction (CreditWise)

A financial risk assessment model that evaluates borrower characteristics and predicts loan approval / credit default risk.

---

## 📂 Project Files

| File | Description |
| :--- | :--- |
| `credit_wise.ipynb` | Comprehensive notebook: EDA, missing value handling, categorical encoding, model training, and threshold tuning |
| `loan_approval_data.csv` | Dataset of loan applicants with income, credit scores, debt obligations, and approval status |

---

## 🎯 Objective & Workflow

In credit underwriting, lending institutions must minimize **False Positives** (granting loans to borrowers likely to default) while maintaining fair access to credit.

### Pipeline Stages:
1. **Exploratory Data Analysis**:
   - Distribution of credit scores, loan amounts, debt-to-income (DTI) ratios.
   - Identifying outliers and skewed financial features.
2. **Preprocessing**:
   - Imputation of missing financial metrics.
   - One-hot encoding of categorical features (employment status, loan purpose, property ownership).
   - `StandardScaler` applied to continuous variables.
3. **Model Training & Comparison**:
   - Logistic Regression as an interpretable baseline.
   - Tree-based classifiers for non-linear credit boundaries.
4. **Evaluation**:
   - Precision, Recall, ROC-AUC score, and confusion matrix analysis.
