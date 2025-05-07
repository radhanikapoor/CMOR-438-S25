# Deep Neural Networks on Medical Cost Dataset

This project implements two deep neural networks from scratch using NumPy to tackle real-world tasks on medical insurance data:

1. **Regression** — Predicting the actual medical charges
2. **Classification** — Predicting smoker status (binary label)

Both models are trained using **Stochastic Gradient Descent (SGD)** and evaluated using appropriate metrics.

---

## Part 1: Regression — Predicting Medical Charges

### Problem Overview

- **Goal**: Predict individual medical costs (`charges`) based on features like age, BMI, and smoking status.
- **Type**: Supervised regression
- **Target**: Continuous-valued `charges`

### Preprocessing

- One-hot encoded categorical variables: `sex`, `smoker`, `region`
- Standardized all features (zero mean, unit variance)
- Normalized the target (`charges`) for better training dynamics
- Data split: 60% train, 20% validation, 20% test

### Model Architecture

- **Input layer**: Number of encoded features
- **Hidden layers**: 2 hidden layers, each with 64 neurons and ReLU activation
- **Output layer**: Single neuron with linear activation for regression
- **Weight Initialization**:
  
  $$
  W \sim \mathcal{N}\left(0, \frac{1}{\sqrt{m}}\right)
  $$

### Training Details

- Loss: **Mean Squared Error (MSE)**
- Optimizer: SGD
- Evaluation metrics: MSE, MAE, and R²

---

## Part 2: Classification — Predicting Smoker Status

### Problem Overview

- **Goal**: Classify whether an individual is a smoker
- **Type**: Binary classification
- **Target**: `smoker` (0 = no, 1 = yes)

### Preprocessing

- Used the same encoded and standardized features
- `smoker` column converted to binary labels
- Maintained the same 60/20/20 data split

### Model Architecture

- **Input layer**: Same as regression model
- **Hidden layers**: 2 hidden layers, each with 64 neurons and ReLU activation
- **Output layer**: Single neuron with sigmoid activation

### Training Details

- Loss: **Binary Cross-Entropy**
- Optimizer: SGD
- Evaluation metrics: Accuracy, Precision, Recall, F1 Score

---

## Weaknesses of Neural Networks

While deep neural networks are powerful, they come with limitations:

- **Require large data**: Performance can suffer with small datasets.
- **Computationally expensive**: More intensive than traditional models like logistic regression.
- **Difficult to interpret**: Weights and layers don’t provide intuitive insights like linear coefficients do.
- **Sensitive to hyperparameters**: Learning rate, initialization, and architecture need careful tuning.
- **Risk of overfitting**: Especially when model capacity is high and data is limited.

---

## Conclusion

This project demonstrates how neural networks can be applied to both regression and classification tasks using only NumPy. By building the entire training loop and model architecture from scratch, we gain deeper insight into how deep learning works under the hood.

Future improvements could include:
- Adding regularization (e.g., dropout, L2)
- Using adaptive optimizers like Adam
- Exploring more complex architectures or activation functions
