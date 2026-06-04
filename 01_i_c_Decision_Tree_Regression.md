# Decision Tree Regression

## Definition

**Decision Tree Regression** is a supervised learning algorithm used to predict **continuous numerical values**. Instead of fitting a single straight line like Linear Regression, it splits the data into smaller regions using decision rules and predicts the output based on the average value of observations in each region.

---

## Intuition

Suppose you want to predict **house prices**.

A Decision Tree may learn rules like:

```text
House Size > 1500 sq.ft?
│
├── Yes
│   ├── Bedrooms > 3?
│   │   ├── Yes → Price = 80 Lakhs
│   │   └── No  → Price = 65 Lakhs
│
└── No
    ├── Location = City?
    │   ├── Yes → Price = 50 Lakhs
    │   └── No  → Price = 35 Lakhs
```

Instead of finding a line, it creates decision rules and predicts a numerical value at the leaf node.

---

## Pictorial Representation

```text
                    Root Node
                         │
              Experience > 3 Years?
                   /             \
                 No               Yes
                 │                 │
         Salary = 4 LPA     Salary > 8 LPA?
                               /        \
                             No          Yes
                             │            │
                        Salary=7LPA   Salary=12LPA
```

Each leaf node contains the predicted numerical value.

---

## Mathematical Expression

Unlike Linear Regression:

```math
y = w₀ + w₁x
```

Decision Trees do **not** have weights and bias.

Instead, they split data to minimize variance within each node.

### Mean Squared Error (MSE)

```math
MSE = (1/n) Σ (yᵢ - ȳ)²
```

Where:

- `yᵢ` = Actual values
- `ȳ` = Mean value of the node
- `n` = Number of samples

The algorithm chooses the split that reduces MSE the most.

---

## How Training Works

1. Start with the entire dataset.
2. Try every possible split.

Example:

```text
Experience > 2.5 ?
Experience > 3.5 ?
Experience > 4.5 ?
```

3. Calculate variance/MSE after each split.
4. Choose the split with the lowest error.
5. Repeat recursively until stopping criteria are met.

---

## Hyperparameters

- max_depth: Maximum depth of the tree.

```text
Depth = 1
Depth = 2
Depth = 3
...
```
- min_samples_split: Minimum samples required to split a node.
- min_samples_leaf:Minimum samples required in a leaf node.
- max_features: Number of features considered for splitting.

---

## Applications

- Finance House price prediction, Loan amount estimation
- Retail - Sales forecasting, Demand prediction
- Manufacturing - Production cost estimation
- Healthcare - Treatment cost prediction
- HR - Salary prediction

---

## Advantages

### 1. Handles Complex Relationships
- Can learn both linear and non-linear patterns.
- Works well when the relationship between features and target is not a straight line.

### 2. Easy to Understand
- Predictions can be explained using simple IF-ELSE rules.

```text
IF Experience > 5
THEN Salary = 15 LPA
```

### 3. No Feature Scaling Needed
- Works directly with the original data.
- No need for normalization or standardization.

### 4. Works with Different Data Types
- Can handle both numerical and categorical data.

### 5. Identifies Important Features
- Helps determine which features have the most impact on predictions.

---

## Disadvantages

### 1. Overfitting
- Deep trees can memorize the training data.
- Performs well on training data but poorly on new data.

### 2. Sensitive to Data Changes
- Small changes in the dataset can produce a different tree.

### 3. Lower Accuracy than Ensemble Models
- Usually less accurate than Random Forest or XGBoost.

### 4. Can Become Complex
- Large trees are difficult to interpret and maintain.

### 5. Greedy Approach
- Chooses the best split at each step.
- May not produce the overall best tree.
---

## Bias-Variance Perspective

### Shallow Tree

```text
High Bias
Low Variance
Underfitting
```

Example:

```text
max_depth = 1
```

### Deep Tree

```text
Low Bias
High Variance
Overfitting
```

Example:

```text
max_depth = 20
```

### Balanced Tree

```text
Moderate Bias
Moderate Variance
Best Generalization
```

---

## Comparison with Linear Regression

| Feature | Linear Regression | Decision Tree Regression |
|----------|----------|----------|
| Relationship | Linear | Linear + Nonlinear |
| Formula | Yes | No |
| Weights & Bias | Yes | No |
| Interpretability | High | High |
| Outlier Handling | Poor | Better |
| Feature Scaling | Sometimes Required | Not Required |
| Complex Patterns | Poor | Good |
| Overfitting Risk | Low | High |

---

## Interview Answer

> Decision Tree Regression is a supervised learning algorithm used to predict continuous numerical values. It works by recursively splitting the dataset into smaller regions based on feature values and predicting the average target value at each leaf node. Unlike Linear Regression, it does not use a mathematical equation with weights and bias. Instead, it selects splits that minimize variance or Mean Squared Error (MSE). It can capture nonlinear relationships, is easy to interpret, and does not require feature scaling. However, it is prone to overfitting, which can be controlled using hyperparameters such as max_depth, min_samples_split, and min_samples_leaf.