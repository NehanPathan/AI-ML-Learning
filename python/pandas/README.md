# Pandas (Data Analysis & Manipulation)

Mastering tabular data structures (**Series** and **DataFrames**), exploratory data analysis (EDA), and data cleaning with Python.

---

## 📂 Contents

| File | Description |
| :--- | :--- |
| `pandas_prac.ipynb` | Comprehensive practice notebook covering DataFrame operations, handling missing data, grouping, merging, and transformations |

---

## 🎯 Key Concepts Covered

1. **DataFrame & Series Operations**:
   - Loading data from CSV, JSON, and dictionaries (`pd.read_csv()`, `pd.DataFrame()`).
   - Structural inspection: `.head()`, `.tail()`, `.info()`, `.describe()`, `.shape`, `.dtypes`.
2. **Selection & Slicing**:
   - Label-based indexing (`.loc[]`) vs integer-based indexing (`.iloc[]`).
   - Multi-condition row filtering (`df[(df['age'] > 30) & (df['income'] >= 50000)]`).
3. **Data Cleaning & Handling Nulls**:
   - Detecting nulls: `.isna()`, `.isnull().sum()`.
   - Imputing values: `.fillna(value)` (mean, median, mode).
   - Removing rows/columns: `.dropna()`, `.drop(columns=[...])`.
   - Deduplication: `.drop_duplicates()`.
4. **Transformations & Feature Engineering**:
   - Applying custom functions: `.apply()`, `.map()`.
   - String operations (`df['name'].str.lower()`).
   - Date/time conversion (`pd.to_datetime()`).
5. **Grouping & Aggregation**:
   - Split-Apply-Combine with `.groupby()`.
   - Aggregating metrics across categories: `df.groupby('dept')['salary'].agg(['mean', 'max', 'count'])`.
   - Pivot tables and cross-tabulations (`df.pivot_table()`, `pd.crosstab()`).

---

## 🚀 Quick Reference

```python
import pandas as pd

# Load & inspect
df = pd.read_csv("dataset.csv")
print(df.info())

# Filter & clean
clean_df = df.dropna(subset=['target_col'])
clean_df['num_col'] = clean_df['num_col'].fillna(clean_df['num_col'].median())

# Group & aggregate
summary = clean_df.groupby("category").agg({
    "price": "mean",
    "quantity": "sum"
}).reset_index()
```
