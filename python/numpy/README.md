# NumPy (Numerical Python)

Foundations of numerical computing, multi-dimensional array operations, and vectorized math in Python.

---

## 📂 Contents

| File | Description |
| :--- | :--- |
| `numpy_prac.ipynb` | Comprehensive practice notebook exploring NumPy ndarray operations, slicing, broadcasting, and linear algebra |

---

## 🎯 Key Concepts Covered

1. **`ndarray` Creation & Shapes**:
   - `np.array()`, `np.zeros()`, `np.ones()`, `np.arange()`, `np.linspace()`
   - Multi-dimensional array reshaping (`reshape()`), flattening (`ravel()`, `flatten()`).
2. **Indexing & Slicing**:
   - 1D, 2D, and multi-axis slicing (`arr[row_start:row_end, col_start:col_end]`).
   - Boolean masking and conditional filtering (`arr[arr > 5]`).
3. **Broadcasting**:
   - Arithmetic operations on arrays of differing shapes according to broadcasting rules.
4. **Mathematical & Statistical Aggregations**:
   - `np.mean()`, `np.std()`, `np.median()`, `np.sum()`, `np.min()`, `np.max()`, and axis-wise operations (`axis=0`, `axis=1`).
5. **Linear Algebra**:
   - Matrix multiplication (`np.dot()`, `@` operator), transpose (`arr.T`), and vector norms.

---

## 🚀 Quick Reference

```python
import numpy as np

# 1. Array creation & shape inspection
a = np.array([[1, 2, 3], [4, 5, 6]])
print(a.shape)  # (2, 3)
print(a.dtype)  # int64

# 2. Vectorized operations (no slow Python loops!)
b = a * 2 + 10

# 3. Boolean filtering
evens = a[a % 2 == 0]

# 4. Axis-wise statistics
col_means = a.mean(axis=0)  # average of each column
```
