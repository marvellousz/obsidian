
## What is Machine Learning?

Machine Learning (ML) is the field of building systems that **learn patterns from data** and use those patterns to make predictions or decisions.

### Types of Machine Learning

**1. Supervised Learning**

Learning from labeled data.

- **Regression** → Predict continuous values  
    Example: house price prediction
    
- **Classification** → Predict categories  
    Example: spam detection
    

**2. Unsupervised Learning**

Learning patterns from unlabeled data.

- **Clustering** → Group similar data
    
- **Anomaly Detection** → Detect unusual data points
    
- **Dimensionality Reduction** → Reduce number of features
    

---

## Tools

### Jupyter Notebooks

Interactive environment used for:

- Writing Python code
    
- Running experiments
    
- Visualizing results
    
- Documenting ML workflows
    

---

# Linear Regression

Linear regression tries to fit a **straight line** to data.

```
y = mx + b
```

Where:

- `m` = slope
    
- `b` = intercept
    
- `x` = input feature
    
- `y` = predicted output
    

---

## Cost Function (Loss Function)

Measures **how wrong the model predictions are**.

The most common loss for regression is:

### Mean Squared Error (MSE)

```
MSE = (1/n) Σ (y_actual − y_predicted)^2
```

The goal of training is to **minimize this error**.

---

## Gradient Descent

A method used to **find the best parameters (m and b)** by minimizing the cost function.

Idea:

> Imagine standing on a hill (high error) and walking downhill to reach the lowest point (minimum error).

At each step:

- Compute the slope of the error surface
    
- Move in the direction that reduces error the most
    

---

## Residuals

Residuals measure prediction error.

```
Residual = Actual Value − Predicted Value
```

Residual analysis helps understand **model performance**.

---

## R² Score (Coefficient of Determination)

Measures **how well the regression line fits the data**.

```
R² = 1 − (Model Error / Error of Predicting Mean)
```

Interpretation:

|Value|Meaning|
|---|---|
|1|Perfect fit|
|0|Model is useless|
|< 0|Worse than predicting average|

---

## Learning Rate

Controls **how big the steps are during gradient descent**.

- Too small → very slow training
    
- Too large → overshoot or divergence
    
- Just right → fast and stable convergence
    

---

# Multiple Linear Regression

Uses **multiple features** to predict output.

```
y = w1x1 + w2x2 + ... + wnxn + b
```

### Why Multiple Features?

Real-world predictions depend on **multiple factors**, not just one.

Example:

House price depends on:

- area
    
- number of rooms
    
- location
    
- age of building
    

---

## Vectorization

Vectorization means performing operations on **entire arrays at once instead of loops**.

Example using NumPy:

```
np.dot(X, W)
```

Benefits:

- Much faster computation
    
- Efficient gradient descent
    
- Cleaner code
    

> Modern ML = Matrix Math

---

## Feature Scaling

Adjusting input features so they are on a **similar scale**.

Why?

If features have very different scales, gradient descent becomes slow.

### Common Methods

**1. Z-score Normalization**

```
x' = (x − μ) / σ
```

**2. Min-Max Scaling**

```
x' = (x − min) / (max − min)
```

---

## Convergence in Gradient Descent

Convergence means **training has stabilized**.

Signs:

- Cost function stops decreasing
    
- Gradient becomes very small
    
- Weights stop changing
    
- Maximum iterations reached
    

### Faster Convergence

- Feature scaling
    
- Good learning rate
    
- Vectorization
    
- Proper initialization
    

---

## Feature Engineering

Feature engineering is the process of:

- Creating new features
    
- Improving existing features
    
- Selecting important features
    

Good features → simple models perform well.

Bad features → even complex models fail.

---

## Polynomial Regression

Adds polynomial terms to capture **curved relationships**.

Example:

Linear model:

```
y = w1x + b
```

Polynomial model:

```
y = w1x + w2x² + b
```

---

# Classification

Classification predicts **categories instead of numbers**.

---

## Logistic Regression

Despite the name, it is a **classification algorithm**.

Uses the **sigmoid function**:

```
σ(z) = 1 / (1 + e^-z)
```

Output range:

```
0 → 1
```

Interpreted as probability.

---

## Cost Function

Instead of MSE, logistic regression uses:

### Binary Cross Entropy (BCE)

```
Loss = − [ y log(p) + (1−y) log(1−p) ]
```

---

## Decision Boundary

The boundary that separates classes.

Example:

```
w1x1 + w2x2 + b = 0
```

At this point:

```
P(y=1) = 0.5
```

---

## Overfitting

Occurs when the model **memorizes training data instead of learning patterns**.

Symptoms:

- Very good training accuracy
    
- Poor performance on new data
    

### Model Behavior Spectrum

```
Underfitting → Good Fit → Overfitting
```

### Causes

- Model too complex
    
- Too many features
    
- Too little training data
    
- Training too long
    
- No regularization
    
- Noisy data
    

---

## Regularization

Adds a **penalty term to the cost function** to prevent overfitting.

### Types

**L2 Regularization (Ridge)**  
Penalizes large weights.

**L1 Regularization (Lasso)**  
Pushes some weights to zero (feature selection).

**Elastic Net**  
Combination of L1 and L2.

---

# Neural Networks

Neural networks were inspired by the **human brain**.

They consist of many logistic-like units stacked together with nonlinear activations.

---

## Structure

### Layers

- **Input Layer**
    
- **Hidden Layers**
    
- **Output Layer**
    

### Output Activation

