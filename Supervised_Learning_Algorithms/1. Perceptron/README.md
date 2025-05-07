# Introduction

In this overview, we describe and analyze the **Perceptron** — one of the earliest and simplest algorithms in machine learning used for **binary classification**.

This is a **supervised learning algorithm**, meaning it learns from labeled input-output pairs to predict a binary outcome (e.g., "yes" or "no", "spam" or "not spam").

---

## What is the Perceptron?

The **Perceptron** models a decision boundary by:
- Computing a **weighted sum** of the input features
- Applying a **step function** to classify the input as either 0 or 1
- Iteratively **updating weights** whenever it makes an incorrect prediction

### Mathematical Formulation

Given input vector **x**, weight vector **w**, and bias **b**, the perceptron predicts:

$$
\hat{y} = 
\begin{cases}
1 & \text{if } \mathbf{w}^\top \mathbf{x} + b \geq 0 \\\\
0 & \text{otherwise}
\end{cases}
$$

### Learning Rule

The Perceptron updates its weights using the following rule for each training example:

$$
\mathbf{w} \leftarrow \mathbf{w} + \eta (y - \hat{y}) \mathbf{x}
$$

$$
b \leftarrow b + \eta (y - \hat{y})
$$

Where:
- \( \eta \) is the **learning rate**
- \( y \) is the true label
- \( \hat{y} \) is the predicted label

---

## Strengths and Limitations

### Pros:
- Simple and fast to implement
- Effective for linearly separable data
- Forms the foundation for more advanced models like neural networks

### Cons:
- Cannot solve non-linearly separable problems (e.g., XOR)
- Sensitive to feature scaling and learning rate
- Convergence is not guaranteed for noisy data

---

## Use Cases

The Perceptron is best used for:
- Educational purposes to understand the foundation of neural networks
- Simple binary classification tasks with linearly separable data

---

## Conclusion

The **Perceptron algorithm** is a foundational tool in machine learning, demonstrating how models can learn from data using weight updates. While it's limited in scope, understanding how it works provides essential insight into more complex models like multilayer neural networks.

