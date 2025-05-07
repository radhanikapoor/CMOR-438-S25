# Random Forests on Insurance Data

This explores the application of **Random Forest** models for both classification and regression tasks using real-world medical insurance data.

Although Random Forests were not covered in class, I implement and evaluate them using built-in methods and my own implelmentation to gain a better understanding of their predictive power.

We focus on:
- Predicting whether an individual is a **smoker** (classification)
- Estimating a person’s **medical charges** (regression)

---

## What is a Random Forest?

A **Random Forest** is an ensemble model that combines the output of multiple **decision trees** to make more accurate and robust predictions.

### Prediction Rules

- **Classification** (Majority Vote):
  $$
  \hat{y}_{\text{clf}} = \arg\max_k \sum_{m=1}^M \mathbf{1}(T_m(x) = k)
  $$

- **Regression** (Averaging):
  $$
  \hat{f}_{\text{reg}}(x) = \frac{1}{M} \sum_{m=1}^M T_m(x)
  $$

### Key Characteristics

- **Bootstrap Aggregation** (Bagging): Each tree is trained on a random subset of the data with replacement.
- **Feature Randomness**: At each split, a random subset of features is considered.
- **Low Bias, Reduced Variance**: By aggregating many decorrelated trees, overfitting is reduced.

---

## Preprocessing and Training

- Categorical variables (`sex`, `region`, `smoker`) were one-hot encoded.
- All features were standardized.
- The dataset was split into training and testing sets.
- We used `RandomForestClassifier` and `RandomForestRegressor` from `scikit-learn`.

---

## Evaluation Metrics

### Classification
- **Accuracy**
- **Confusion Matrix**
- **ROC Curve** and **AUC Score**
- **Feature Importance**

### Regression
- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **R² Score**
- **Partial Dependence Plots (PDPs)** to visualize feature influence

---

## Strengths of Random Forests

- Handles both classification and regression tasks well
- **Resistant to overfitting** due to ensemble averaging
- Can model **nonlinear relationships** and feature interactions
- **Works with both numerical and categorical features**
- Provides **feature importance** scores for model interpretation

---

## Weaknesses of Random Forests

- **Less interpretable** than a single decision tree
- **Large memory footprint** due to storing many trees
- **Slower inference** compared to simpler models
- **Can still overfit** if not properly tuned (e.g., max depth, number of trees)
- **PDPs and feature importance** can be misleading with correlated features

---

## Conclusion

Random Forests are powerful and flexible ensemble methods. In this project, we demonstrated:

- High classification performance for predicting smoker status
- Strong regression capabilities for modeling medical costs
- Useful diagnostics like feature importance and PDPs

Future directions could include hyperparameter tuning, using cross-validation, or comparing with Gradient Boosted Trees.
