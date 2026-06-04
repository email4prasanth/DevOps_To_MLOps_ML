# Random Forest Regression

## Definition

**Random Forest Regression** is an ensemble supervised learning algorithm used to predict continuous numerical values. It combines the predictions of multiple Decision Trees and returns the average prediction, resulting in better accuracy and reduced overfitting compared to a single Decision Tree.

---

## Why Random Forest?

A single Decision Tree can easily **overfit** the training data.

Random Forest solves this by:

- Creating multiple Decision Trees
- Training each tree on a random subset of data (Bootstrap Sampling)
- Using a random subset of features for each split
- Averaging the predictions from all trees

This reduces variance and improves generalization.

---

## Applications

### Finance

- House price prediction
- Stock demand forecasting
- Risk assessment

### Retail

- Sales forecasting
- Demand prediction
- Revenue estimation

### Healthcare

- Medical cost prediction
- Insurance claim estimation

### Manufacturing

- Production cost prediction
- Equipment maintenance cost estimation

---

## Pictorial Representation

### Step 1: Create Multiple Trees

```text
                Training Data
                       |
      ----------------------------------
      |               |               |
      v               v               v

    Tree 1         Tree 2         Tree 3
     8.5            9.0            8.8
```

### Step 2: Average Predictions

```text
Prediction = (8.5 + 9.0 + 8.8) / 3

Prediction = 8.76
```

Final Output = Average of all tree predictions.

---

## Mathematical Expression

### Random Forest Prediction

\[
\hat{y} = \frac{1}{N}\sum_{i=1}^{N} T_i(x)
\]

Where:

- \(\hat{y}\) = Final prediction
- \(N\) = Number of trees
- \(T_i(x)\) = Prediction from the i-th tree

---

## Working Process

### 1. Bootstrap Sampling

Randomly select samples from training data with replacement.

```text
Original Data
      |
      +--> Sample 1
      |
      +--> Sample 2
      |
      +--> Sample 3
```

Each tree gets different training data.

---

### 2. Feature Randomization

At every split:

```text
Features:
Age, Salary, Experience, Education

Tree 1:
Age, Salary

Tree 2:
Salary, Education

Tree 3:
Age, Experience
```

This makes trees less correlated.

---

### 3. Build Multiple Trees

```text
Data --> Tree 1
Data --> Tree 2
Data --> Tree 3
...
Data --> Tree N
```

---

### 4. Average Predictions

```text
Tree 1 Prediction = 100

Tree 2 Prediction = 110

Tree 3 Prediction = 105

Final Prediction
= (100 + 110 + 105)/3

= 105
```

---

## Important Hyperparameters

| Hyperparameter | Description |
|---------------|-------------|
| `n_estimators` | Number of trees |
| `max_depth` | Maximum depth of tree |
| `min_samples_split` | Minimum samples required to split |
| `min_samples_leaf` | Minimum samples in leaf node |
| `max_features` | Number of random features considered |
| `bootstrap` | Whether bootstrap sampling is used |

---

## Bias and Variance

### Decision Tree

```text
Low Bias
High Variance
```

Trees learn training data very well but may overfit.

### Random Forest

```text
Slightly Higher Bias
Much Lower Variance
```

Averaging many trees reduces variance significantly.

---

## Advantages
- High Accuracy - Usually performs better than Linear Regression for complex data
- Handles Non-Linear Relationships - Captures complex patterns
- Reduces Overfitting - Multiple trees reduce variance
- Robust to Outliers - Less affected than Linear Regression
- Feature Importance - Can identify the most influential features
- Minimal Data Preparation - No need for feature scaling
---

## Disadvantages
- Slower Training - Many trees need to be built
- More Memory Usage - Stores multiple trees
- Less Interpretable - Harder to explain than Linear Regression
- Large Model Size - Can become computationally expensive
---

## Random Forest vs Linear Regression

| Feature | Linear Regression | Random Forest Regression |
|----------|------------------|-------------------------|
| Relationship | Linear | Linear + Nonlinear |
| Accuracy | Moderate | High |
| Interpretability | High | Low |
| Outlier Sensitivity | High | Low |
| Feature Scaling | Recommended | Not Required |
| Overfitting Risk | Low | Very Low |
| Training Speed | Fast | Slower |

---

## Interview Answer

> Random Forest Regression is an ensemble supervised learning algorithm used to predict continuous numerical values. It builds multiple Decision Trees using bootstrap sampling and random feature selection. Each tree makes a prediction, and the final output is the average of all tree predictions. This reduces overfitting, lowers variance, and improves accuracy compared to a single Decision Tree. It is commonly used in house price prediction, sales forecasting, demand forecasting, and financial modeling because it can handle complex nonlinear relationships and is robust to outliers.