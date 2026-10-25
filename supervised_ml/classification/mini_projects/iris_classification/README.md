# Iris Flower Species Classification

The seminal machine learning benchmark: classifying Iris flowers into three distinct species (*Iris setosa*, *Iris versicolor*, *Iris virginica*) based on morphological petal and sepal measurements.

---

## 📂 Project Files

| File | Description |
| :--- | :--- |
| `iris_flower.ipynb` | Complete classification pipeline: pairplots, KNN, Decision Tree, Confusion Matrix, and decision surface plotting |
| `IRIS.csv` | Dataset with 150 instances, 4 numeric features (`sepal_length`, `sepal_width`, `petal_length`, `petal_width`), and target `species` |

---

## 🌸 Key Takeaways

1. **Linear Separability**:
   - *Iris setosa* is linearly separable from the other two species purely by `petal_length`.
   - *Iris versicolor* and *Iris virginica* have slight boundary overlaps requiring multivariate classifiers.
2. **Algorithm Comparison**:
   - Compares **KNN** ($K=3, 5$) vs **Decision Trees** vs **Logistic Regression**.
   - Demonstrates multi-class classification metrics (Macro vs Weighted F1 score).
