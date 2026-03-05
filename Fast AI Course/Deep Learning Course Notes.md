
# 1. Getting Started

This section introduces the **basic concepts of deep learning**.

Focus:

- Overview of machine learning and deep learning
    
- Basic terminology
    
- High-level understanding of how models learn
    

It mainly covers **foundational ideas rather than advanced techniques**.

---

# 2. Deployment

This section covers **how machine learning projects are deployed**.

## ML Project Cycle

Typical workflow:

1. Collect data
    
2. Train model
    
3. Evaluate model
    
4. Deploy model
    
5. Monitor and improve
    

---

## Deployment Tools

### Gradio

A Python library used to quickly create **interactive interfaces for ML models**.

Example uses:

- Demo ML models
    
- Share experiments
    
- Build simple web interfaces
    

---

### Streamlit

Another tool for creating **ML dashboards and apps** with minimal code.

Common use cases:

- Model visualization
    
- Data exploration
    
- Interactive ML apps
    

---

### Hugging Face Spaces

A platform used to **host ML demos online**.

Supports:

- Gradio apps
    
- Streamlit apps
    
- ML model demos
    

Useful for sharing projects publicly.

---

# 3. Neural Network Foundations

## Linear Functions

A linear function looks like:

```
y = wx + b
```

However, **stacking linear functions does not increase model power**.

Example:

```
Linear → Linear → Linear = still Linear
```

This means the model **cannot learn complex patterns**.

---

## Non-Linear Activation Functions

Non-linear activations solve this limitation.

They allow neural networks to **approximate complex functions**.

Common activation functions:

- **Sigmoid**
    
- **Tanh**
    
- **ReLU** (most commonly used)
    

---

### ReLU (Rectified Linear Unit)

```
ReLU(x) = max(0, x)
```

Behavior:

- If `x < 0` → output = 0
    
- If `x ≥ 0` → output = x
    

Benefits:

- Simple
    
- Efficient
    
- Helps deep networks learn complex patterns
    

---

## Core Components of Deep Learning

Deep learning models mainly use:

- **Linear layers**
    
- **Non-linear activation functions**
    
- **Gradient-based optimization**
    

---

## Gradient Descent

Gradient descent is used to **update model weights** to reduce error.

### Standard Gradient Descent

Uses the **entire dataset** to compute gradients.

Problem:

- Too slow for large datasets.
    

---

## Stochastic Gradient Descent (SGD)

Instead of using the entire dataset:

- Uses **one example at a time** (stochastic)
    
- Or a **small batch of examples** (mini-batch)
    

Advantages:

- Faster training
    
- Works well with large datasets
    

---

### Core Idea of Deep Learning

```
Linear Layers
+ Non-linear Activations (ReLU)
+ Stochastic Gradient Descent
```

These three components form the **foundation of deep learning models**.

---

## Applications Covered

- Computer Vision
    
- Tabular Data
    
- Next section: **Natural Language Processing (NLP)**
    

---

# 4. Natural Language Processing (NLP)

Two important libraries used:

### fast.ai

High-level deep learning library designed for **simplicity and rapid experimentation**.

---

### Hugging Face Transformers

More **low-level and flexible** library used for:

- NLP
    
- LLMs
    
- Transformers
    

Widely used in modern AI systems.

---

## Fine-Tuning Pretrained Models

Fine-tuning means:

Taking a **model already trained on a huge dataset** and continuing training on a **smaller task-specific dataset**.

Benefits:

- Faster training
    
- Better performance
    
- Requires less data
    

Example:

A language model trained on internet text can be fine-tuned for:

- sentiment analysis
    
- chatbot tasks
    
- summarization
    

---

## Masked Language Modeling

Modern NLP models often use **Masked Language Modeling (MLM)**.

Instead of predicting the next word, the model learns to **predict missing words**.

Example:

```
The cat sat on the [MASK].
```

Model predicts:

```
mat
```

This helps the model learn **bidirectional context**.

---

## Tokenization

Neural networks understand **numbers, not text**.

Therefore text must be converted into **tokens**.

Example:

```
"I love AI"
```

Tokenized into:

```
["I", "love", "AI"]
```

Each token is converted into a **numerical representation**.

---

## Overfitting vs Underfitting

### Overfitting

Model memorizes training data instead of learning patterns.

Result:

- High training accuracy
    
- Poor performance on new data
    

---

### Underfitting

Model is too simple and fails to capture patterns.

Result:

- Poor training performance
    
- Poor test performance
    

---

# Evaluation Metrics

## Metrics vs Loss

**Loss**

- Used during training
    
- Optimized by gradient descent
    

**Metrics**

- Used to evaluate model performance
    
- Not necessarily optimized directly
    

---

## Pearson Correlation Coefficient

Measures **linear relationship between two variables**.

Formula concept:

```
r ∈ [-1, 1]
```

Interpretation:

|Value|Meaning|
|---|---|
|1|Perfect positive correlation|
|0|No correlation|
|-1|Perfect negative correlation|

Often used in **regression tasks**.
