## Introduction

This project demonstrates how to implement and analyze linear regression models using a real-world dataset: **medical insurance charges**. The objective is to predict a person’s medical expenses (`charges`) based on demographic and health-related features such as `age`, `bmi`, and `smoker` status.

---

## What is Linear Regression?

Linear regression models the relationship between a dependent variable \( y \) and one or more independent variables \( X \). The model assumes a linear combination of input features can predict the outcome:

$$
\hat{y} = \mathbf{w}^\top \mathbf{x} + b
$$

Where:
- $ \mathbf{x} $ is the feature vector
- $ \mathbf{w} $ is the weight vector
- $ b $ is the bias (intercept)

---

## Implementation Overview

We implemented three approaches to linear regression:

1. **Closed-Form Solution** (Normal Equation):
   - Solves \( \mathbf{w} = (X^\top X)^{-1} X^\top y \)
   - Efficient for small datasets with a guaranteed solution

2. **Gradient Descent**:
   - Iteratively updates weights to minimize Mean Squared Error (MSE)
   - Useful for large-scale or high-dimensional problems

3. **scikit-learn** (`LinearRegression`):
   - A standard library method used for benchmarking

---

## Performance Metrics

We evaluate model accuracy using:
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **R²** Score (Coefficient of Determination)

These metrics assess the prediction error and explanatory power of the models.

---

## Residual Analysis

Residuals (actual - predicted) are plotted to assess model fit. Patterns in residuals may indicate:
- Non-linearity
- Heteroscedasticity
- Missing variables

A good linear model should have **residuals randomly scattered around zero**.

---

## Coefficient Interpretation

Each coefficient represents the **expected change in charges** for a one-unit increase in the corresponding feature, holding other variables constant.

High-magnitude coefficients (e.g., `smoker`) reflect features with stronger influence on charges.

---

## Weaknesses of Linear Regression

Despite its simplicity and interpretability, linear regression has several limitations:

- **Assumes linearity**: It fails to capture non-linear relationships between variables.
- **Sensitive to outliers**: Extreme values can disproportionately affect the model fit.
- **Multicollinearity**: When features are highly correlated, coefficient estimates become unstable.
- **No feature interactions**: Basic linear regression does not account for interaction effects between variables.
- **Assumes homoscedasticity**: The variance of residuals should be constant, which is often not true in real data.

These limitations highlight the importance of diagnostic checks and, when needed, using more flexible models like polynomial regression or regularized methods.

---

## Conclusion

Linear regression is a powerful yet interpretable model for regression tasks. In this project, we showed:
- How to preprocess real-world data
- How different linear regression methods compare
- The importance of residuals and coefficient interpretation

This foundation can be extended to more complex models such as regularized regression or non-linear approaches.
