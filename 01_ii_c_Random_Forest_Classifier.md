# Random Forest Classifier

## Definition

**Random Forest Classifier** is a supervised machine learning algorithm used for **classification problems**. It combines multiple Decision Trees and makes the final prediction based on the **majority vote** of all trees.

The idea is:

> Many weak decision trees together create a strong and more accurate model.

---

## Why Random Forest?

A single Decision Tree can easily **overfit** the training data.

Random Forest reduces overfitting by:

1. Creating multiple decision trees.
2. Training each tree on a random subset of data (**Bootstrap Sampling**).
3. Using a random subset of features for each split (**Feature Randomness**).
4. Taking the majority vote from all trees.

---

## Pictorial Representation

### Single Decision Tree

```text
                Age > 30?
               /         \
             Yes          No
             /             \
      Salary > 50k?      Reject
         /      \
      Accept   Reject
```

**Problem:**
- Can overfit
- Sensitive to noise

---

### Random Forest

```text
                    Input Data
                         |
 -------------------------------------------------
 |               |              |               |
Tree 1         Tree 2         Tree 3         Tree 4
 |               |              |               |
Accept         Accept        Reject         Accept
 -------------------------------------------------
                         |
                  Majority Vote
                         |
                      Accept
```

---

## Mathematical Idea

Suppose:

```text
Tree1 → Yes
Tree2 → Yes
Tree3 → No
Tree4 → Yes
Tree5 → No
```

Majority Vote:

```text
Yes = 3
No  = 2
```

Final Prediction:

```text
Yes
```

Classification Output:

```text
ŷ = Mode(T1, T2, T3, ..., Tn)
```

Where:

- ŷ = Predicted Class
- T₁ ... Tₙ = Predictions from individual trees

---

## Working Process

### Step 1: Bootstrap Sampling

Create multiple random datasets from the original dataset.

**Original Data**

```text
1 2 3 4 5
```

**Sample 1**

```text
1 2 2 4 5
```

**Sample 2**

```text
1 3 3 4 5
```

**Sample 3**

```text
2 2 4 5 5
```

---

### Step 2: Build Multiple Trees

Each tree gets:

- Random records
- Random features

---

### Step 3: Predict

Each tree predicts independently.

---

### Step 4: Majority Voting

Most common class becomes the final output.

---

## Example

### Bank Loan Approval

**Input Features**

```text
Age
Salary
Credit Score
Experience
```

**Output**

```text
Approved
Rejected
```

Random Forest learns patterns from historical loan data and predicts whether a new customer should be approved.

---

## Important Hyperparameters

| Parameter | Purpose |
|------------|----------|
| n_estimators | Number of trees |
| max_depth | Maximum tree depth |
| min_samples_split | Minimum samples required to split |
| min_samples_leaf | Minimum samples required in a leaf node |
| max_features | Features considered at each split |
| bootstrap | Enable bootstrap sampling |

---

## Feature Importance

One major advantage:

Random Forest can tell which features are most important.

**Example**

```text
Loan Approval

Credit Score → 50%
Salary       → 25%
Experience   → 15%
Age          → 10%
```

This helps explain the model.

---

## Bias vs Variance

### Decision Tree

```text
Bias     : Low
Variance : High
```

**Problem:** Overfitting

---

### Random Forest

```text
Bias     : Slightly Higher
Variance : Much Lower
```

**Result:**
- Better generalization
- Better performance on unseen data

---

## Advantages

### High Accuracy

- Usually performs better than a single Decision Tree.

### Reduces Overfitting

- Multiple trees reduce variance.

### Handles Large Datasets

- Works well with large feature sets.

### Handles Missing Values

- More robust than many algorithms.

### Feature Importance

- Provides feature ranking.

### Less Data Preprocessing

- No need for normalization or scaling.

---

## Disadvantages

### Slower Training

- Building many trees takes time.

### Higher Memory Usage

- Stores multiple trees.

### Less Interpretable

- Harder to explain than a single Decision Tree.

### Large Model Size

- Not ideal for resource-constrained systems.

---

## When to Use Random Forest?

### Use Random Forest When

- High prediction accuracy is required
- Data contains nonlinear relationships
- You want feature importance
- Dataset has many features
- Overfitting is a concern

### Avoid When

- Model explainability is the highest priority
- Extremely low latency is required

---

## Interview Answer (2 Minutes)

> Random Forest is a supervised ensemble learning algorithm used for classification and regression. It builds multiple decision trees using bootstrap sampling and random feature selection. Each tree makes an independent prediction, and the final output is determined by majority voting in classification or averaging in regression. Compared to a single decision tree, Random Forest reduces overfitting, lowers variance, improves generalization, and provides feature importance. It is commonly used in fraud detection, customer churn prediction, disease diagnosis, and loan approval systems.