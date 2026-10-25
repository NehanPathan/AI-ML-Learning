# Unsupervised Learning

Learning algorithms for problems without labeled target data. Discover patterns, structures, and groupings in data.

## 📂 Structure

```
unsupervised_ml/
├── concepts/          # Clustering, Dimensionality Reduction techniques
└── mini_projects/     # Real-world applications
```

## 🎯 Topics Covered

### Clustering
**Goal**: Group similar data points into clusters without predefined labels

**Algorithms**:
- **KMeans**: Partition data into K clusters
  - Fast, effective for spherical clusters
  - Requires knowing K beforehand
  
- **Hierarchical Clustering**: Build a tree of nested clusters
  - Agglomerative (bottom-up) or Divisive (top-down)
  - Creates dendrograms showing relationships
  
- **DBSCAN**: Density-Based Spatial Clustering
  - Finds clusters of arbitrary shape
  - Identifies outliers automatically
  
- **Isolation Forest**: Anomaly detection
  - Identifies unusual/outlier points

### Dimensionality Reduction
**Goal**: Reduce number of features while preserving information

**Algorithms**:
- **PCA (Principal Component Analysis)**
  - Find directions of maximum variance
  - Useful for visualization and preprocessing
  - Reduces computational complexity

## 📊 Use Cases

### When to Use Clustering
- Customer Segmentation: Group customers by behavior
- Document Clustering: Organize similar documents
- Image Segmentation: Separate image regions
- Gene Sequencing: Group similar genetic profiles
- Social Networks: Find communities

### When to Use Dimensionality Reduction
- Visualization: Plot high-dimensional data in 2D/3D
- Feature Engineering: Create new synthetic features
- Noise Reduction: Remove less important dimensions
- Preprocessing: Speed up downstream algorithms

## 🚀 Learning Order

1. **KMeans** (simplest, most intuitive)
2. **Hierarchical Clustering** (understand relationships)
3. **DBSCAN** (handle irregular shapes)
4. **PCA** (reduce dimensions)
5. **Isolation Forest** (outlier detection)

## 📊 Typical Workflow

### Clustering
```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

# 1. Load and scale data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# 2. Train model (example: KMeans with K=3)
kmeans = KMeans(n_clusters=3, random_state=42)
clusters = kmeans.fit_predict(X_scaled)

# 3. Evaluate
from sklearn.metrics import silhouette_score
score = silhouette_score(X_scaled, clusters)  # -1 to 1 (higher is better)

# 4. Visualize
plt.scatter(X[:, 0], X[:, 1], c=clusters, cmap='viridis')
plt.scatter(kmeans.cluster_centers_[:, 0], 
            kmeans.cluster_centers_[:, 1], 
            marker='X', s=200, c='red')
plt.show()
```

### Dimensionality Reduction
```python
from sklearn.decomposition import PCA

# 1. Apply PCA
pca = PCA(n_components=2)
X_reduced = pca.fit_transform(X_scaled)

# 2. Explained variance
print(f"Variance explained: {pca.explained_variance_ratio_}")

# 3. Visualize
plt.scatter(X_reduced[:, 0], X_reduced[:, 1], c=y, cmap='viridis')
plt.xlabel(f'PC1 ({pca.explained_variance_ratio_[0]:.2%})')
plt.ylabel(f'PC2 ({pca.explained_variance_ratio_[1]:.2%})')
plt.show()
```

## 🔗 Common Imports

```python
# Clustering
from sklearn.cluster import KMeans, DBSCAN, AgglomerativeClustering
from sklearn.ensemble import IsolationForest

# Dimensionality Reduction
from sklearn.decomposition import PCA

# Evaluation
from sklearn.metrics import silhouette_score, davies_bouldin_score

# Preprocessing
from sklearn.preprocessing import StandardScaler
from scipy.cluster.hierarchy import dendrogram, linkage

# Visualization
import matplotlib.pyplot as plt
import seaborn as sns
```

## 💡 Key Concepts

### Silhouette Score
- Measures how similar a point is to its own cluster vs other clusters
- Range: -1 to 1 (higher is better)
- Above 0.5: Well-separated clusters
- Below 0.3: Overlapping clusters

### Elbow Method (for KMeans)
- Plot inertia vs number of clusters
- Look for the "elbow" bend in the curve
- The elbow indicates optimal K

### Feature Scaling
- **Always scale** before clustering (except tree-based)
- Different scales can bias distance calculations
- Use `StandardScaler` or `MinMaxScaler`

### Choosing Between Algorithms
- **KMeans**: Fast, for well-separated spherical clusters
- **Hierarchical**: See cluster hierarchy, works with any distance metric
- **DBSCAN**: Arbitrary shapes, automatic outlier detection
- **PCA**: Primarily for visualization and dimensionality reduction

## 📚 Resources

- Scikit-learn Clustering: https://scikit-learn.org/stable/modules/clustering.html
- Scikit-learn Decomposition: https://scikit-learn.org/stable/modules/decomposition.html
- Elbow Method Explanation: https://en.wikipedia.org/wiki/Elbow_method_(clustering)

---

**Last updated**: 2026-06-14
