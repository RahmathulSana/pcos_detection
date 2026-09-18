# Vision Transformer Results

## Model

Vision Transformer (ViT-B/16)

## Training

The Vision Transformer was trained for 5 epochs using the PCOS image dataset.

### Training Loss

| Epoch | Training Loss |
|---|---:|
| 1 | 0.1722 |
| 2 | 0.0647 |
| 3 | 0.0416 |
| 4 | 0.0329 |
| 5 | 0.0438 |

### Training Accuracy

| Epoch | Training Accuracy |
|---|---:|
| 1 | 93.16% |
| 2 | 97.99% |
| 3 | 98.95% |
| 4 | 99.11% |
| 5 | 98.66% |

## Evaluation Results

| Metric | Score |
|---|---:|
| Accuracy | 98.60% |
| Precision | 96.18% |
| Recall | 96.79% |
| F1-Score | 96.49% |
| ROC-AUC | 99.72% |

## Confusion Matrix

The confusion matrix contains:

- True Positives: 624
- False Positives: 6
- False Negatives: 5
- True Negatives: 151

## Result Files

- `vit_results.csv` — Evaluation metrics
- `vit_training_loss.png` — Training loss curve
- `vit_training_accuracy.png` — Training accuracy curve
- `vit_roc_curve.png` — ROC curve
- `vit_confusion_matrix.png` — Confusion matrix
