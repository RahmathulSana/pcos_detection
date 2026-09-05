# ResNet50 Results

## Model Configuration

| Parameter | Value |
|---|---|
| Architecture | ResNet50 |
| Pretrained Weights | ImageNet |
| Fine-tuning | All layers |
| Input Size | 224 × 224 |
| Output Classes | 2 |
| Loss Function | CrossEntropyLoss |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Batch Size | 32 |
| Epochs | 5 |
| GPU | NVIDIA Tesla T4 |

## Baseline Results

| Metric | Result |
|---|---:|
| Accuracy | 98.85% |
| Precision | 96.82% |
| Recall | 97.44% |
| F1-score | 97.12% |
| ROC-AUC | 99.67% |

## Confusion Matrix

```text
[[625, 5],
 [4, 152]]
True Positives (infected): 625
False Negatives (infected): 5
False Positives (noninfected): 4
True Negatives (noninfected): 152

Total test samples: 786
Total misclassified samples: 9
```
## Class-Weighted Experiment

Class weights:

| Class | Weight |
|---|---:|
| Infected | 0.6234 |
| Noninfected | 2.5257 |

| Metric | Baseline | Class-Weighted |
|---|---:|---:|
| Accuracy | 98.85% | 98.85% |
| Precision | 96.82% | 96.82% |
| Recall | 97.44% | 97.44% |
| F1-score | 97.12% | 97.12% |
| ROC-AUC | 99.67% | 99.72% |

The class-weighted experiment produced the same accuracy, precision, recall, F1-score, and confusion matrix as the baseline model. A small improvement in ROC-AUC was observed.

## Interpretation

The ResNet50 model achieved strong performance on the held-out test set, with an accuracy of 98.85% and ROC-AUC of 99.67%.

The confusion matrix shows that 777 out of 786 test images were correctly classified, while 9 images were misclassified.

The class-weighted experiment did not produce a meaningful improvement in classification metrics compared with the baseline.

## Saved Results

- `confusion_matrix.png` — Confusion matrix visualization
- `roc_curve.png` — ROC curve visualization
- `results.md` — Experiment results and configuration