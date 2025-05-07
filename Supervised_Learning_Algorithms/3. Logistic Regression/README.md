# Logistic Regression: Classification with Real-World Data

This project demonstrates how to implement and evaluate logistic regression using a real-world dataset: predicting whether a person has high medical costs based on features like age, BMI, and smoking status. The objective is to classify individuals into binary outcomes: high cost (1) vs. not high cost (0).

## What is Logistic Regression?

Logistic regression is a statistical model used for binary classification. Unlike linear regression, which predicts continuous values, logistic regression predicts the probability that a given input belongs to a particular class:

$$
\hat{y} = \sigma(\mathbf{w}^\top \mathbf{x} + b)
$$

Where:

- $\mathbf{x}$ is the feature vector  
- $\mathbf{w}$ is the weight vector  
- $b$ is the bias term  
- $\sigma(z) = \frac{1}{1 + e^{-z}}$ is the sigmoid function, which maps real-valued inputs to probabilities in [0, 1]

## Implementation Overview

We implemented logistic regression using three approaches:

### 1. Manual Gradient Descent:

- Computes the gradient of the binary cross-entropy loss  
- Iteratively updates weights using learning rate and gradient  
- Offers insights into model internals and optimization dynamics

### 2. scikit-learn (LogisticRegression):

- Standard and optimized implementation  
- Useful for benchmarking and validation  

## Performance Metrics

To evaluate classification performance, we used:

- **Accuracy**: Proportion of correct predictions  
- **Precision**: True positives / (true positives + false positives)  
- **Recall**: True positives / (true positives + false negatives)  
- **F1 Score**: Harmonic mean of precision and recall  
- **Confusion Matrix**: Shows the breakdown of true/false positives/negatives

These metrics assess the model’s effectiveness in distinguishing between classes.

## Decision Boundary Visualization

We plotted the decision boundary in 2D feature space to visualize the classifier’s learned separation between classes. This helps assess model behavior and identify potential misclassifications.

## Coefficient Interpretation

Each coefficient reflects the log-odds change in the predicted probability of the positive class given a one-unit increase in the corresponding feature, holding others constant.

- Positive coefficients increase the likelihood of the positive class  
- Larger magnitude indicates stronger influence

## Weaknesses of Logistic Regression

Despite its strengths, logistic regression has several limitations:

- **Linear decision boundary**: Cannot model complex nonlinear relationships  
- **Feature scaling needed**: Gradient descent can converge slowly without normalization  
- **Imbalanced data**: Performs poorly when one class dominates  
- **Multicollinearity**: Like linear regression, suffers from unstable coefficients  
- **Assumes independence**: Between features, which may not hold in real-world data

These limitations can be mitigated through preprocessing, feature engineering, or using more flexible models like decision trees or neural networks.

## Conclusion

Logistic regression is a powerful and interpretable model for binary classification tasks. In this project, we explored:

- Manual and library-based implementations  
- How to evaluate classification performance  
- The role of coefficients and decision boundaries  

This foundation supports extension to multi-class classification and regularized logistic regression for improved generalization.

