### **Linear Regression:**

Linear regression is a simple, foundational algorithm in machine learning used to model the relationship between one or more input features (independent variables) and a continuous output variable (dependent variable). In simple linear regression, the relationship is modeled by a straight line.

### **Model Representation**:

The model assumes that the dependent variable y is a linear function of the independent variable xx:

$y= w_0 + w_1 x + \epsilon$

Where:

- $y$ is the predicted output (target variable).
- $x$ is the input feature (independent variable).
- $w_0$ is the bias term (intercept).
- $w1$ is the weight (slope) for the input feature xx.
- $ϵ$ is the error term (the difference between the predicted and actual values).

For multiple features, the model extends to:

$y= w_0 + w_1 x_1 + w_2 x_2 + \dots + w_n x_n$

Where $x_1,x_2,…,x_n$ are multiple features, and $w_1,w_2,…,w_n$ are their corresponding weights.

### **Cost Function:**

In machine learning, the goal is to minimize the difference between the model's predictions and the actual values. This difference is quantified using a **cost function**.

The most common cost function for linear regression is the **Mean Squared Error (MSE)**, defined as:

$J(w_0,w_1,…,w_n)= \frac{1}{2m} \sum_{i=1}^{m} \left( \hat{y}_i - y_i \right)^2$

Where:

- $m$ is the number of training examples.
- $\hat{y}_i$ is the predicted value for the $i-th$ example.
- $y_i$ is the actual value for the $i-th$ example.
- $\hat{y}_i= w_0 + w_1 x_1 + w_2 x_2 + \dots + w_n x_n$ (the predicted output for the $i-th$ example).

### **Why the MSE Cost Function?**

The MSE calculates the average squared difference between the predicted and actual values. The goal of the algorithm is to find the weights $w_0,w_1,…,w_n$ that minimize this error, thus making the model's predictions as close as possible to the true values.

- Squaring ensures that large errors are penalized more than smaller ones.
- The term $\frac{1}{2m}$ normalizes the sum and simplifies the derivative calculations during optimization.

---

### **Intuition Behind the Cost Function:**

1. **Prediction Error**:
    
    - For each data point, the model predicts $\hat{y}_i$, but the actual value is $y_i$. The difference between the predicted and actual values is called the **error** $(\hat{y}_i - y_i)$.
2. **Squaring the Error**:
    
    - Squaring the error ensures that both positive and negative errors are treated equally and gives higher weight to larger errors.
3. **Summing the Errors**:
    
    - Summing over all data points gives the total error for the whole dataset.
4. **Minimizing the Cost**:
    
    - The goal of linear regression is to adjust the weights $w_0,w_1,…,w_n$ so that the total error (cost function) is minimized, leading to the best-fit line.
5. **Gradient Descent**:
    
    - Gradient descent is typically used to minimize the cost function. It adjusts the weights iteratively by taking steps proportional to the negative gradient of the cost function with respect to the weights.

---

### **Gradient Descent Update Rule:**

The gradient descent update rule for each weight $w_j$ is given by:

$w_j:= w_j - \alpha \frac{\partial J(w_0, w_1, \dots, w_n)}{\partial w_j}$

Where:

- $α$ is the learning rate (step size).
- $\frac{\partial J(w_0, w_1, \dots, w_n)}{\partial w_j}$ is the partial derivative of the cost function with respect to $w_j$, which tells us how much the cost function changes as $w_j$ changes.

---

### **Intuition of Linear Regression**:

1. **Finding the Best Fit Line**:
    - Imagine you have a scatter plot of data points. The goal is to draw a straight line that best represents the relationship between the input and the output.
2. **Minimizing the Cost**:
    - The "best" line is the one where the sum of squared errors (distance from each point to the line) is minimized. This is the line that fits the data most closely.
3. **Optimization**:
    - The weights $w_0$ and $w_1$ are adjusted so that the line minimizes the distance to the points (or the cost function).

---

### **Example Calculation**:

Suppose you have the following data points for a simple linear regression problem:

|x (Input)|y (Output)|
|---|---|
|1|2|
|2|3|
|3|4|
|4|5|

The linear regression model aims to fit a line of the form:

$y=w_0 + w_1 x$

To find the best-fit line, you would:

1. Calculate the predicted values $\hat{y}_i$ for each input.
2. Calculate the error for each data point.
3. Use the cost function (MSE) to evaluate how well the model fits.
4. Adjust the weights $w_0$ and $w_1$ using gradient descent or other optimization methods to minimize the MSE.
