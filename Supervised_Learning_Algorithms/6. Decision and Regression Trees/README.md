# Decision and Regression Trees on Insurance Data

This demonstrates how to implement and analyze **Decision Tree** algorithms for both **classification** and **regression** tasks on the medical insurance dataset.

I explore:
- Classification of `smoker` status based on health and demographic features
- Regression of `charges` (medical expenses) using the same inputs

---

## What are Decision Trees?

Decision trees split the input space into axis-aligned regions and make predictions based on the average or most common label within each region.

For any new input $x$, the prediction is:

$$
\hat{f}(x) = \sum_{m=1}^M c_m\,\mathbf{1}(x \in R_m)
$$

Where:
- $R_m$: Region (leaf node)
- $c_m$: Constant prediction in that region

---

## Classification with Decision Trees

### Goal

Predict whether a person is a smoker (`0` or `1`) based on their attributes.

### Key Concepts

- **Gini Impurity**:
  $G = \sum_{k=1}^{K} p_k(1 - p_k)$
  Measures impurity; lower is better.
  
- **Information Gain**: Reduction in impurity after a split.

### Evaluation Metrics

- **Accuracy**
- **Confusion Matrix**
- **ROC Curve** and **AUC**: Assess model performance across thresholds

---

## Regression with Decision Trees

### Goal

Predict continuous `charges` (medical costs) for individuals.

### Key Concepts

- **Piecewise Constant Prediction**: Each region (leaf) returns the **mean** of target values in that region.
- **Mean Squared Error (MSE)** is minimized at each split.

### Evaluation Metrics

- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **R² Score**:
  $R^2 = 1 - \frac{\sum_i (y_i - \hat{y}_i)^2}{\sum_i (y_i - \bar{y})^2}$
  

---

## Bias–Variance Tradeoff

Tree **depth** controls the tradeoff between:
- **Underfitting** (high bias, shallow trees)
- **Overfitting** (high variance, deep trees)

We visualize how model performance changes across depths to identify optimal complexity.

---

## Weaknesses of Decision Trees

Despite their interpretability, decision trees have several limitations:

- **Overfitting**: Deep trees can memorize noise in the training data.
- **High variance**: Small changes in the data can lead to drastically different trees.
- **Axis-aligned splits only**: Cannot capture oblique boundaries unless boosted or randomized.
- **Instability**: Trees are sensitive to feature scaling and irrelevant features.
- **Lower accuracy vs. ensemble models**: Alone, trees usually underperform compared to Random Forests or Gradient Boosted Trees.

---

## Conclusion

Decision Trees are a powerful, interpretable model for both classification and regression. In this project, we demonstrated:
- Implementation of classification and regression trees
- How trees partition the feature space
- Evaluation using confusion matrices, ROC curves, and regression metrics

In practice, decision trees form the backbone of more robust ensemble methods like Random Forests and XGBoost.
