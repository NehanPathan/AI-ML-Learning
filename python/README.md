# Python Fundamentals for Data Science

Core Python libraries essential for machine learning and data analysis.

## 📂 Structure

```
python/
├── numpy/    # Numerical computing with arrays
└── pandas/   # Data manipulation and analysis
```

## 🎯 Learning Objectives

### NumPy
Master **N-dimensional arrays** and numerical operations:

- Array creation and indexing
- Mathematical operations
- Broadcasting (working with different shapes)
- Linear algebra basics
- Random number generation

**Why NumPy?**
- Foundation for pandas, scikit-learn, and most ML libraries
- Extremely fast (C implementation)
- Essential for understanding ML algorithms

### Pandas
Master **DataFrame operations** and data wrangling:

- Load data from CSV, JSON, Excel
- Explore data (head, info, describe, dtypes)
- Filtering and selecting data
- Handling missing values
- Grouping and aggregation
- Merging and concatenating datasets
- Creating pivot tables

**Why Pandas?**
- Standard for data exploration and cleaning
- Makes data manipulation intuitive
- Required for real-world ML projects

## 🚀 Quick Start

### NumPy Example
```python
import numpy as np

# Create arrays
arr = np.array([1, 2, 3, 4, 5])
matrix = np.array([[1, 2, 3], [4, 5, 6]])

# Operations
result = arr * 2  # [2, 4, 6, 8, 10]
mean_val = arr.mean()  # 3.0
sum_val = arr.sum()  # 15

# Useful functions
zeros = np.zeros((3, 3))  # 3x3 matrix of zeros
ones = np.ones((2, 4))   # 2x4 matrix of ones
random_arr = np.random.rand(5)  # 5 random values [0, 1)
```

### Pandas Example
```python
import pandas as pd

# Load data
df = pd.read_csv('data.csv')

# Explore
print(df.head())        # First 5 rows
print(df.info())        # Data types and nulls
print(df.describe())    # Statistical summary

# Select columns
df['column_name']
df[['col1', 'col2']]

# Filter rows
df[df['age'] > 25]
df[(df['age'] > 25) & (df['income'] > 50000)]

# Handle missing values
df.fillna(0)  # Fill with 0
df.dropna()   # Remove rows with nulls
df.isnull().sum()  # Count nulls

# Group and aggregate
df.groupby('category')['amount'].sum()

# Create new columns
df['new_col'] = df['col1'] + df['col2']
```

## 📚 Common Patterns

### Data Loading & Inspection
```python
import pandas as pd
import numpy as np

df = pd.read_csv('data.csv')
print(f"Shape: {df.shape}")
print(df.dtypes)
print(df.isnull().sum())
```

### Data Cleaning
```python
# Remove duplicates
df = df.drop_duplicates()

# Handle missing values
df['numeric_col'].fillna(df['numeric_col'].mean())
df['categorical_col'].fillna('Unknown')

# Convert data types
df['date_col'] = pd.to_datetime(df['date_col'])
df['category'] = df['category'].astype('category')
```

### Feature Engineering
```python
# Create new features
df['age_squared'] = df['age'] ** 2
df['log_income'] = np.log(df['income'])

# Categorical encoding
df_encoded = pd.get_dummies(df, columns=['category'])

# Scaling (use scikit-learn for ML)
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
df[['col1', 'col2']] = scaler.fit_transform(df[['col1', 'col2']])
```

### Data Aggregation
```python
# Group by and summarize
summary = df.groupby('category').agg({
    'amount': 'sum',
    'price': 'mean',
    'quantity': 'count'
})

# Pivot tables
pivot = df.pivot_table(
    values='sales',
    index='product',
    columns='region',
    aggfunc='sum'
)
```

## 🔗 Common Imports

```python
import numpy as np
import pandas as pd

# Commonly used numpy functions
from numpy import mean, std, sum, min, max
from numpy.random import rand, randn, choice

# Commonly used pandas features
from pandas import read_csv, read_json, DataFrame, Series
```

## 📊 NumPy vs Pandas vs Lists

| Task | List | NumPy | Pandas |
|------|------|-------|--------|
| Store numbers | ✓ | ✓✓ (fast) | ✓✓ |
| 2D data | Limited | ✓✓ | ✓✓ |
| Mathematical ops | Slow | ✓✓ (fast) | ✓ |
| Label columns | No | No | ✓✓ |
| Missing values | Complex | Manual | ✓✓ (built-in) |
| Read CSV | No | No | ✓✓ |

## 💡 Performance Tips

1. **Use vectorization**: Avoid Python loops with NumPy/Pandas
2. **Use `.values` or `.to_numpy()`**: When you need raw NumPy arrays
3. **Use `.loc[]` for labels**: More readable than integer indexing
4. **Use `.isin()` for filtering**: Faster than multiple OR conditions
5. **Use `copy()`**: When you don't want to modify original data

## 🎓 Progression

1. **Week 1**: NumPy arrays and basic operations
2. **Week 2**: NumPy advanced (broadcasting, slicing, linear algebra)
3. **Week 3**: Pandas DataFrames and loading data
4. **Week 4**: Data exploration and cleaning with Pandas
5. **Week 5**: Feature engineering with Pandas
6. **Week 6+**: Apply to real datasets from supervised_ml/

## 📚 Resources

- NumPy Documentation: https://numpy.org/doc/
- Pandas Documentation: https://pandas.pydata.org/docs/
- NumPy Tutorial: https://numpy.org/doc/stable/user/basics.html
- Pandas Tutorial: https://pandas.pydata.org/docs/user_guide/index.html

---

**Last updated**: 2026-06-14
