# DBSCAN Clustering on Insurance Data

In this notebook, we explore **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)** — an unsupervised clustering algorithm that identifies dense regions of data and labels low-density points as outliers.

Unlike K-Means, DBSCAN:
- Does **not** require the number of clusters in advance
- Can find **non-spherical** clusters
- Automatically detects and isolates **outliers**

---

## How DBSCAN Works

DBSCAN relies on two key parameters:

- **`eps`**: Maximum distance between two points to be considered neighbors
- **`min_samples`**: Minimum number of points required to form a dense region

### Cluster Types:
- **Core Points**: Have ≥ `min_samples` within `eps` radius
- **Border Points**: Not core points themselves but within `eps` of a core
- **Noise Points**: Neither core nor border

---

## Datasets Used

### 1. Car Insurance Dataset

Initially, DBSCAN was applied to a preprocessed version of the car insurance dataset with features like `Age`, `Annual Premium`, and `Vintage`. However, despite tuning `eps` and `min_samples`, the algorithm failed to identify meaningful clusters. Most data points were labeled as noise.

DBSCAN may struggle on sparse, high-dimensional, or uniformly distributed data.

### 2. Wine Dataset (PCA-reduced)

To test DBSCAN in a more favorable setting:
- The **Wine dataset** was used with PCA applied for dimensionality reduction.
- In this 2D setting, DBSCAN was able to:
  - Form distinct clusters
  - Clearly identify outliers
  - Outperform K-Means in capturing true groupings

---

## Evaluation Techniques

- **Scatter plots** in 2D PCA space to visualize cluster shapes
- **Silhouette Score** to evaluate cohesion and separation
- **Parameter sweep** over `eps` and `min_samples` to tune density sensitivity

---

## Strengths of DBSCAN

- **No need to specify `k`**: Automatically determines the number of clusters
- **Outlier detection**: Explicitly labels noise
- **Robust to shape**: Identifies clusters of arbitrary geometry
- **No assumption of cluster size**: Handles varying densities better than K-Means

---

## Weaknesses of DBSCAN

Despite its power, DBSCAN has several limitations:

- **Sensitive to parameter choice**: Poor `eps` or `min_samples` leads to over- or under-clustering
- **Struggles with high-dimensional data**: Distance becomes less meaningful
- **Difficulty with varying density**: Assumes uniform density, failing with clusters of differing compactness
- **Ineffective on scaled/uniform datasets**: May fail if clusters aren't well-separated in feature space

---

## Conclusion

DBSCAN is a valuable clustering technique when data exhibits local density patterns and noise. In this project, we found:

- DBSCAN underperforms on sparse real-world data like the insurance dataset
- With PCA and a more structured dataset (Wine), DBSCAN excels in identifying meaningful clusters

Careful preprocessing and parameter tuning are critical to unlocking DBSCAN's full potential.
