# Datasets

Centralized repository for all datasets used in learning materials.

## 📂 Structure

```
datasets/
├── raw/              # Original, unprocessed data from various sources
├── processed/        # Cleaned and prepared datasets ready for analysis
└── external/         # Third-party or external source datasets
```

## 📋 Dataset Guide

### raw/ - Raw Datasets

| Dataset | Source | Use Case |
|---------|--------|----------|
| `insurance.csv` | Sample data | Regression, exploratory analysis |
| `1-heart.csv` | Health data | Classification, feature analysis |
| `globalAirQuality.csv` | Environmental data | Time series, anomaly detection |
| `raw_data.csv` | Demo data | Data cleaning practice |
| `sorted_data.csv` | Demo data | Sorting and transformation |
| `store_data-Copy1.json` | E-commerce | JSON parsing, data wrangling |

### processed/ - Processed Datasets

| Dataset | Source | Description |
|---------|--------|-------------|
| `data.csv` | Cleaned version of raw_data | Ready for ML applications |

### external/ - External/Third-Party Datasets

Location for datasets downloaded from external sources.

## 🔗 Dataset Usage

### In Supervised ML Projects
Datasets are typically **local to each project folder**:

```
supervised_ml/classification/mini_projects/iris_classification/
├── iris_flower.ipynb
└── IRIS.csv                    # Project-specific data
```

Load with:
```python
import pandas as pd
from pathlib import Path

data_path = Path(__file__).parent / "IRIS.csv"
df = pd.read_csv(data_path)
```

### In Concept Notebooks
Reference generic datasets from this folder:

```python
from pathlib import Path

# From concepts folder, go up to datasets
data_path = Path(__file__).parent.parent.parent.parent / "datasets" / "raw" / "insurance.csv"
df = pd.read_csv(data_path)
```

## 📊 Adding New Datasets

1. **Raw data**: Place in `raw/` with original filename
2. **Processed data**: Clean first, then place in `processed/`
3. **External data**: Download to `external/` with source documentation
4. **Project-specific**: Keep with the project notebook (don't add to central datasets)

## 🧹 Data Cleaning Checklist

When preparing raw data for analysis:

- [ ] Load data and check shape (`df.shape`)
- [ ] View first/last rows (`df.head()`, `df.tail()`)
- [ ] Check data types (`df.dtypes`)
- [ ] Identify missing values (`df.isnull().sum()`)
- [ ] Check for duplicates (`df.duplicated().sum()`)
- [ ] Handle outliers (visualize distributions)
- [ ] Encode categorical variables
- [ ] Scale numerical features (if needed)
- [ ] Document transformations applied
- [ ] Save cleaned data to `processed/` folder

## 💡 Best Practices

1. **Don't modify raw data**: Always keep originals in `raw/`
2. **Document sources**: Note where each dataset came from
3. **Version control**: Track major changes to datasets
4. **Separate concerns**: Project datasets stay with projects
5. **Use relative paths**: Makes notebooks portable across machines

## 🔄 File Format Notes

### CSV Files
- Standard tabular format
- Load with: `pd.read_csv(filename)`
- Save with: `df.to_csv(filename, index=False)`

### JSON Files
- Structured, hierarchical data
- Load with: `pd.read_json(filename)` or `json.load(open(filename))`
- Save with: `df.to_json(filename)` or `json.dump(data, open(filename, 'w'))`

### Parquet Files (Optional)
- Efficient columnar format
- Faster than CSV for large datasets
- Load with: `pd.read_parquet(filename)`
- Save with: `df.to_parquet(filename)`

---

**Last updated**: 2026-06-14
