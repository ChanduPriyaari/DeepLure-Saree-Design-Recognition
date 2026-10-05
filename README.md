# Color-Invariant Saree Design Recognition using PyTorch

## Overview

This project focuses on saree design recognition with reduced dependence on color. A pretrained ResNet-50 model is fine-tuned using PyTorch to classify four saree design categories:

- Banarasi
- Bandhani
- Ikat
- Pichwai

Color augmentation is applied during training to improve robustness to changes in image color and appearance.

## Approach

The model uses a pretrained ResNet-50 backbone with transfer learning. The final classification layer is adapted for four classes.

Training includes:

- Image resizing to 224 × 224
- Random horizontal flipping
- Random rotation
- ColorJitter augmentation
- ImageNet normalization
- Class-weighted cross-entropy loss
- AdamW optimizer
- Validation-based learning-rate scheduling
- Early stopping and best-checkpoint selection

The 2048-dimensional feature representation from ResNet-50 is also used for image retrieval and verification using L2-normalized cosine similarity.

## Dataset

The experiments use the publicly available Indian Saree Patterns dataset from Kaggle.

The proprietary DeepLure Saree Corpus is not redistributed in this repository.

## Evaluation

### Classification

- Best Validation Accuracy: 96.52%
- Test Accuracy: 95.00%

### Image Retrieval

- Top-1 Retrieval: 93.33%
- Top-3 Retrieval: 93.33%
- Top-5 Retrieval: 95.00%

### Color-Invariance Experiment

Synthetic color perturbations were applied to the test images to evaluate robustness to color changes.

- Top-1: 95.00%
- Top-3: 95.00%
- Top-5: 95.00%

### Verification

Verification was evaluated using synthetic color-perturbation pairs.

- ROC-AUC: 99.94%
- Accuracy: 99.17%
- Precision: 100.00%
- Recall: 98.33%
- F1 Score: 99.16%

These verification results represent robustness to synthetic color perturbations and should not be interpreted as independent same-motif verification performance.

## Model Details

- Architecture: ResNet-50
- Framework: PyTorch
- Embedding Dimension: 2048
- Parameters: 23,508,032
- Approximate FP32 Model Size: 89.68 MB

## Repository Contents

```text
DeepLure-Saree-Design-Recognition/
└── notebook8dfba43e40.ipynb
