# Logistic Regression

## Definition

**Logistic Regression** is a supervised machine learning classification algorithm used to predict the probability that an input belongs to a particular class.

Unlike Linear Regression, which predicts a continuous value, Logistic Regression predicts a **categorical outcome** such as:

- Spam / Not Spam
- Fraud / Not Fraud
- Churn / No Churn
- Disease / No Disease

---

## Why Not Use Linear Regression for Classification?

Suppose we want to predict:

```text
0 = Not Spam
1 = Spam
```

Linear Regression can produce outputs like:

```text
-0.5
1.7
2.3
```

These are not valid probabilities.

Logistic Regression converts the output into a probability between **0 and 1**.

---

## Mathematical Expression

### Step 1: Linear Combination

Similar to Linear Regression:

```math
z = w₀ + w₁x₁ + w₂x₂ + ... + wₙxₙ
```

Where:

- `w₀` = Bias
- `w₁,w₂,...,wₙ` = Weights
- `x₁,x₂,...,xₙ` = Features

---

### Step 2: Apply Sigmoid Function

The sigmoid function converts any value into a probability between 0 and 1.

```math
σ(z) = 1 / (1 + e⁻ᶻ)
```

Output range:

```text
0 ≤ Probability ≤ 1
```

---

## Pictorial Representation

### Linear Regression

```text
Output
 ^
 |
 |
 |        /
 |      /
 |    /
 |  /
 |/
 +-----------------> X
```

### Logistic Regression

```text
Probability
1.0 |           **********
    |          *
0.5 |--------- *
    |          *
0.0 |**********
    +-----------------> X
```

This S-shaped curve is called the **Sigmoid Curve**.

---

## Decision Boundary

The predicted probability is converted into a class.

```text
Probability >= 0.5  → Class 1
Probability < 0.5   → Class 0
```

Example:

| Probability | Prediction |
|------------|------------|
| 0.92 | Spam |
| 0.85 | Spam |
| 0.45 | Not Spam |
| 0.12 | Not Spam |

---

## Bias and Weights

The interpretation is similar to Linear Regression.

### Weight

- Positive weight → increases probability of Class 1.
- Negative weight → decreases probability of Class 1.

### Bias

- Shifts the decision boundary.
- Helps adjust the classification threshold.

Example:

```text
Spam Probability = σ(-3 + 0.8 × Number_of_Links)
```

---

## Cost Function

Unlike Linear Regression, Logistic Regression does **not** use MSE.

It uses **Log Loss (Binary Cross Entropy)**.

```math
Log Loss = -(1/n) Σ [ yᵢ log(ŷᵢ) + (1-yᵢ) log(1-ŷᵢ) ]
```

Where:

- `yᵢ` = Actual label
- `ŷᵢ` = Predicted probability
- `n` = Number of samples

This heavily penalizes confident wrong predictions.

---

## Applications

### Email Filtering

- Spam detection

### Banking

- Fraud detection
- Loan approval prediction

### Healthcare

- Disease prediction
- Cancer detection

### HR Analytics

- Employee attrition prediction

### Marketing

- Customer churn prediction
- Lead conversion prediction

---

## Advantages

### Simple and Fast

- Easy to train.

### Produces Probabilities

- Gives confidence scores.

### Highly Interpretable

- Easy to understand feature impact.

### Works Well on Small Datasets

- Good baseline classification model.

### Low Computational Cost

- Efficient compared to many complex models.

---

## Disadvantages

### Linear Decision Boundary

- Struggles with complex nonlinear patterns.

### Sensitive to Outliers

- Can be affected by extreme values.

### Requires Feature Engineering

- Performance often depends on quality features.

### Lower Accuracy on Complex Data

- Models like Random Forest, XGBoost, or Neural Networks may perform better.

---

## Linear Regression vs Logistic Regression

| Feature | Linear Regression | Logistic Regression |
|----------|------------------|--------------------|
| Problem Type | Regression | Classification |
| Output | Continuous Value | Probability (0-1) |
| Equation | Linear | Sigmoid |
| Prediction | Salary, Price | Spam, Fraud |
| Cost Function | MSE | Log Loss |
| Output Range | (-∞, +∞) | (0,1) |

---

## Interview Answer (2 Minutes)

> Logistic Regression is a supervised classification algorithm used to predict the probability of a categorical outcome. It first computes a linear combination of input features and then applies the sigmoid function to convert the result into a probability between 0 and 1. Based on a threshold, typically 0.5, the model classifies the input into one of two classes. It is widely used for spam detection, fraud detection, customer churn prediction, and disease diagnosis because it is simple, interpretable, and computationally efficient.