# K-Nearest Neighbors on Insurance Data

This project explores the **K-Nearest Neighbors (KNN)** algorithm to predict whether an individual is a smoker based on their demographic and health-related features.

KNN is a **non-parametric**, **instance-based** learning method. It makes predictions by comparing a new data point to the most similar training examples using a distance metric.

---

## What is KNN?

The KNN algorithm classifies a sample by majority vote among its `k` closest neighbors in the feature space. It requires no explicit training phase — it simply stores the dataset and defers all computation to prediction time.

### Prediction Rule

For a query point \( x \):

$$
\hat{y}(x) = \text{mode} \left( y_i \mid x_i \in \mathcal{N}_k(x) \right)
$$

Where:
- $ \mathcal{N}_k(x) $: the set of the `k` nearest neighbors to $ x $
- Distance metric (usually Euclidean):

$$
d(x_1, x_2) = \sqrt{ \sum_{i=1}^{n} (x_{1i} - x_{2i})^2 }
$$

---

## Implementation Overview

We implemented KNN in two ways:
1. **Manual implementation**:
   - Compute distances, sort neighbors, and vote
   - Good for conceptual understanding

2. **scikit-learn’s `KNeighborsClassifier`**:
   - Efficient and optimized implementation
   - Easily configurable with `n_neighbors`, distance metric, and weighting

---

## Preprocessing

- One-hot encoded categorical variables like `sex`, `region`, and `smoker`
- Standardized all features using `StandardScaler` to ensure equal weight in distance calculations
- Split the dataset into train and test sets

---

## Evaluation Metrics

To evaluate classification performance, we used:
- **Accuracy**
- **Confusion Matrix**
- **Precision, Recall, F1 Score** (via classification report)
- **ROC Curve** and **AUC Score**

These metrics help visualize class separation and detect any imbalance or false prediction patterns.

---

## Weaknesses of KNN

Although KNN is simple and intuitive, it comes with several limitations:

- **Computationally expensive**: Prediction involves calculating distances to every training point
- **Storage intensive**: Must retain the entire training dataset in memory
- **Sensitive to irrelevant or redundant features**
- **Suffers with high dimensionality**: Distance measures become less meaningful in high-dimensional space (curse of dimensionality)
- **Hard to interpret**: No model parameters or coefficients to analyze

---

## Conclusion

KNN is a powerful yet simple algorithm ideal for small-scale datasets and problems where the decision boundary is highly non-linear. In this project, we demonstrated:
- Manual and library-based implementations
- Importance of feature scaling in distance-based models
- Multiple evaluation techniques for binary classification

Future work could involve experimenting with:
- Distance-weighted voting
- Dimensionality reduction techniques (e.g., PCA)
- More scalable models like SVM or random forests
