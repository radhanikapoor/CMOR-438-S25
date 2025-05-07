# Supervised Learning Module

## What is Supervised Learning?

Supervised learning is a type of machine learning where the algorithm is trained on labeled data—that is, input-output pairs where the correct output (label) is known. The goal is to learn a function that maps inputs to outputs, enabling accurate prediction on new, unseen data.

Supervised learning tasks are generally divided into:
- Regression: Predicting continuous values 
- Classification: Predicting discrete categories 

<img src="supervised_learning.png" alt="Supervised Learning Image" width="1500"/>

---

## Algorithms Implemented

### 1. Linear Regression
- Type: Regression
- Description: Fits a straight line to minimize the mean squared error. Used to predict continuous values based on input features.
- Dataset Used: `insurance.csv`

### 2. Logistic Regression
- Type: Classification
- Description: Predicts binary outcomes using the sigmoid function. Used in scenarios like spam detection or medical diagnoses.
- Dataset Used: `insurance.csv`

### 3. Perceptron
- Type: Binary Classification
- Description: One of the earliest neural models, it classifies data by learning a linear decision boundary.
- Dataset Used: `spotify_dataset.csv` and `insurance.csv`

### 4. Neural Networks
- Type: Classification
- Description: A simple multi-layer perceptron (MLP) implemented from scratch using gradient descent.
- Dataset Used: `insurance.csv`

### 5. K-Nearest Neighbors (KNN)
- Type: Classification
- Description: A non-parametric method that classifies a point based on the majority label among its k-nearest neighbors.
- Dataset Used: `insurance.csv`

### 6. Decision Trees
- Type: Classification and Regression
- Description: Builds a tree by recursively splitting the data based on feature thresholds. Works for both tasks.
- Dataset Used: `insurance.csv`

### 7. Random Forests
- Type: Classification
- Description: An ensemble of decision trees that improves accuracy through bagging and randomness.
- Dataset Used: `insurance.csv`

### 8. Ensemble Methods
- Type: Classification
- Description: Combines predictions from multiple models (e.g., AdaBoost, Bagging) to improve performance.
- Dataset Used: `insurance.csv`

---

## Datasets

| Dataset               | Description                                      | Used For                   |
|-----------------------|--------------------------------------------------|----------------------------|
| `insurance.csv`       | U.S. medical insurance data                      | Regression & Classification |


### `insurance.csv`

This dataset contains information about individuals’ medical charges billed by U.S. insurance companies. It is commonly used for regression (predicting medical costs) or binary classification (e.g., predicting high vs. low cost).

**Columns:**

- `age`: Age of the individual (integer)
- `sex`: Gender of the individual (`male`, `female`)
- `bmi`: Body mass index (float)
- `children`: Number of children covered by health insurance (integer)
- `smoker`: Whether the individual is a smoker (`yes`, `no`)
- `region`: Geographic region of residence in the U.S. (`northeast`, `southeast`, `southwest`, `northwest`)
- `charges`: Total medical charges billed (float) — *target for regression*


> **Note**: All datasets are stored in the `Datasets/` folder at the root of the project. When loading data from a notebook, use relative paths like `../Datasets/insurance.csv` depending on your folder structure.


---

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

- `Linear_Regression.ipynb`
- `Logistic_Regression.ipynb`
- `perceptron.ipynb`
- `Neural_Networks.ipynb`
- `KNN.ipynb`
- `Decision_and_Regression_Trees.ipynb`
- `Random_Forests.ipynb`
- `Ensemble methods.ipynb`

---

## Notes

- All code is written in Python 3 using Jupyter Notebooks.
- Each notebook includes detailed explanations, visualizations, and performance metrics.
- Ensure both `insurance.csv` and `spotify_dataset.csv` are in the same directory as the notebooks, or adjust the file path accordingly.
- Ensure both `insurance.csv` and `spotify_dataset.csv` are in the same directory as the notebooks, or adjust the file path accordingly.

