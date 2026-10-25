# Regression in Supervised Machine Learning

Predicting continuous numerical target values (e.g., prices, temperature, demand, sales) using linear, regularized, and support vector regression models.

---

## 📂 Subdirectories

| Folder | Contents | Description |
| :--- | :--- | :--- |
| [`concepts/`](concepts/README.md) | Notebooks covering core regression algorithms | Lasso ($L_1$) Regularization, Support Vector Regression (SVR) with Kernels |
| [`mini_projects/`](mini_projects/README.md) | Practical real-world regression applications | House Price Prediction pipeline |

---

## 🎯 Regression Fundamentals

- **Linear Hypothesis**:
  $$\hat{y} = w_1 x_1 + w_2 x_2 + \dots + w_n x_n + b = \mathbf{w}^T \mathbf{x} + b$$
- **Residual Sum of Squares (RSS)**:
  $$\text{RSS} = \sum_{i=1}^m (y^{(i)} - \hat{y}^{(i)})^2$$

### Evaluation Metrics

1. **Mean Absolute Error (MAE)**:
   $$\text{MAE} = \frac{1}{m} \sum_{i=1}^m |y^{(i)} - \hat{y}^{(i)}|$$
2. **Mean Squared Error (MSE)** & **Root Mean Squared Error (RMSE)**:
   $$\text{RMSE} = \sqrt{\frac{1}{m} \sum_{i=1}^m (y^{(i)} - \hat{y}^{(i)})^2}$$
3. **Coefficient of Determination ($R^2$ Score)**:
   $$R^2 = 1 - \frac{\sum (y_i - \hat{y}_i)^2}{\sum (y_i - \bar{y})^2}$$
