# Artificial Neural Networks (ANN / MLP)

Implementation of Multi-Layer Perceptrons (MLPs) using **PyTorch** for both regression and multi-class classification tasks.

---

## 📂 Directory Contents

| File | Description | Target / Task |
| :--- | :--- | :--- |
| `ANN_Regression.ipynb` | Feedforward Neural Network for continuous prediction on Combined Cycle Power Plant data | Predict Net Hourly Electrical Energy Output (`PE`) |
| `ANN_Classification.ipynb` | Deep Neural Network for multi-class classification on Date Fruit varieties | Classify 7 distinct date fruit varieties |
| `powerplant_data.csv` | Dataset for regression (Ambient Temperature, Pressure, Relative Humidity, Exhaust Vacuum) | Regression dataset |
| `DateFruit_Dataset.csv` | Dataset containing extracted morphological and texture features of date fruits | Classification dataset |
| `best_model.pt` | Saved PyTorch model weights checkpoint with the best validation performance | Model checkpoint |
| `prac.ipynb` | Scratchpad for layer experimentation and testing custom activations | Experimentation |

---

## 🔬 Projects Overview

### 1. Power Plant Energy Output (ANN Regression)
- **Objective**: Predict the net hourly electrical energy output (`PE`) of a combined cycle power plant based on thermodynamic variables.
- **Features**:
  - `AT`: Ambient Temperature
  - `V`: Exhaust Vacuum
  - `AP`: Ambient Pressure
  - `RH`: Relative Humidity
- **Architecture**:
  - Input Layer: 4 features
  - Hidden Layers: Fully connected (`nn.Linear`) with `nn.ReLU` activations and optional Dropout for regularization
  - Output Layer: 1 linear unit (continuous output)
- **Loss Function**: Mean Squared Error (`nn.MSELoss`)
- **Optimizer**: Adam optimizer with learning rate scheduling
- **Evaluation**: RMSE, MAE, and $R^2$ Score

### 2. Date Fruit Variety Classification (ANN Classification)
- **Objective**: Accurately categorize date fruits into 7 different varieties using external features (morphological and color metrics).
- **Architecture**:
  - Multi-layer dense feedforward network
  - Normalization: `StandardScaler` fitted on training split
  - Activation: `nn.ReLU` or `nn.LeakyReLU`
  - Output Layer: 7 logits mapped via `nn.CrossEntropyLoss` (combines LogSoftmax and NLLLoss)
- **Optimizer**: Adam with weight decay
- **Evaluation**: Accuracy, Confusion Matrix, Precision/Recall, and Classification Report

---

## 🛠️ Typical PyTorch MLP Pipeline

```python
import torch
import torch.nn as nn
from torch.utils.data import Dataset, DataLoader

# Custom PyTorch Dataset
class TabularDataset(Dataset):
    def __init__(self, X, y):
        self.X = torch.tensor(X, dtype=torch.float32)
        self.y = torch.tensor(y, dtype=torch.float32)
        
    def __len__(self):
        return len(self.X)
        
    def __getitem__(self, idx):
        return self.X[idx], self.y[idx]

# Model Definition
class MLP(nn.Module):
    def __init__(self, in_features, hidden_dims, out_features):
        super().__init__()
        layers = []
        prev_dim = in_features
        for h in hidden_dims:
            layers.append(nn.Linear(prev_dim, h))
            layers.append(nn.BatchNorm1d(h))
            layers.append(nn.ReLU())
            layers.append(nn.Dropout(0.2))
            prev_dim = h
        layers.append(nn.Linear(prev_dim, out_features))
        self.network = nn.Sequential(*layers)

    def forward(self, x):
        return self.network(x)
```

---

## 💡 Best Practices Demonstrated

1. **Feature Scaling**: Essential for neural networks. Always fit `StandardScaler` on training data and transform validation/test sets to avoid data leakage.
2. **Model Checkpointing**: Save state dictionary (`model.state_dict()`) when validation loss reaches a new minimum (`best_model.pt`).
3. **Mini-batch Training**: Utilize `DataLoader` with appropriate batch size (e.g., 32 or 64) and `shuffle=True` for training.
