# Unsupervised Learning Concepts & Algorithms

Notebooks implementing clustering algorithms, dimensionality reduction, and anomaly detection without labeled targets.

---

## 📂 Notebooks in this Directory

| Notebook | Topic / Algorithm | Description |
| :--- | :--- | :--- |
| `KMeans.ipynb` | **K-Means Clustering** | Centroid initialization, Voronoi partitions, Elbow method (Inertia WCSS), Silhouette analysis |
| `KMeansForIris.ipynb` | **K-Means on Iris Dataset** | Unsupervised clustering on benchmark Iris data comparing discovered clusters with true ground-truth species |
| `KMeansPrac.ipynb` | **K-Means Practice** | Scaling impacts, spherical vs elongated cluster limitations |
| `hierarchical_clustering.ipynb`| **Hierarchical Clustering** | Agglomerative clustering, linkage criteria (Ward, Complete, Average), Dendrogram visualization via Scipy |
| `DBSCAN.ipynb` | **DBSCAN** | Density-Based Spatial Clustering of Applications with Noise: $\epsilon$ neighborhood, `min_samples`, Core/Border/Noise points |
| `clustering_DBSCAN.ipynb` | **DBSCAN Deep Dive** | Non-spherical cluster discovery (concentric rings, moons) where K-Means fails |
| `PCA.ipynb` | **Principal Component Analysis** | Dimensionality reduction, covariance matrix, eigenvectors, explained variance ratio, 2D/3D projection |
| `isolation_forest.ipynb` | **Isolation Forest** | Unsupervised anomaly detection, path length in random trees, identifying outliers |
| `thyroid_dataset.csv` | Dataset | Tabular dataset used for anomaly detection and multivariate clustering |

---

## 🚀 Key Scikit-Learn Imports

```python
# Clustering
from sklearn.cluster import KMeans, DBSCAN, AgglomerativeClustering
from scipy.cluster.hierarchy import dendrogram, linkage

# Dimensionality Reduction
from sklearn.decomposition import PCA

# Anomaly Detection
from sklearn.ensemble import IsolationForest

# Evaluation Metrics (No ground truth required)
from sklearn.metrics import silhouette_score, davies_bouldin_score
```

---

## 💡 Practical Decision Guide

- **K-Means**: Fast ($O(n)$), but assumes spherical, equally-sized clusters. Always scale features first!
- **DBSCAN**: Does not require specifying cluster count $K$; isolates noise/outliers naturally; handles arbitrary cluster geometries.
- **PCA**: Crucial for high-dimensional feature visualization (e.g., projecting 50 features down to 2 components for Matplotlib plotting).
