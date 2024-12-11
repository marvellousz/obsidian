## 1. Overview
Logistic regression is a classification algorithm used to predict the probability of a binary outcome (e.g., 0 or 1, True or False).

### Model Representation
The logistic regression model predicts the probability $P(y=1|x)$ using the **sigmoid function**:
$$
h_\theta(x) = \frac{1}{1 + e^{-\theta^T x}}
$$
Where:
- $x$: Input features (vector).
- $\theta$: Model parameters (vector).
- $h_\theta(x)$: Predicted probability.

---

## 2. Sigmoid Function
The sigmoid function is used to map any real number to a value between 0 and 1.

### Formula
$$
\sigma(z) = \frac{1}{1 + e^{-z}}
$$

### Properties
- $\sigma(z) \to 1$ as $z \to \infty$.
- $\sigma(z) \to 0$ as $z \to -\infty$.
- $\sigma(z) = 0.5$ when $z = 0$.

The sigmoid function ensures the output is interpretable as a probability.

---

## 3. Decision Boundary
The decision boundary is the threshold at which the predicted probability transitions from one class to another.

### Rule
- If $h_\theta(x) \geq 0.5$, predict class 1 ($y=1$).
- If $h_\theta(x) < 0.5$, predict class 0 ($y=0$).

### Decision Boundary in Terms of $z$
The decision boundary corresponds to $z = \theta^T x = 0$. 

### Interpretation
The decision boundary is a hyperplane (line in 2D, plane in 3D, etc.) separating the two classes.

---

## 4. Cost Function for Logistic Regression
The cost function measures the difference between the predicted probabilities and the actual outcomes.

### Loss Function for One Training Example
For a single training example $(x^{(i)}, y^{(i)})$, the loss is:
$$
\text{Loss} = 
\begin{cases} 
-\log(h_\theta(x^{(i)})) & \text{if } y^{(i)} = 1, \\
-\log(1 - h_\theta(x^{(i)})) & \text{if } y^{(i)} = 0.
\end{cases}
$$

### Combined Cost Function
The overall cost function for $m$ examples is:
$$
J(\theta) = -\frac{1}{m} \sum_{i=1}^m \left[ y^{(i)} \log(h_\theta(x^{(i)})) + (1 - y^{(i)}) \log(1 - h_\theta(x^{(i)})) \right]
$$

This formulation ensures:
- A high cost when predictions deviate from actual labels.
- A low cost when predictions align with actual labels.

---

## 5. Gradient Descent for Logistic Regression
Gradient descent is used to minimize the cost function $J(\theta)$ by updating the parameters $\theta$.

### Gradient of the Cost Function
The partial derivative of $J(\theta)$ with respect to $\theta_j$ is:
$$
\frac{\partial J(\theta)}{\partial \theta_j} = \frac{1}{m} \sum_{i=1}^m \left( h_\theta(x^{(i)}) - y^{(i)} \right) x_j^{(i)}
$$

### Update Rule
For each parameter $\theta_j$, update using:
$$
\theta_j := \theta_j - \alpha \frac{\partial J(\theta)}{\partial \theta_j}
$$
Where:
- $\alpha$: Learning rate.
- $\frac{\partial J(\theta)}{\partial \theta_j}$: Gradient of the cost function.

---

## 6. Algorithm for Logistic Regression
1. **Initialize Parameters**:
   - Set $\theta = [0, 0, \dots, 0]$ or small random values.

2. **Iterative Updates**:
   - Compute predictions: $h_\theta(x^{(i)}) = \sigma(\theta^T x^{(i)})$.
   - Compute the gradient: $\frac{1}{m} \sum_{i=1}^m \left( h_\theta(x^{(i)}) - y^{(i)} \right) x_j^{(i)}$.
   - Update $\theta$: $\theta_j := \theta_j - \alpha \frac{\partial J(\theta)}{\partial \theta_j}$.

3. **Stopping Criterion**:
   - Stop if the change in $J(\theta)$ or $\theta$ is below a threshold, or after a fixed number of iterations.

---

## 7. Example
Suppose we have the following data:

| $x_1$ (Hours Studied) | $y$ (Pass/Fail) |
|-----------------------|-----------------|
| 1                     | 0               |
| 2                     | 0               |
| 3                     | 1               |
| 4                     | 1               |

### Steps
1. **Input Matrix**:
   $$
   X = 
   \begin{bmatrix}
   1 & 1 \\
   1 & 2 \\
   1 & 3 \\
   1 & 4 \\
   \end{bmatrix}
   $$

2. **Output Vector**:
   $$
   y = 
   \begin{bmatrix}
   0 \\
   0 \\
   1 \\
   1 \\
   \end{bmatrix}
   $$

3. **Initialize Parameters**:
   $\theta = [0, 0]^T$.

4. **Perform Gradient Descent**:
   - Compute predictions using $h_\theta(x)$.
   - Compute gradients.
   - Update $\theta$.

5. **Final Decision Boundary**:
   - The decision boundary is where $\theta^T x = 0$.

