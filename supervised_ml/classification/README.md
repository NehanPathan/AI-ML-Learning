# Classification in Supervised Machine Learning

Predicting discrete categories, classes, or labels from structured tabular features.

---

## 📂 Subdirectories

| Folder | Contents | Description |
| :--- | :--- | :--- |
| [`concepts/`](concepts/README.md) | Notebooks for core classification algorithms | Logistic Regression, KNN, Naive Bayes, Support Vector Machines (SVM), Decision Trees |
| [`mini_projects/`](mini_projects/README.md) | Practical real-world classification projects | Credit Risk, E-commerce Behavior, Employee Turnover, Iris Flower Classification |

---

## 🎯 Classification Algorithms Matrix

| Algorithm | Type | Strengths | Ideal Scenario |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | Linear / Probabilistic | Interpretable odds ratios, fast, outputs calibrated probabilities | Baseline binary/multinomial classification |
| **K-Nearest Neighbors (KNN)** | Non-parametric / Instance-based | No training phase, intuitive distance metrics | Low-dimensional data with clean cluster boundaries |
| **Naive Bayes** | Probabilistic (Bayes' Theorem) | High efficiency, handles high dimensions, great with text | Text classification, spam filtering |
| **Support Vector Classifier (SVC)**| Kernel / Margin-based | Maximizes margin, effective in high dimensions, kernel trick | Complex non-linear separation boundaries |
| **Decision Trees** | Non-parametric / Rule-based | Highly explainable, handles non-linear interactions, no scaling needed | Rule-based decision systems, feature importance |

---

## 📊 Evaluation Metrics

Classification models are evaluated using:
- **Confusion Matrix**: True Positives (TP), False Positives (FP), True Negatives (TN), False Negatives (FN)
- **Accuracy**: $\frac{\text{TP} + \text{TN}}{\text{Total}}$ (Caution: misleading on imbalanced data)
- **Precision**: $\frac{\text{TP}}{\text{TP} + \text{FP}}$ (Quality of positive predictions)
- **Recall (Sensitivity)**: $\frac{\text{TP}}{\text{TP} + \text{FN}}$ (Completeness of positive predictions)
- **F1-Score**: Harmonic mean of Precision and Recall: $2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$
- **ROC-AUC**: Area under Receiver Operating Characteristic curve across classification thresholds
