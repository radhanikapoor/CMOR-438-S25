# Ensemble Methods: Bagging and Gradient Boosting on Medical Cost Data

Building on our Decision Tree baseline, we explore two ensemble-based regression models:
- **Bagging Regressor** (Bootstrap Aggregating)
- **Gradient Boosting Regressor**

Both are applied to predict individual medical insurance charges using demographic and health-related features.

---

## Key Concepts

### Bagging (Bootstrap Aggregating)

Bagging reduces variance by training multiple models on **bootstrapped samples** (random samples with replacement) and averaging their predictions:


$\hat{f}_{\mathrm{bag}}(x) = \frac{1}{M} \sum_{m=1}^{M} h_m(x)$


- Each base model $h_m$ is typically a decision tree
- Averaging reduces overfitting

### Gradient Boosting

Gradient Boosting builds models **sequentially**, where each new model fits the residuals (errors) of the combined ensemble so far:

$$
F_0(x) = \bar{y}, \quad F_m(x) = F_{m-1}(x) + \nu h_m(x)
$$

- $h_m(x)$: tree trained on current residuals
- $\nu$: learning rate controls the step size
- Designed to reduce **bias** and improve accuracy

---

## Implementation and Training

- Dataset: Preprocessed `insurance.csv` with encoded categorical variables
- Data split: 60% training / 20% validation / 20% test
- Models: `BaggingRegressor` and `GradientBoostingRegressor` from `sklearn.ensemble`
- Standardized features for better learning behavior

---

## Evaluation Metrics

Models were evaluated on both validation and test sets using:
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **R² Score**
- **Error histograms**
- **Learning curves** to observe underfitting or overfitting behavior
- **Feature importances** and **Partial Dependence Plots (PDPs)** to interpret models

---

## Visual Insights

- **Bagging** tends to yield smoother residuals by reducing variance
- **Boosting** adapts to residual errors more aggressively and often results in better R² scores
- PDPs provide insight into marginal effects of features like `bmi`, `age`, and `smoker`

---

## Weaknesses of Ensemble Methods

While ensemble methods improve predictive performance, they have limitations:

- **Computational cost**: Training multiple trees or sequential learners is resource-intensive
- **Reduced interpretability**: More complex than a single decision tree
- **Overfitting risk**: Especially for Gradient Boosting without proper regularization
- **Sensitive to hyperparameters**: Boosting performance highly depends on learning rate, depth, and number of estimators
- **Longer training time**: Particularly in large datasets or with many iterations

---

## Conclusion

Bagging and Gradient Boosting significantly enhance the performance of decision tree models by reducing variance and bias, respectively. In this project, we:

- Trained both models on real-world insurance data
- Compared their accuracy, learning behavior, and interpretability
- Visualized feature importance and dependencies

Future steps could include:
- Hyperparameter tuning via grid search
- Cross-validation for more robust evaluation
- Trying more advanced variants like XGBoost or HistGradientBoosting
