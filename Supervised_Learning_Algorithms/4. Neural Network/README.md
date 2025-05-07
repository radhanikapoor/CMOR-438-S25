# Deep Neural Networks on Medical Cost Dataset

## What is a Neural Network

A neural network algorithm is a type of machine learning algorithm inspired by the structure and function of the human brain. It is designed to recognize patterns and relationships in data through interconnected layers of neurons (also called nodes or units).

### Basic Structure of a Neural Network
Input Layer: Takes in the input features (e.g., age, income, pixels of an image).
Hidden Layers: One or more layers where the data is transformed using weighted connections and activation functions.

Output Layer: Produces the final prediction (e.g., class label, probability, numeric value).

### How It Works
Forward Propagation:
Each neuron computes a weighted sum of its inputs, applies an activation function (like ReLU or sigmoid), and passes it to the next layer.
This continues until the output layer gives a prediction.
Loss Function:
Measures how far the predictions are from the actual values (e.g., mean squared error for regression, cross-entropy for classification).
Backpropagation:
The algorithm calculates the gradient of the loss with respect to each weight using the chain rule of calculus.
It then updates the weights using an optimization method like gradient descent to minimize the loss.

<img src="neural_networks.png" alt="Supervised Learning Image" width="1500"/>

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
