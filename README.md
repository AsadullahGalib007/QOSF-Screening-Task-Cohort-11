# Quantum Binary Classification on Palmer Penguins 🐧

A comparative study of **Variational Quantum Classifier (VQC)** and **Quantum Support Vector Machine (QSVM)** for binary classification using the **Palmer Penguins** dataset.

## Overview
- **Dataset**: Palmer Penguins (344 samples, 4 features, 3 species)
- **Tasks**: Binary classification across all species pairs
- **Feature Selection**: EDA-driven & PCA-based (2D)
- **Models**:
  - VQC (trainable, amplitude encoding, 3-layer ansatz)
  - QSVM (kernel-based, angle encoding)
  - Classical RBF-SVM (baseline)

## Key Findings
- **No quantum advantage** observed
- All methods achieve **~100% accuracy** on easy tasks
- Classical SVM outperforms on moderate tasks (up to **82.7%**)
- QSVM more stable and NISQ-friendly than VQC
- **Feature engineering > model choice**

## Results (5-fold Stratified Cross-Validation)

| Species Pair         | Feature Set | Method       | Accuracy (mean ± std) | F1-Score (mean) |
|----------------------|-------------|--------------|------------------------|-----------------|
| **Adelie vs Chinstrap** | **EDA**     | Classical SVM | **0.736 ± 0.023**     | **0.824**       |
|                      |             | VQC          | 0.696 ± 0.011         | 0.816           |
|                      |             | QSVM         | 0.691 ± 0.011         | 0.810           |
|                      | **PCA**     | Classical SVM | **0.827 ± 0.037**     | **0.882**       |
|                      |             | VQC          | 0.686 ± 0.009         | 0.814           |
|                      |             | QSVM         | **0.841 ± 0.032**     | **0.890**       |
| **Adelie vs Gentoo** | **EDA**     | Classical SVM | 0.989 ± 0.009         | 0.990           |
|                      |             | VQC          | 0.899 ± 0.082         | 0.891           |
|                      |             | QSVM         | **0.993 ± 0.009**     | **0.994**       |
|                      | **PCA**     | Classical SVM | **1.000 ± 0.000**     | **1.000**       |
|                      |             | VQC          | 0.993 ± 0.009         | 0.993           |
|                      |             | QSVM         | **1.000 ± 0.000**     | **1.000**       |
| **Chinstrap vs Gentoo** | **EDA**  | Classical SVM | **1.000 ± 0.000**     | **1.000**       |
|                      |             | VQC          | **1.000 ± 0.000**     | **1.000**       |
|                      |             | QSVM         | **1.000 ± 0.000**     | **1.000**       |
|                      | **PCA**     | Classical SVM | **1.000 ± 0.000**     | **1.000**       |
|                      |             | VQC          | **1.000 ± 0.000**     | **1.000**       |
|                      |             | QSVM         | **1.000 ± 0.000**     | **1.000**       |

## Run the Code
Open in Google Colab:  
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15HAclD4D4kOUJOOoBXIoTrhpiUY20Vkg)
