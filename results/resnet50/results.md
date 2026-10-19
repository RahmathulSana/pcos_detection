# ResNet50 Results

## Model Configuration

| **Parameter** | **Value** |
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

| **Metric** | **Result** |
|---|---:|
| Test Accuracy | 98.73% |
| Macro Precision | 98.00% |
| Macro Recall | 98.00% |
| Macro F1-score | 98.00% |
| ROC-AUC* | 99.84% |

### Confusion Matrix

```text
[[625, 5],
 [5, 151]]
```

- True positives (PCOS-positive): 625
- False negatives (PCOS-positive): 5
- False positives (PCOS-negative): 5
- True negatives (PCOS-negative): 151
- Total test samples: 786
- Total misclassified samples: 10

## Class-Weighted Experiment

Class weights calculated from the training dataset:

| **Class** | **Weight** |
|---|---:|
| Infected (PCOS-positive) | 0.6234 |
| Noninfected (PCOS-negative) | 2.5257 |

| **Metric** | **Baseline** | **Class-Weighted** |
|---|---:|---:|
| Test Accuracy | 98.73% | 98.73% |
| Macro Precision | 98.00% | 98.00% |
| Macro Recall | 98.00% | 98.00% |
| Macro F1-score | 98.00% | 98.00% |
| ROC-AUC* | 99.84% | 99.88% |

The class-weighted experiment was performed by continuing fine-tuning from the saved baseline checkpoint using a weighted cross-entropy loss. Both models produced the same hard predictions and confusion matrix. The class-weighted model showed a small increase in ROC-AUC, from 99.84% to 99.88%, but no improvement in accuracy or macro F1-score.

## Interpretation

The ResNet50 baseline achieved 98.73% accuracy on the held-out test set, correctly classifying 776 of 786 images. The confusion matrix shows five false negatives and five false positives.

The class-weighted experiment retained the same classification performance while producing a small increase in ROC-AUC. Therefore, class weighting did not provide a meaningful improvement in the model's overall classification metrics in this experiment.

## Saved Results

- `confusion_matrix.png` — Baseline confusion matrix
- `ROC.png` — Baseline ROC curve
- `confusion_matrix_weighted.png` — Class-weighted confusion matrix
- `ROC_weighted.png` — Class-weighted ROC curve
- `results.md` — Experiment configuration, metrics, and interpretation

\* ROC-AUC treats the noninfected (PCOS-negative) class as the positive class for score calculation, consistent with the evaluation code. Results reflect classification on this dataset's held-out test split and do not establish clinical diagnostic performance.
