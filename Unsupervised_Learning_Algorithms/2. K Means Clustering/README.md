# K-Means Clustering for Customer Segmentation

In this project, we apply **K-Means Clustering**, a foundational unsupervised learning algorithm, to discover underlying customer segments in a car insurance dataset.

K-Means helps identify patterns or structure in unlabeled data, enabling data-driven segmentation that can inform marketing, pricing, or service personalization strategies.

---

## Workflow Summary

We follow a standard clustering pipeline:

1. **Preprocess** data (encode categoricals, scale numericals)
2. **Reduce dimensionality** with PCA for visualization
3. Apply **K-Means** across different values of $k$
4. Use the **Elbow Method** and **Silhouette Score** to select the optimal number of clusters
5. **Visualize clusters** in 2D and interpret segment differences (e.g., by annual premium, claims, or age)

---

## What is K-Means?

K-Means aims to partition data into $k$ clusters by minimizing within-cluster variance. It assigns each point to the cluster with the nearest centroid and iteratively updates these centroids.

### Objective Function


$\arg\min_S \sum_{i=1}^k \sum_{x \in S_i} \|x - \mu_i\|^2$



Where:
- $S_i$: data points in cluster $i$
- $\mu_i$: centroid of cluster $i$

---

## Dimensionality Reduction with PCA

To visualize clusters in 2D, we apply **Principal Component Analysis (PCA)**. PCA projects high-dimensional data onto the directions of greatest variance, simplifying interpretation of clustering outcomes.

---

## Evaluation Techniques

- **Within-Cluster Sum of Squares (WCSS)**: Measures total intra-cluster variance
- **Elbow Method**: Plot WCSS vs. $k$ to identify diminishing returns ("elbow")
- **Silhouette Score**: Evaluates cluster cohesion and separation (closer to 1 = better)

---

## Cluster Interpretation

Once optimal clusters are selected:
- We visualize them using PCA-reduced 2D scatter plots
- Analyze key feature distributions (e.g., `Annual Premium`, `Policy Type`, `Vehicle Age`) across clusters
- Gain business insights by profiling each cluster

---

## Weaknesses of K-Means

Despite its simplicity and speed, K-Means has several limitations:

- **Assumes spherical clusters**: Performs poorly with elongated or irregular shapes
- **Needs $k$ in advance**: Choosing the optimal number of clusters can be non-trivial
- **Sensitive to initialization**: Poor centroid seeds can lead to suboptimal solutions (mitigated by `k-means++`)
- **Not robust to outliers**: Single anomalies can heavily shift centroids
- **Equal importance assumption**: Without proper scaling, features with larger magnitudes dominate the distance metric

---

## Conclusion

K-Means is an effective baseline clustering technique that, when paired with preprocessing and dimensionality reduction, can yield interpretable groupings in unlabeled data.

In this notebook, we:
- Preprocessed and reduced dimensionality of a car insurance dataset
- Applied K-Means clustering
- Selected the optimal number of clusters using WCSS and silhouette analysis
- Visualized and interpreted customer segments

Next steps could include:
- Trying **DBSCAN** or **Gaussian Mixture Models** for non-spherical clusters
- Using domain-specific metrics to validate clustering relevance
- Deploying segmentation insights for targeted interventions
