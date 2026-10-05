# Approach Note

We fine-tune a pretrained ResNet-50 in PyTorch for four saree design categories, using ColorJitter augmentation to reduce dependence on color. The classifier's 2048-dimensional feature representation is L2-normalized and used for cosine-similarity retrieval and verification. We evaluate classification accuracy, Top-K retrieval, robustness to synthetic color perturbations, and verification using ROC-AUC, precision, recall and F1, with early stopping and the best validation checkpoint.
