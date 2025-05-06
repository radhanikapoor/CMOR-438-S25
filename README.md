# Machine Learning Algorithms and Applications

## Overview

This repository is a comprehensive collection of supervised and unsupervised machine learning algorithm implementations. The goal is to explore the theory and application of fundamental ML algorithms using Python, and to understand how each method interprets and operates on real-world datasets.

Each notebook includes well-documented code, visualizations, and clear markdown explanations to enhance reproducibility and learning.

## Project Structure

The project is organized by learning type (supervised vs. unsupervised), and further divided by algorithm families such as regression, classification, clustering, and dimensionality reduction.

### Supervised Learning
Supervised learning involves training models on labeled data where the outcome variable (target) is known. The following algorithms are implemented:

- **Linear Regression**: Fit a line to data for continuous prediction tasks.
- **Logistic Regression**: Predict binary classes using a sigmoid transformation.
- **Perceptron**: A binary linear classifier trained via stochastic gradient descent.
- **Multilayer Neural Network**: Implemented from scratch using mini-batch gradient descent.
- **Decision Trees & Regression Trees**: Tree-based models for both classification and regression.
- **Random Forests**: Ensemble method combining multiple decision trees for improved performance.
- **Ensemble Methods**: Techniques like bagging and boosting to enhance model stability and accuracy.

### Unsupervised Learning
Unsupervised learning is applied to unlabeled data to identify patterns or structure:

- **K-Means Clustering**: Partition data into clusters based on feature similarity.
- **DBSCAN**: Density-based clustering to detect arbitrarily shaped clusters and noise.
- **Principal Component Analysis (PCA)**: Reduce dimensionality while preserving variance.
- **Singular Value Decomposition (SVD)**: Used for dimensionality reduction and image compression.

---

## Tools and Technologies

- **Language**: Python 3
- **Libraries**: `numpy`, `pandas`, `matplotlib`, `scikit-learn`, `seaborn`
- **Environment**: Jupyter Notebooks for interactive coding and visualization

---

## Educational Context

This repository was created in the context of exploring core machine learning principles. It draws inspiration from the [INDE577 - Data Science and Machine Learning](https://github.com/RandyRDavila/Data_Science_and_Machine_Learning_Spring_2022) course at Rice University, taught by Professor Randy R. Davila.

---

## Attribution

-  Some explanations and formatting were supported by **ChatGPT**, which was used as a writing and organization aid.
- The original course content and structure inspiration came from [Dr. Randy R. Davila's public GitHub repository](https://github.com/RandyRDavila/Data_Science_and_Machine_Learning_Spring_2022).

---

## Reproducibility

All notebooks are self-contained and designed to be reproducible. Each script includes:
- Data loading steps
- Preprocessing pipelines
- Training and evaluation procedures
- Visualization of results

---

## How to Use

### Clone the Repo

```bash
git clone https://github.com/t0dd26/CMOR438-Spring-2025.git
cd CMOR438-Spring-2025
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Launch Jupyter

```bash
jupyter lab
```

Then open any notebook under `notebooks/`.

