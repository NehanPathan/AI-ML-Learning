# Matplotlib & Statistical Plotting

Hands-on plotting practice using **Matplotlib** (`matplotlib.pyplot`) and figure customizations.

---

## 📂 Contents

| File | Description |
| :--- | :--- |
| `Prac.ipynb` | Practice notebook exploring line charts, scatter plots, subplots, histograms, and figure styling |

---

## 🚀 Quick Plotting Template

```python
import matplotlib.pyplot as plt
import numpy as np

# Sample data
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Create figure & axis
fig, ax = plt.subplots(figsize=(8, 4), dpi=100)

ax.plot(x, y, label="$\sin(x)$", color="#2563eb", linewidth=2)
ax.set_title("Sine Wave Progression", fontsize=14, fontweight="bold")
ax.set_xlabel("Time (s)")
ax.set_ylabel("Amplitude")
ax.grid(True, linestyle="--", alpha=0.6)
ax.legend()

plt.tight_layout()
plt.show()
```
