# Brain Tumor Diagnostic Platform

A deep learning-based medical imaging tool that classifies brain MRI scans into four diagnostic categories using a Convolutional Neural Network (CNN) built with PyTorch.

> Final Year Project — B.Tech in Computer Science and Engineering, Dr. Sudhir Chandra Sur Degree College (2024)

---

## Overview

Brain tumor diagnosis from MRI scans is a time-intensive process that relies heavily on radiologist expertise. This project explores automating the classification step using CNNs, with the goal of providing a reliable assistive tool for clinical screening.

The model classifies MRI scans into four categories:
- Glioma
- Meningioma
- Pituitary tumor
- No tumor

---

## Results

| Class | Accuracy |
|-------|----------|
| Overall | 82.84% |
| Glioma | 86.05% |
| Meningioma | 85.71% |
| No Tumor | 92.31% |
| Pituitary | 97.06% |

---

## Dataset Structure

Three separate datasets were used across the pipeline:

```
Dataset/
├── Training/               # Primary 4-class MRI dataset (Kaggle)
│   ├── glioma/
│   ├── meningioma/
│   ├── pituitary/
│   └── no_tumor/
├── Validation/             # 4-class test split (used as validation during training)
│   ├── glioma/
│   ├── meningioma/
│   ├── pituitary/
│   └── no_tumor/
└── Testing/                # Independent binary dataset (Kaggle) — final evaluation
    ├── yes/                # Tumor present
    └── no/                 # No tumor
```

The training and validation sets are drawn from a real-world MRI dataset originally collected by The Cancer Imaging Archive (TCIA) and sourced via Kaggle. The testing set is an independent binary classification dataset (tumor / no tumor), used as a final out-of-distribution stress test to evaluate the model's generalization beyond its training distribution.

---

## Why a Binary Test Set for a Multiclass Model?

Rather than only testing on held-out samples from the same source, using a structurally different dataset (yes/no labels vs. four-class labels) provides a stronger signal of real-world robustness — the model must correctly map its four-class predictions to the presence or absence of a tumor without having seen this labeling scheme during training.

---

## Methodology

- **Model architecture:** Convolutional Neural Network (CNN)
- **Framework:** PyTorch
- **Techniques applied:**
  - Data augmentation (flipping, rotation, zoom) to improve generalization
  - Transfer learning to leverage pre-trained feature representations
  - Hyperparameter tuning (learning rate, batch size, epochs) to optimize clinical relevance

---

## Project Structure

```
├── data/               # Dataset directory (not included, see Dataset section)
├── model/              # Model architecture definition
├── train.py            # Training script
├── evaluate.py         # Evaluation and metrics
├── notebooks/          # Exploratory analysis and experiments
└── requirements.txt    # Dependencies
```

---

## Setup

```bash
git clone https://github.com/ehtesham04/Brain-Tumor-Prediction-Model
cd Brain-Tumor-Prediction-Model
pip install -r requirements.txt
```

---

## Dependencies

- Python 3.x
- PyTorch
- NumPy
- Matplotlib
- Scikit-learn

---

## Acknowledgements

Training/validation dataset sourced from Kaggle, originally collected from The Cancer Imaging Archive (TCIA). The binary testing dataset was also sourced from Kaggle. Project developed as part of the B.Tech final year curriculum.
