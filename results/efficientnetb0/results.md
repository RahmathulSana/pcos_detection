# EfficientNetB0 Results

## Model Configuration

| **Parameter** | **Value** |
|---|---|
| Architecture | EfficientNetB0 |
| Pretrained Weights | ImageNet |
| Fine-tuning | All layers |
| Input Size | 224 × 224 |
| Output Classes | 2 |
| Loss Function | CrossEntropyLoss |
| Optimizer | Adam |
| Learning Rate | 0.0001 |
| Batch Size | 32 |
| Epochs | 5 per experiment |
| GPU | NVIDIA Tesla T4 |

## Baseline Training Results

| **Epoch** | **Loss** | **Training Accuracy** |
|---|---:|---:|
| 1 | 0.2118 | 92.78% |
| 2 | 0.0415 | 98.95% |
| 3 | 0.0306 | 99.24% |
| 4 | 0.0278 | 99.20% |
| 5 | 0.0183 | 99.52% |

## Baseline Test Results

| **Metric** | **Result** |
|---|---:|
| Test Accuracy | 98.85% |
| Macro Precision | 98.09% |
| Macro Recall | 98.32% |
| Macro F1-score | 98.20% |
| ROC-AUC* | 99.24% |

## Baseline Classification Report

| **Class** | **Precision** | **Recall** | **F1-score** | **Support** |
|---|---:|---:|---:|---:|
| infected | 0.9936 | 0.9921 | 0.9929 | 630 |
| noninfected | 0.9682 | 0.9744 | 0.9712 | 156 |

## Baseline Confusion Matrix

```text
[[625, 5],
 [  4, 152]]
```

- Correctly classified: 777
- Misclassified: 9
- Total test samples: 786

## Class-Weighted Experiment

The class-weighted experiment continued fine-tuning from the saved baseline checkpoint using weighted cross-entropy loss.

### Class Weights

| **Class** | **Weight** |
|---|---:|
| infected | 0.6234 |
| noninfected | 2.5257 |

### Class-Weighted Training Results

| **Epoch** | **Loss** | **Training Accuracy** |
|---|---:|---:|
| 1 | 0.0310 | 99.11% |
| 2 | 0.0226 | 99.30% |
| 3 | 0.0196 | 99.40% |
| 4 | 0.0288 | 99.17% |
| 5 | 0.0153 | 99.59% |

### Baseline vs. Class-Weighted Test Results

| **Metric** | **Baseline** | **Class-Weighted** |
|---|---:|---:|
| Test Accuracy | 98.85% | 98.73% |
| Macro Precision | 98.09% | 97.78% |
| Macro Recall | 98.32% | 98.24% |
| Macro F1-score | 98.20% | 98.01% |
| ROC-AUC* | 99.24% | 99.75% |

### Class-Weighted Classification Report

| **Class** | **Precision** | **Recall** | **F1-score** | **Support** |
|---|---:|---:|---:|---:|
| infected | 0.9936 | 0.9905 | 0.9921 | 630 |
| noninfected | 0.9620 | 0.9744 | 0.9682 | 156 |

### Class-Weighted Confusion Matrix

```text
[[624, 6],
 [  4, 152]]
```

- Correctly classified: 776
- Misclassified: 10
- Total test samples: 786

## Interpretation

The EfficientNetB0 baseline achieved 98.85% accuracy and a ROC-AUC of 99.24% on the held-out test dataset. It correctly classified 777 out of 786 test images.

The class-weighted experiment achieved 98.73% accuracy and a ROC-AUC of 99.75%. Although its ROC-AUC was higher, it produced one additional misclassification and did not improve recall for the minority `noninfected` class.

Therefore, class weighting did not provide a clear overall improvement in this experiment. The baseline remains the stronger reference based on accuracy and macro F1-score, while the class-weighted model showed better ROC-AUC.

## Saved Visualizations

### Baseline
- `efficientnetb0_confusion_matrix.png` — Baseline confusion matrix
- `Efficientnetb0_ROC.png` — Baseline ROC curve

### Class-Weighted
- `class_weighted_confusion_matrix.png` — Class-weighted confusion matrix
- `class_weighted_ROC.png` — Class-weighted ROC curve

- `results.md` — Model configuration, training history, evaluation metrics, and interpretation

\* ROC-AUC treats the `noninfected` class as the positive class for score calculation, consistent with the evaluation code. These results describe performance on the held-out dataset and do not establish clinical diagnostic performance.
