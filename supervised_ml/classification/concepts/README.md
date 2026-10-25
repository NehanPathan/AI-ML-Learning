# Classification Concepts & Algorithms

Notebooks demonstrating individual classification algorithms from theoretical intuition to Scikit-Learn implementation.

---

## 📂 Notebooks in this Directory

| Notebook | Focus Algorithm / Topic | Key Concepts |
| :--- | :--- | :--- |
| `1-logistic_regression.ipynb` | Logistic Regression | Sigmoid activation, log-loss, decision boundaries, multi-class One-vs-Rest (OvR) |
| `knn.ipynb` | K-Nearest Neighbors (KNN) | Euclidean & Manhattan distances, choice of $K$, curse of dimensionality |
| `naive_bayes.ipynb` | Naive Bayes Classifier | Prior, likelihood, posterior probabilities, GaussianNB, conditional independence assumption |
| `svc_implementation.ipynb` | Support Vector Classifier (SVC) | Margin maximization, support vectors, RBF / Linear / Polynomial kernels, $C$ and $\gamma$ hyperparameters |
| `tree.ipynb` | Decision Tree Classifier | Information Gain, Entropy, Gini Impurity, tree pruning (`max_depth`, `min_samples_split`) |
| `regre_naive_knn.ipynb` | Comparative Study | Comparing regression vs Naive Bayes vs KNN across synthetic datasets |
| `supervised_learning.ipynb` | Overview & Foundations | Supervised learning paradigms, train/test splits, cross-validation, baseline metrics |

---

## 🚀 Scikit-Learn Import Guide

```python
# Models
from sklearn.linear_model import LogisticRegression
from sklearn.neighbors import KNeighborsClassifier
from sklearn.naive_bayes import GaussianNB
from sklearn.svm import SVC
from sklearn.tree import DecisionTreeClassifier

# Preprocessing & Selection
from sklearn.model_selection import train_test_split, GridSearchCV, StratifiedKFold
from sklearn.preprocessing import StandardScaler

# Metrics
from sklearn.metrics import (
    accuracy_score, precision_score, recall_score, f1_score,
    confusion_matrix, classification_report, roc_auc_score
)
```

---

## 💡 Practical Takeaways

- **Scale Before Distance-Based Models**: Always apply `StandardScaler` to features when training **KNN**, **SVC**, or **Logistic Regression**. Decision Trees do not require scaling.
- **Tuning $K$ in KNN**: Always use cross-validation to select odd values of $K$ (to prevent tiebreaks in binary classification).
- **Tree Overfitting**: Without pruning (`max_depth`, `min_samples_leaf`), decision trees will memorize noise and severely overfit.
