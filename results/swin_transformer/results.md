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
| 1 | 0.1012 | 96.75% |
| 2 | 0.0461 | 98.82% |
| 3 | 0.0347 | 99.08% |
| 4 | 0.0242 | 99.43% |
| 5 | 0.0278 | 99.20% |

## Test Results

| Metric | Result |
|---|---:|
| Accuracy | 98.60% |
| Precision | 99.05% |
| Recall | 99.13% |
| F1-score | 99.13% |
| ROC-AUC | 99.62% |


## Confusion Matrix

```text
[[625, 5],
 [6, 150]]
Total test samples: 786
Correctly classified: 775
Misclassified: 11
```

## Interpretation

Swin Transformer achieved 98.60% accuracy and a 99.62% ROC-AUC on the held-out test dataset.

The model correctly classified 775 out of 786 test images and misclassified 11 images.

