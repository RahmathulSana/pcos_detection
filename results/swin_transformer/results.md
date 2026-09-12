# Swin Transformer Results

## Model Configuration

| Parameter | Value |
|---|---|
| Architecture | Swin Transformer |
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
| 1 | 0.1388 | 94.78% |
| 2 | 0.0377 | 99.01% |
| 3 | 0.0385 | 99.05% |
| 4 | 0.0297 | 99.30% |
| 5 | 0.0280 | 99.24% |

## Test Results

| Metric | Result |
|---|---:|
| Accuracy | 98.85% |
| Precision | 98.04% |
| Recall | 96.15% |
| F1-score | 97.09% |
| ROC-AUC | 99.74% |

## Classification Report

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| infected | 0.99 | 1.00 | 0.99 | 630 |
| noninfected | 0.98 | 0.96 | 0.97 | 156 |

## Confusion Matrix

```text
[[627, 3],
 [6, 150]]
Total test samples: 786
Correctly classified: 777
Misclassified: 9
```

## Interpretation

Swin Transformer achieved 98.85% accuracy and a 99.74% ROC-AUC on the held-out test dataset.

The model correctly classified 777 out of 786 test images and misclassified 9 images.

## Saved Visualizations

- `swin_confusion_matrix.png` — Swin Transformer confusion matrix
- `swin_roc_curve.png` — Swin Transformer ROC curve
- `swin_training_loss.png` — Swin Transformer training loss
- `swin_training_accuracy.png` — Swin Transformer training accuracy
- `swin_transformer_results.csv` — Swin Transformer performance metrics
