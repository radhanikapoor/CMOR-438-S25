# Unsupervised Learning Module


## What is Unsupervised Learning?

Unsupervised learning is a type of machine learning that works with **unlabeled data**, where the goal is to uncover hidden patterns, groupings, or structures without any predefined outcomes. It is commonly used for clustering, dimensionality reduction, anomaly detection, and exploratory data analysis.

Unlike supervised learning, unsupervised models do not predict specific outcomes but instead reveal insights about the structure of the data.

<img src="unsupervised_learning.png" alt="Unsupervised Learning Image" width="1500"/>

---

## Algorithms Implemented

### 1. K-Means Clustering
- Type: Clustering
- Description: Partitions data into k clusters by minimizing intra-cluster variance. Assumes spherical cluster shapes and requires the number of clusters as input.
- Dataset Used: `Wholesale.csv`

### 2. DBSCAN
- Type: Clustering
- Description: Density-Based Spatial Clustering of Applications with Noise. Groups together points that are closely packed and marks points that lie alone in low-density regions as outliers.
- Dataset Used: `Wholesale.csv`

### 3. Principal Component Analysis (PCA)
- Type: Dimensionality Reduction
- Description: Transforms data into a set of orthogonal components that capture the most variance. Often used as a preprocessing step or for visualization.
- Dataset Used: `car_insurance.csv`

### 4. Singular Value Decomposition (SVD)
- Type: Dimensionality Reduction
- Description: Decomposes a matrix into singular vectors and values. Applied here to reduce the dimensionality of image data and reconstruct compressed versions.
- Dataset Used: Image dataset embedded in the notebook

---

## Datasets

| Dataset             | Description                                         | Used For                   |
|---------------------|-----------------------------------------------------|----------------------------|
| `Wholesale.csv`     | Spending patterns of wholesale customers across product categories | DBSCAN |
| `car_insurance.csv` | Attributes of car insurance customers               |  PCA, K means, DBSCAN |
| Olivetti Faces Dataset | 400 greyscale facial images (64x64)               | SVD |

### `Wholesale.csv`

This dataset contains spending data from customers of a wholesale distributor. It is used to analyze patterns in customer purchase behavior.

**Columns:**

- `Fresh`: Annual spending on fresh products
- `Milk`: Annual spending on milk products
- `Grocery`: Annual spending on grocery products
- `Frozen`: Annual spending on frozen products
- `Detergents_Paper`: Annual spending on cleaning products
- `Delicassen`: Annual spending on delicatessen items
- (Optional categorical columns: `Channel`, `Region`)

---

### `car_insurance.csv`

This dataset includes personal and demographic information about car insurance customers. It is used to examine underlying dimensions in the data through PCA.

**Columns:**

- Includes a mix of numerical and categorical features such as `Age`, `Income`, `Vehicle_Type`, `Credit_Score`, etc.
- Typically used to uncover correlations and reduce dimensions for visualization and interpretation

---

> **Note**: All datasets are stored in the `Datasets/` folder at the root of the project. When loading data from a notebook, use relative paths like `../Datasets/car_insurance.csv` depending on your notebook’s location.

---

The car insurance data set was used across as many algorithms as possible to help draw conclusions on how algorithms perform with a specific type of data set and understand what it works best on. I have also included practical implications for the indistry at the bottom of the unupervised learning algorithms

## Reproducibility

### Clone the Repository

```bash
git clone https://github.com/t0dd26/CMOR438-Spring-2025.git
cd CMOR438-Spring-2025
```

### Install Required Dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

### Launch Jupyter Notebook

```bash
jupyter lab
```

Then open any of the following notebooks under `notebooks/` (or your working folder):

- `K_Means_clustering.ipynb`
- `DBSCAN.ipynb`
- `Principal_Component_Analysis.ipynb`
- `SVD.ipynb`

---

## Notes

- All code is written in Python 3 using Jupyter Notebooks.
- Each notebook includes clear visualizations and analysis of patterns in the data.
- Ensure both `Wholesale.csv` and `car_insurance.csv` are in the `Datasets/` folder, and adjust relative paths accordingly when reading data from notebooks.
