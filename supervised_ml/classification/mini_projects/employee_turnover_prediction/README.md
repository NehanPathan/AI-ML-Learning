# Employee Turnover & Attrition Prediction

An HR analytics project predicting employee attrition and identifying retention drivers using **Logistic Regression** and machine learning classifiers.

---

## 📂 Project Files

| File | Description |
| :--- | :--- |
| `employee_turnover_project.ipynb` | Comprehensive turnover analysis, feature engineering, model training, and feature importance interpretation |
| `employee_stay_logistic_prediction.ipynb` | Dedicated logistic regression notebook focused on probability estimation and odds ratios |
| `employee_turnover.csv` | Primary dataset containing satisfaction levels, evaluation scores, average monthly hours, tenure, and turnover status |
| `employee_data.csv` / `employee_data.json` | Auxiliary employee records formatted in CSV and JSON |

---

## 🎯 Key HR Insights & Analysis

1. **Top Turnover Drivers**:
   - Job satisfaction level is typically the strongest negative predictor of departure.
   - Overworking (excessive monthly working hours) combined with low promotion rates leads to elevated burnout and flight risk.
   - Years at company: Medium-tenure employees (3-5 years) often experience peak attrition if career progression stalls.
2. **Modeling Techniques**:
   - Class imbalance adjustment (using `class_weight='balanced'` in Logistic Regression).
   - Precision-Recall curves to assess trade-offs between retaining critical talent vs. unnecessary retention interventions.
