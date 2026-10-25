# Regression Concepts & Implementations

In-depth notebooks exploring regularized linear models and non-linear kernel regression.

---

## 📂 Notebooks in this Directory

| Notebook | Algorithm | Focus Area |
| :--- | :--- | :--- |
| `1-lasso_regression.ipynb` | **Lasso Regression ($L_1$ Regularization)** | Cost function penalty $\lambda \sum |w_j|$, driving irrelevant feature coefficients strictly to 0 (feature selection) |
| `svr_implementation.ipynb` | **Support Vector Regression (SVR)** | $\epsilon$-tube margin of tolerance, slack variables $\xi_i$, RBF kernel, $C$ and $\gamma$ tuning |

---

## 🚀 Key Mathematical Insights

### 1. Lasso Regularization ($L_1$)
$$\min_{\mathbf{w}} \frac{1}{2m} \|X\mathbf{w} - \mathbf{y}\|_2^2 + \alpha \|\mathbf{w}\|_1$$
Unlike Ridge ($L_2$), Lasso forces coefficients of collinear or redundant features to zero, yielding sparse, interpretable models.

### 2. Support Vector Regression (SVR)
SVR solves for a function where predictions lie within an $\epsilon$-insensitive tube around actual values. Points outside the tube incur a linear penalty governed by parameter $C$.

```python
from sklearn.linear_model import Lasso, Ridge, ElasticNet
from sklearn.svm import SVR
from sklearn.preprocessing import StandardScaler
from sklearn.pipeline import make_pipeline

# Pipelines guarantee proper scaling for SVR and Lasso
lasso_pipe = make_pipeline(StandardScaler(), Lasso(alpha=0.1))
svr_pipe = make_pipeline(StandardScaler(), SVR(kernel="rbf", C=100, epsilon=0.1))
```
