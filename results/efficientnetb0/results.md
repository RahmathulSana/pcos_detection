# EfficientNetB0 Results

## Model Configuration

| Parameter | Value |
|---|---|
| Architecture | EfficientNetB0 |
| Pretrained Weights | ImageNet |
| Input Size | 224 × 224 |
| Output Classes | 2 |
| Loss Function | CrossEntropyLoss |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Batch Size | 32 |
| Epochs | 5 |
| GPU | NVIDIA Tesla T4 |

## Training Results

| Epoch | Loss | Training Accuracy |
|---|---:|---:|
| 1 | 0.1845 | 95.39% |
| 2 | 0.0452 | 98.95% |
| 3 | 0.0345 | 99.11% |
| 4 | 0.0194 | 99.55% |
| 5 | 0.0193 | 99.52% |

## Test Results

| Metric | Result |
|---|---:|
| Accuracy | 98.73% |
| Precision | 96.79% |
| Recall | 96.79% |
| F1-score | 96.79% |
| ROC-AUC | 99.42% |

## Classification Report

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| infected | 0.99 | 0.99 | 0.99 | 630 |
| noninfected | 0.97 | 0.97 | 0.97 | 156 |

## Confusion Matrix

```text
[[625, 5],
 [5, 151]]
Total test samples: 786
Correctly classified: 776
Misclassified: 10
```

## Interpretation

EfficientNetB0 achieved 98.73% accuracy and a 99.42% ROC-AUC on the held-out test dataset. 
The model correctly classified 776 out of 786 test images.

## Saved Visualizations
-`confusion_matrix.png` — EfficientNetB0 confusion matrix
-`roc_curve.png` — EfficientNetB0 ROC curve
