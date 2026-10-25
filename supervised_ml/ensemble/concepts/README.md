# Ensemble Methods: Concepts & Implementations

Hands-on notebooks detailing bagging, boosting, and heterogeneous ensemble architectures.

---

## 📂 Notebooks in this Directory

| Notebook | Ensemble Family | Algorithm Details |
| :--- | :--- | :--- |
| `random_forest.ipynb` | Bagging | Random Forest Classifier & Regressor, out-of-bag (OOB) score, feature importance ranking, `n_estimators`, `max_features` |
| `adaboost.ipynb` | Boosting | Adaptive Boosting with decision stumps, dynamic sample weight updates $\alpha_m$, exponential loss minimization |
| `gradient_boosting.ipynb`| Gradient Boosting | Sequential gradient descent in functional space, residual fitting, learning rate shrinkage |
| `xgboost.ipynb` | Scaled Gradient Boosting | Extreme Gradient Boosting regression, second-order Taylor approximations, tree regularization |
| `xgboost_classification.ipynb` | Scaled Gradient Boosting | XGBoost classification, handling missing values, early stopping, scale_pos_weight |
| `ensemble_heterogenous.ipynb` | Stacking / Blending | VotingClassifier, StackingClassifier, combining diverse estimators with a logistic meta-learner |

---

## 🚀 Key Imports & Cheat Sheet

```python
from sklearn.ensemble import (
    RandomForestClassifier,
    AdaBoostClassifier,
    GradientBoostingClassifier,
    VotingClassifier,
    StackingClassifier
)
from xgboost import XGBClassifier, XGBRegressor

# Random Forest example
rf = RandomForestClassifier(
    n_estimators=100,
    max_depth=10,
    max_features="sqrt",
    oob_score=True,
    random_state=42
)

# XGBoost example
xgb = XGBClassifier(
    n_estimators=200,
    learning_rate=0.05,
    max_depth=4,
    subsample=0.8,
    colsample_bytree=0.8,
    eval_metric="logloss"
)
```
