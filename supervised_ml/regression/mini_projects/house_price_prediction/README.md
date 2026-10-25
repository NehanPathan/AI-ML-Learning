# House Price Prediction

Predicting real estate sales prices using property specifications, physical dimensions, location features, and condition ratings.

---

## 📂 Project Files

| File | Description |
| :--- | :--- |
| `house_price_predictor.ipynb` | End-to-end regression pipeline: missing value imputation, log transforms, categorical encoding, regression modeling, and residual analysis |
| `HousePricePrediction.csv` | Real estate tabular dataset containing square footage, bedrooms, bathrooms, year built, garage capacity, and sale prices |

---

## 🎯 Key Project Steps

1. **Target Distribution Analysis**:
   - Examining right-skewness of home prices and applying logarithmic transformations: `np.log1p(df['SalePrice'])`.
2. **Handling Multicollinearity**:
   - Inspecting correlation heatmaps (e.g. square footage vs number of rooms, garage area vs car capacity).
3. **Encoding Categoricals**:
   - Converting nominal features via One-Hot Encoding and ordinal quality scores to numeric ranks.
4. **Evaluation**:
   - Comparing baseline Linear Regression vs Lasso vs Ridge using Root Mean Squared Error (RMSE) on validation splits.
