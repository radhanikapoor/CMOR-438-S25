# Principal Component Analysis (PCA)

This section demonstrates how to apply **Principal Component Analysis (PCA)** for dimensionality reduction and visualization. PCA is an unsupervised linear transformation technique that projects data into a lower-dimensional space while preserving as much variance as possible.

## What is PCA?

PCA transforms the original features into a new set of orthogonal axes called **principal components**, ordered by the amount of variance they capture from the data. The goal is to reduce dimensionality while retaining the most important information.

Mathematically, the transformation is given by:

$$
Z = XW
$$

Where:
- $X$ is the standardized data matrix (samples × features)
- $W$ is the matrix of eigenvectors (principal axes)
- $Z$ is the projection of the data onto the principal components

## Implementation Overview

 we used `sklearn.decomposition.PCA` to efficiently compute components 

## Explained Variance

We evaluated how much variance each principal component captures. The first few components often capture most of the variability, justifying dimensionality reduction.

## 2D Visualization

We visualized the data projected onto the top 2 principal components to reveal structure:

- Similar groups cluster together.
- PCA reveals directions of maximum variance.
- Useful for pattern recognition and preprocessing before clustering or classification.

## Limitations

While PCA is a powerful tool, it has several limitations:

- **Linear**: PCA assumes linear relationships between features.
- **Interpretability**: Principal components are combinations of original features and may lack intuitive meaning.
- **Sensitive to scaling**: Features must be standardized for meaningful results.
- **Ignores label information**: PCA is unsupervised and does not consider class boundaries.

## Conclusion

PCA is a valuable technique for data compression and visualization. It helps simplify high-dimensional datasets while retaining essential structure and variance, making it a common first step in many data science workflows.
