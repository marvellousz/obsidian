## 1. Feature Engineering

Feature engineering involves transforming raw data into meaningful inputs that improve the performance of a machine learning model.

### Key Techniques

1. **Scaling**:
   - Use **Normalization** (scaling features to a [0, 1] range) or **Standardization** (scaling to zero mean and unit variance).
   - Example: 
     $$x' = \frac{x - \mu}{\sigma}$$
     where $\mu$ is the mean and $\sigma$ is the standard deviation.

2. **Encoding Categorical Variables**:
   - Use **one-hot encoding** for nominal categories.
   - Example:
     - `Gender: Male/Female` → `Gender_Male, Gender_Female`.

3. **Feature Selection**:
   - Remove irrelevant or redundant features (e.g., through correlation analysis, variance thresholding).

4. **Feature Transformation**:
   - Apply transformations like logarithms, square roots, or exponential functions for skewed data.

5. **Handling Missing Values**:
   - Use imputation methods like filling with mean, median, or a placeholder value.

---

## 2. Checking Gradient Descent for Convergence

Gradient descent convergence ensures the cost function $J(w)$ is minimized properly.

### Monitoring Convergence

1. **Cost Function Plot**:
   - Plot $J(w)$ vs. the number of iterations. If the cost decreases smoothly and levels off, convergence is achieved.

2. **Gradient Norm**:
   - Compute the gradient's magnitude $\|\nabla J(w)\|$. If it becomes very small (below a threshold like $10^{-6}$), gradient descent is near convergence.

3. **Stopping Criteria**:
   - Stop if the relative change in $J(w)$ between iterations is below a certain threshold:
     $$\text{If } \frac{|J(w^{(i)}) - J(w^{(i-1)})|}{J(w^{(i-1)})} < \epsilon, \text{ stop}.$$

### Common Issues

1. **Divergence**:
   - If $J(w)$ increases, the learning rate is likely too high.
2. **Slow Convergence**:
   - If $J(w)$ decreases very slowly, the learning rate is too low.

---

## 3. Choosing the Learning Rate

The learning rate $\alpha$ controls the step size in gradient descent.

### Guidelines

1. **Experimentation**:
   - Start with a small $\alpha$ (e.g., $0.01$) and adjust based on the cost function's behavior.

2. **Visualization**:
   - Plot $J(w)$ over iterations to ensure steady convergence.

3. **Adaptive Learning Rates**:
   - Techniques like **Learning Rate Decay** reduce $\alpha$ over time:
     $$\alpha_t = \frac{\alpha_0}{1 + k \cdot t}$$
     where $t$ is the current iteration, $\alpha_0$ is the initial learning rate, and $k$ is a decay factor.

### Best Practices

- Use libraries like Adam or RMSProp optimizers, which adjust learning rates dynamically.

---

## 4. Polynomial Regression

Polynomial regression extends linear regression by modeling non-linear relationships.

### Model Representation

For a polynomial of degree $d$:
$$y = w_0 + w_1x + w_2x^2 + \dots + w_dx^d$$

### Steps for Polynomial Regression

1. **Feature Transformation**:
   - Expand the input features to include polynomial terms (e.g., $x^2, x^3, \dots$).

2. **Fit a Linear Model**:
   - Use the transformed features in a linear regression framework:
     $$\hat{y} = X' \cdot w$$
     where $X'$ includes $x, x^2, \dots, x^d$.

3. **Regularization** (optional):
   - Use techniques like Ridge or Lasso regression to prevent overfitting.

### Example

Given data points $(x, y)$:
- $x = [1, 2, 3]$
- $y = [2, 6, 12]$

Transform $x$ into polynomial features:
$$X' = \begin{bmatrix} 1 & 1 & 1^2 \\ 1 & 2 & 2^2 \\ 1 & 3 & 3^2 \end{bmatrix}$$

Fit a linear regression model to $X'$ and $y$.

---

## 5. Feature Engineering for Polynomial Regression

Feature engineering is crucial for polynomial regression to balance complexity and generalization.

### Techniques

1. **Degree Selection**:
   - Use cross-validation to choose the optimal degree of the polynomial.

2. **Interaction Terms**:
   - Include combinations of features (e.g., $x_1 \cdot x_2$) for better modeling.

3. **Normalization**:
   - Scale polynomial features to prevent large magnitude differences.

4. **Regularization**:
   - Apply Ridge or Lasso regression to penalize large coefficients.