|Task|Activation|
|---|---|
|Binary classification|Sigmoid|
|Multiclass classification|SoftMax|
|Regression|Linear|

---

## Forward Propagation

Process where:

1. Inputs pass through the network
    
2. Each layer applies weights, bias, and activation
    
3. Output prediction is produced
    

---

## Activation Functions

Common activations:

- **Sigmoid**
    
- **ReLU**
    
- **Tanh**
    
- **SoftMax**
    

---

## Loss Functions

|Task|Loss|
|---|---|
|Regression|Mean Squared Error|
|Binary classification|Binary Cross Entropy|
|Multiclass classification|Cross Entropy|

---

## Backpropagation

Algorithm used to **update weights in neural networks**.

Steps:

1. Compute prediction
    
2. Calculate loss
    
3. Propagate error backwards
    
4. Update weights using gradient descent
    

---

## Common Neural Network Types

### Feedforward Networks (MLP)

Basic fully connected neural networks.

### Convolutional Neural Networks (CNN)

Best for:

- Image recognition
    
- Computer vision
    

### Recurrent Neural Networks (RNN)

Best for sequential data:

- text
    
- speech
    
- time series
    

Variants:

- LSTM
    
- GRU
    

### Transformers

Modern state-of-the-art architecture used in:

- LLMs
    
- NLP
    
- Vision
    

### Autoencoders

Used for:

- dimensionality reduction
    
- compression
    
- anomaly detection
    

### GANs (Generative Adversarial Networks)

Used for generating:

- images
    
- videos
    
- audio
    

---

## Neural Network Learning Process

Each neuron:

1. Takes input
    
2. Multiplies by weights
    
3. Adds bias
    
4. Applies activation
    
5. Sends output to next layer
    

Training loop:

```
Forward Pass
→ Compute Loss
→ Backpropagation
→ Update Weights
→ Repeat
```

Until convergence.

---

# Model Evaluation

## Dataset Splitting

Data is usually divided into:

|Set|Purpose|
|---|---|
|Training set|Train the model|
|Validation set|Tune hyperparameters|
|Test set|Final evaluation|

---

## Bias vs Variance

**High Bias → Underfitting**

- Model too simple
    
- Cannot capture patterns
    

**High Variance → Overfitting**

- Model too complex
    
- Memorizes training data
    

---

## Precision and Recall

Used in classification evaluation.

**Precision**

```
TP / (TP + FP)
```

Measures correctness of positive predictions.

**Recall**

```
TP / (TP + FN)
```

Measures how many positives were correctly detected.

---

# Decision Trees

Decision trees split data using **feature-based rules**.

Example:

```
Is Age > 30?
```

Used for:

- classification
    
- regression
    

---

## Random Forest

Ensemble of many decision trees.

Idea:

```
Train many trees → average predictions
```

Benefits:

- reduces overfitting
    
- improves stability
    

---

## XGBoost

Extreme Gradient Boosting.

A powerful boosting algorithm that:

- builds trees sequentially
    
- corrects previous errors
    
- achieves state-of-the-art performance in many problems
    

---

# Clustering

A form of **unsupervised learning**.

Goal: group similar data points.

---

## K-Means Clustering

Groups data using **centroids**.

Algorithm:

1. Choose K centroids
    
2. Assign points to nearest centroid
    
3. Recalculate centroids
    
4. Repeat
    

Optimization metric:

### Within Cluster Sum of Squares (WCSS)

Measures compactness of clusters.

---

# Anomaly Detection

Detects unusual or rare data points.

Often uses **Gaussian distribution**.

---

## Gaussian Distribution

Normal distribution defined by:

- mean (μ)
    
- variance (σ²)
    

Used to estimate probability of a data point.

---

## Anomaly Detection vs Supervised Learning

Use **anomaly detection** when:

- very few positive examples
    
- many normal examples
    
- anomalies are hard to label
    

Use **supervised learning** when:

- plenty of labeled positive and negative data exists
    

---

# Recommender Systems

Goal:

Predict what a **user will like**.

Uses:

- user history
    
- similar users
    
- similar items
    

---

## Item Feature Representation

Each item can be represented as a **feature vector**.

Example for movies:

```
[Action, Romance, Comedy, Drama]
```

---

## Types of Recommender Systems

### Content-Based Filtering

Recommend items **similar to what the user liked before**.

Example:

If you like action movies → recommend more action movies.

---

### Collaborative Filtering

Recommend items liked by **similar users**.

Example:

Users with similar tastes often like the same movies.

---

# Reinforcement Learning

Learning by **interacting with an environment**.

Agent learns by:

- taking actions
    
- receiving rewards
    
- improving its policy over time
    

Examples:

- robotics
    
- game playing
    
- recommendation systems
    
- autonomous driving
    

---

# Quick Recap

Machine Learning = learning patterns from data.

- **Supervised Learning** → regression, classification
    
- **Unsupervised Learning** → clustering, anomaly detection
    
- **Linear Regression** → line minimizing MSE
    
- **Gradient Descent** → optimize weights
    
- **Feature Scaling** → faster convergence
    
- **Logistic Regression** → sigmoid + cross entropy
    
- **Regularization** → prevents overfitting
    
- **Neural Networks** → layers + activations + backprop
    
- **Model Evaluation** → train / validation / test
    
- **Tree Methods** → decision trees, random forests, XGBoost
    
- **Clustering** → K-means
    
- **Anomaly Detection** → Gaussian probability
    
- **Recommenders** → content-based vs collaborative
    

