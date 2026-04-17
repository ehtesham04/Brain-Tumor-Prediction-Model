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
- No tumor (Benign)

---

## Results

| Metric | Value |
|--------|-------|
| Classification accuracy | 85% |
| Reduction in misclassification (vs. baseline) | 18% |
| Number of classes | 4 |

---

## Dataset

Real-world brain MRI scan dataset sourced from Kaggle, originally collected from The Cancer Imaging Archive (TCIA). The dataset contains labeled MRI images across the four tumor categories listed above.

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

Dataset sourced from Kaggle. Project developed as part of the B.Tech final year curriculum.
