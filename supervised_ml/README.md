# Supervised Learning

Learning algorithms for problems where training data includes target labels.

## 📂 Structure

```
supervised_ml/
├── regression/          # Predict continuous values
├── classification/      # Predict discrete categories  
└── ensemble/           # Combine multiple models
```

## 🎯 Topics Covered

### Regression
**Concept**: Predict continuous numerical values (prices, temperatures, etc.)

**Algorithms**:
- Linear/Lasso Regression
- Support Vector Regression (SVR)

**Project**: House Price Prediction
- Estimate property prices using features
- Learn feature engineering and model evaluation

### Classification
**Concept**: Predict discrete categories (yes/no, spam/ham, species, etc.)

**Algorithms**:
- Logistic Regression
- K-Nearest Neighbors (KNN)
- Naive Bayes
- Support Vector Machines (SVM)
- Decision Trees

**Projects**:
1. **Iris Classification**: Classify flower species
2. **Employee Turnover Prediction**: Predict employee attrition
3. **Credit Risk Prediction**: Assess loan default risk
4. **E-commerce Analysis**: Customer classification

### Ensemble Methods
**Concept**: Combine multiple models for better predictions

**Algorithms**:
- AdaBoost (Adaptive Boosting)
- Gradient Boosting
- Random Forest
- XGBoost

## 🚀 Learning Order

1. Start with classification concepts (intuitive, visual)
2. Learn regression (similar pipeline, different target)
3. Master ensemble methods (combine what you've learned)

## 📊 Typical ML Pipeline

1. **Load & Explore**: `pd.read_csv()`, `df.info()`, `df.describe()`
2. **Clean Data**: Handle missing values, outliers, duplicates
3. **Feature Engineering**: Create/select meaningful features
4. **Split Data**: `train_test_split(test_size=0.2)`
5. **Scale Features**: `StandardScaler()` (important for distance-based algorithms)
6. **Train Model**: `model.fit(X_train, y_train)`
7. **Predict**: `y_pred = model.predict(X_test)`
8. **Evaluate**: 
   - Regression: R², MSE, RMSE
   - Classification: Accuracy, Precision, Recall, F1, Confusion Matrix

## 🔗 Common Imports

```python
# Data manipulation
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler

# Regression models
from sklearn.linear_model import LinearRegression, Lasso
from sklearn.svm import SVR

# Classification models
from sklearn.linear_model import LogisticRegression
from sklearn.neighbors import KNeighborsClassifier
from sklearn.naive_bayes import GaussianNB
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier

# Ensemble models
from sklearn.ensemble import AdaBoostClassifier, RandomForestClassifier, GradientBoostingClassifier
from xgboost import XGBClassifier

# Evaluation
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
from sklearn.metrics import r2_score, mean_squared_error
```

## 💡 Tips

- **Feature Scaling**: Many algorithms benefit from scaling (KNN, SVM, Logistic Regression)
- **Train/Test Split**: Always use separate test data for unbiased evaluation
- **Hyperparameter Tuning**: Use `GridSearchCV` for parameter optimization
- **Class Imbalance**: Use `class_weight='balanced'` when dealing with imbalanced datasets
- **Model Selection**: Compare models on the same train/test split

## 📚 Resources

- Scikit-learn documentation: https://scikit-learn.org/
- Pandas documentation: https://pandas.pydata.org/
- XGBoost documentation: https://xgboost.readthedocs.io/

---

**Last updated**: 2026-06-14
