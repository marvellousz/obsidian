## Model Representation
The equation for multiple linear regression is:

$y = w_0 + w_1 x_1 + w_2 x_2 + \dots + w_n x_n$

Or, in vectorized form:

$\hat{y} = X \cdot w$

Where:
- $\hat{y}$: Predicted output (vector of predictions for all examples).
- $X$: Input matrix ($m \times (n+1)$) where $m$ is the number of examples and $n$ is the number of features. The first column of $X$ is typically filled with ones to account for $w_0$ (the intercept).
- $w$: Weight vector ($(n+1) \times 1$), where $w_0$ is the intercept term and $w_1, w_2, \dots, w_n$ are the weights for the features.

---

## Vectorization
Vectorization allows efficient computation by using matrix operations, avoiding explicit loops.

### Key Matrix Operations
1. **Predictions**:
   $\hat{y} = X \cdot w$

2. **Error**:
   $\text{Error} = \hat{y} - y$

3. **Cost Function (Mean Squared Error)**:
   $J(w) = \frac{1}{2m} \cdot (X \cdot w - y)^T \cdot (X \cdot w - y)$

4. **Gradient Calculation**:
   $\nabla J(w) = \frac{1}{m} \cdot X^T \cdot (X \cdot w - y)$

---

## Gradient Descent for Multiple Linear Regression
Gradient descent is used to minimize the cost function by iteratively updating the weights.

### Update Rule
For each iteration:

$w := w - \alpha \cdot \nabla J(w)$

Where:
- $w$: Weight vector ($(n+1) \times 1$).
- $\alpha$: Learning rate (step size).
- $\nabla J(w)$: Gradient of the cost function:
  $\nabla J(w) = \frac{1}{m} \cdot X^T \cdot (X \cdot w - y)$

---

## Gradient Descent Algorithm
1. **Initialize Weights**:
   - Set all weights $w$ to small random values or zero.

2. **Iterative Updates**:
   - Compute predictions: $\hat{y} = X \cdot w$.
   - Compute the gradient: $\nabla J(w) = \frac{1}{m} \cdot X^T \cdot (X \cdot w - y)$.
   - Update weights: $w := w - \alpha \cdot \nabla J(w)$.

3. **Convergence**:
   - Stop when the change in cost function $J(w)$ or weights $w$ is smaller than a predefined threshold, or after a fixed number of iterations.

---

## Example
Suppose you have the following data:

| $x_1$ (Hours Studied) | $x_2$ (Sleep Hours) | $y$ (Score) |
|-----------------------|---------------------|-------------|
| 1                     | 8                   | 50          |
| 2                     | 7                   | 60          |
| 3                     | 6                   | 65          |
| 4                     | 5                   | 70          |

### Step 1: Prepare Matrices
- Input Matrix $X$ (add a bias column of 1s):
  $$
  X = 
  \begin{bmatrix}
  1 & 1 & 8 \\
  1 & 2 & 7 \\
  1 & 3 & 6 \\
  1 & 4 & 5 \\
  \end{bmatrix}
  $$

- Output Vector $y$:
  $$
  y = 
  \begin{bmatrix}
  50 \\
  60 \\
  65 \\
  70 \\
  \end{bmatrix}
  $$

### Step 2: Initialize Weights
$$
w = 
\begin{bmatrix}
w_0 \\
w_1 \\
w_2 \\
\end{bmatrix}
$$
Start with $w = [0, 0, 0]^T$.

### Step 3: Gradient Descent
- Compute $\hat{y} = X \cdot w$.
- Compute gradient: $\nabla J(w) = \frac{1}{m} \cdot X^T \cdot (X \cdot w - y)$.
- Update $w$ using the gradient descent rule.

---

## Advantages of Vectorization
1. **Efficiency**:
   - Matrix operations are highly optimized in libraries like NumPy.

2. **Simplicity**:
   - Compact representation reduces code complexity.

3. **Scalability**:
   - Handles large datasets more effectively than loops.

