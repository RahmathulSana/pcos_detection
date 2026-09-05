# Early PCOS Detection Using Deep Learning from Ultrasound Images

## Overview

This project explores the use of deep learning and transfer learning for the early screening of PCOS using ultrasound images.

The study focuses on preprocessing and dataset quality, followed by training and comparison of multiple deep learning architectures:

- ResNet50
- EfficientNetB0
- MobileNetV2

Model performance will be evaluated using accuracy, precision, recall, F1-score, ROC-AUC, and confusion matrices. Grad-CAM will also be used to improve model interpretability.

> **Note:** This project is developed for academic and research purposes and is not intended to replace clinical diagnosis.

## Workflow

```text
Dataset
   ↓
Dataset Audit & Cleaning
   ↓
Preprocessing & Augmentation
   ↓
Deep Learning Models
   ↓
Performance Evaluation
   ↓
Model Comparison
   ↓
Grad-CAM Explainability
   ↓
Prediction GUI 
```


## Dataset Preparation

The dataset was carefully audited before model training.

- 11,784 readable images were initially identified.
- 3,996 unique image contents remained after exact duplicate analysis.
- Cross-class near-duplicate analysis identified 34 strong conflicting pairs (68 images), which were removed.
- Final cleaned dataset: 3,928 images.
- The dataset was divided into approximately 80% training and 20% testing data.

## Technologies
- Python
- PyTorch
- torchvision
- OpenCV
- scikit-learn
- NumPy
- Pandas
- Matplotlib
- Google Colab
- Git & GitHub

## Team
Rahmathul Sana C P
Simna Muhammed E C

*Guide*: Prof. Gopika Gopan
TKM College of Engineering

