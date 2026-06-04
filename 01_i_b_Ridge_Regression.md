# Ridge Regression

## What is Ridge Regression?

**Ridge Regression** is an extension of Linear Regression that adds a **penalty term (L2 Regularization)** to the cost function to reduce overfitting and handle multicollinearity.

When a Linear Regression model becomes too complex or the features are highly correlated, the weights can become very large, leading to poor performance on unseen data. Ridge Regression addresses this by shrinking the weights toward zero.

---

## Why Do We Need Ridge Regression?

### Problem with Linear Regression

Suppose we are predicting house prices using:

- House Area
- Number of Rooms
- House Age
- Distance to City

If some features are highly correlated (e.g., Area and Number of Rooms), Linear Regression may assign very large weights.

Result:
- High Variance
- Overfitting
- Poor Generalization

Ridge Regression adds a penalty to keep weights small.

---

## Mathematical Expression

### Linear Regression Cost Function

```math
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
```

### Ridge Regression Cost Function

```math
MSE + \lambda\sum_{j=1}^{p}w_j^2
```

Or equivalently:

```math
\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2 + \lambda\sum_{j=1}^{p}w_j^2
```

Where:

- **MSE** = Prediction Error
- **wj** = Feature weights
- **λ (Lambda)** = Regularization parameter
- **p** = Number of features

---

## Role of Lambda (λ)

### λ = 0

```text
Ridge Regression = Linear Regression
```

No regularization.

### Small λ

```text
Slight weight reduction
Balanced model
```

### Large λ

```text
Strong weight reduction
Simpler model
Higher bias
Lower variance
```

---

## Pictorial Representation

### Linear Regression (Overfitting Risk)

```text
Weight Values

Feature1 = 120
Feature2 = 95
Feature3 = 140
Feature4 = 110
```

Large coefficients.

### Ridge Regression

```text
Weight Values

Feature1 = 25
Feature2 = 18
Feature3 = 30
Feature4 = 22
```

Weights are shrunk but not removed.

---

## Key Characteristic

### Ridge Regression Never Makes Coefficients Exactly Zero

```text
Linear Regression:
[120, 95, 140, 110]

Ridge Regression:
[25, 18, 30, 22]
```

All features remain in the model.

---

## Effect on Bias and Variance

| Model | Bias | Variance |
|---------|---------|---------|
| Linear Regression | Low | High |
| Ridge Regression | Slightly Higher | Lower |

### Trade-off

```text
Increase λ
    ↓
Increase Bias
    ↓
Decrease Variance
    ↓
Reduce Overfitting
```

---

## Applications

### Finance
- Stock price prediction
- Credit risk modeling

### Real Estate
- House price prediction

### Sales Forecasting
- Revenue prediction

### Healthcare
- Medical cost prediction

### Marketing
- Customer spending prediction

---

## Advantages

- Reduces Overfitting - Improves generalization.
- Handles Multicollinearity - Works well when features are highly correlated.
- Stable Predictions - Less sensitive to data fluctuations.
- Keeps All Features - Useful when every feature has business importance.

---

## Disadvantages

- Does Not Perform Feature Selection - Coefficients become small but never exactly zero.
- Requires Hyperparameter Tuning - Need to choose λ carefully.
- Less Interpretable - Coefficients are shrunk.

---

## Linear Regression vs Ridge Regression

| Aspect | Linear Regression | Ridge Regression |
|----------|----------|----------|
| Regularization | No | L2 |
| Overfitting Control | Poor | Good |
| Multicollinearity Handling | Poor | Good |
| Feature Selection | No | No |
| Weight Reduction | No | Yes |
| Variance | High | Lower |
| Bias | Lower | Slightly Higher |

---

## Interview Answer

> Ridge Regression is a regularized version of Linear Regression that adds an L2 penalty term to the cost function. The penalty term shrinks the coefficients toward zero, reducing model complexity and preventing overfitting. It is particularly useful when features are highly correlated. Unlike Lasso Regression, Ridge Regression does not eliminate features; it only reduces their impact. As the regularization parameter λ increases, bias increases slightly while variance decreases, resulting in better generalization on unseen data.