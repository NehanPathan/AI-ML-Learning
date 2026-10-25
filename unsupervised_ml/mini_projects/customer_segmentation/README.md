# Customer Segmentation (SmartCart)

Unsupervised clustering of retail customers into distinct persona segments based on annual income, spending scores, and purchasing habits.

---

## 📂 Project Files

| File | Description |
| :--- | :--- |
| `smartcart.ipynb` | Complete customer segmentation notebook: EDA, feature scaling, Elbow method, Silhouette score evaluation, and 2D/3D cluster profiling |
| `smartcart_customers.csv` | Customer demographics and behavioral dataset (Customer ID, Gender, Age, Annual Income, Spending Score) |

---

## 🎯 Segmentation Workflow

1. **Exploratory Data Analysis**:
   - Distribution of customer age, annual income, and spending scores.
2. **Optimal Cluster Selection ($K$)**:
   - **Elbow Method**: Plotting Within-Cluster-Sum-of-Squares (WCSS / Inertia) vs $K$.
   - **Silhouette Analysis**: Measuring how well-separated individual clusters are.
3. **Cluster Persona Profiling**:
   - **High Income, High Spending**: Target with luxury promotions and loyalty programs.
   - **High Income, Low Spending**: Target with value campaigns to incentivize purchase frequency.
   - **Low Income, High Spending**: Impulse buyers, sensitive to discount coupons.
   - **Low Income, Low Spending**: Frugal / budget-conscious shoppers.
4. **Cluster Visualization**:
   - Color-coded scatter plots with centroid coordinates labeled.
