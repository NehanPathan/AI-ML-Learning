# Convolutional Neural Networks (CNN)

Hands-on implementations of Convolutional Neural Networks for computer vision and image classification using **PyTorch** and **torchvision**.

---

## 📂 Directory Contents

| File / Folder | Description |
| :--- | :--- |
| `CNN_for_CIFAR10.ipynb` | End-to-end CNN implementation trained on the CIFAR-10 image dataset |
| `data/` | Directory where CIFAR-10 raw/processed batches are downloaded automatically |
| `prac.ipynb` | Notebook for testing kernel operations, pooling effects, and receptive fields |

---

## 🖼️ Project: CIFAR-10 Image Classification

The **CIFAR-10** dataset consists of 60,000 $32 \times 32$ color images across 10 classes (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck).

### CNN Building Blocks Covered:
1. **2D Convolution (`nn.Conv2d`)**:
   - Extracting spatial feature hierarchies (edges $\to$ textures $\to$ object parts).
   - Kernel size, stride, and padding calculations:
     $$\text{Output size} = \left\lfloor \frac{\text{Input} - \text{Kernel} + 2 \times \text{Padding}}{\text{Stride}} \right\rfloor + 1$$
2. **Pooling (`nn.MaxPool2d`)**:
   - Downsampling spatial dimensions to provide translation invariance and reduce parameter count.
3. **Batch Normalization (`nn.BatchNorm2d`)**:
   - Accelerating convergence and stabilizing gradient propagation.
4. **Non-linearity (`nn.ReLU`)**:
   - Introducing necessary non-linear transformations after each convolution.
5. **Fully Connected / Dense Head (`nn.Linear`)**:
   - Flattening spatial feature maps and mapping features into class probability logits.

---

## 🛠️ Architecture Implementation Example

```python
import torch
import torch.nn as nn

class ConvNet(nn.Module):
    def __init__(self, num_classes=10):
        super().__init__()
        self.features = nn.Sequential(
            # Block 1: 3x32x32 -> 32x32x32 -> 32x16x16
            nn.Conv2d(in_channels=3, out_channels=32, kernel_size=3, padding=1),
            nn.BatchNorm2d(32),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=2, stride=2),
            
            # Block 2: 32x16x16 -> 64x16x16 -> 64x8x8
            nn.Conv2d(in_channels=32, out_channels=64, kernel_size=3, padding=1),
            nn.BatchNorm2d(64),
            nn.ReLU(inplace=True),
            nn.MaxPool2d(kernel_size=2, stride=2)
        )
        self.classifier = nn.Sequential(
            nn.Flatten(),
            nn.Linear(64 * 8 * 8, 256),
            nn.ReLU(inplace=True),
            nn.Dropout(0.3),
            nn.Linear(256, num_classes)
        )

    def forward(self, x):
        x = self.features(x)
        return self.classifier(x)
```

---

## 💡 Practical Computer Vision Tips

- **Data Augmentation**: Use `torchvision.transforms.Compose` with `RandomCrop`, `RandomHorizontalFlip`, and `Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5))` to boost generalization.
- **GPU Acceleration**: Always verify CUDA or Apple Silicon MPS device availability for image workloads.
- **Flattening**: Use `nn.Flatten()` before dense classification layers.
