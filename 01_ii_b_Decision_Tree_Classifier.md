# Decision Tree Classifier

## Definition

**Decision Tree Classification** is a supervised machine learning algorithm used to predict **categorical outputs (classes)**. It works by repeatedly splitting the data into smaller groups based on feature values until a decision can be made.

Think of it like a flowchart of **if-else conditions**.

---

## Example Problem

**Predict whether a customer will buy a product.**

| Age | Income | Bought Product |
|------|----------|---------------|
| Young | High | No |
| Young | Low | No |
| Middle | High | Yes |
| Old | High | Yes |
| Old | Low | Yes |

The Decision Tree learns rules such as:

```text
                Age?
               /    \
          Young      Old/Middle
            |            |
           No           Yes
```

---

## Pictorial Representation

```text
                  Root Node
                  Age <= 30?
                  /       \
                Yes        No
                /           \
         Income > 50K?      Buy = Yes
           /      \
         Yes      No
         /         \
      Buy=No     Buy=Yes
```

### Components

#### 1. Root Node
- First decision point.
- Contains the entire dataset.

#### 2. Internal Node
- Represents a condition or test.

#### 3. Branch
- Outcome of a condition.

#### 4. Leaf Node
- Final prediction (class label).

---

## How It Works

### Step 1
Start with all training data.

### Step 2
Find the feature that best separates the classes.

### Step 3
Split the data.

### Step 4
Repeat recursively.

### Step 5
Stop when:
- Pure nodes are obtained, or
- Maximum depth is reached, or
- Minimum samples are reached.

---

## Mathematical Concepts

Decision Trees do not use weights and bias like Linear Regression.

Instead they use **Impurity Measures**.

---

## 1. Entropy

Measures disorder or impurity.

### Formula

```math
Entropy(S) = -∑ pᵢ log₂(pᵢ)
```

Where:
- pᵢ = probability of class i
- c = number of classes

### Interpretation

| Entropy | Meaning |
|----------|---------|
| 0 | Pure node |
| 1 | Completely mixed (binary classes) |

---

## 2. Information Gain

Measures reduction in entropy after splitting.

### Formula

```math
Information Gain = Entropy(Parent) - ∑ (|Child| / |Parent|) × Entropy(Child)
```

The feature with the **highest Information Gain** is selected.

---

## 3. Gini Impurity

Most commonly used in practical implementations.

### Formula

```math
Gini = 1 - ∑ pᵢ²
```

### Interpretation

| Gini | Meaning |
|-------|---------|
| 0 | Pure node |
| High | Mixed classes |

The algorithm chooses the split with the **lowest Gini Impurity**.

---

## Why Gini is Preferred

- Faster computation
- No logarithmic calculations
- Used by default in many implementations

---

## Important Hyperparameters

| Parameter | Purpose |
|------------|---------|
| max_depth | Maximum depth of tree |
| min_samples_split | Minimum samples needed to split |
| min_samples_leaf | Minimum samples in a leaf node |
| criterion | Gini or Entropy |
| max_features | Number of features considered per split |

---

## Advantages

### Easy to Understand
- Highly interpretable.

### No Feature Scaling Required
- Works directly on raw data.

### Handles Numerical and Categorical Data
- Very flexible.

### Feature Importance
- Shows which features are important.

### Nonlinear Relationships
- Captures complex patterns.

---

## Disadvantages

### Overfitting
- Trees can become very deep.

### High Variance
- Small changes in data can produce a different tree.

### Unstable
- Sensitive to noisy data.

### Lower Accuracy Than Ensembles
- Usually outperformed by Random Forest and XGBoost.

---

## Bias-Variance Perspective

| Tree Type | Bias | Variance |
|------------|------|----------|
| Shallow Tree | High | Low |
| Deep Tree | Low | High |
| Properly Pruned Tree | Balanced | Balanced |

### Underfitting

```text
Very shallow tree
Too few splits
Misses important patterns
```

### Overfitting

```text
Very deep tree
Memorizes training data
Poor generalization
```

---

## Typical Use Cases

### Banking
- Loan approval
- Credit risk classification

### Healthcare
- Disease prediction

### E-commerce
- Customer purchase prediction
- Customer churn prediction

### Cybersecurity
- Spam detection
- Fraud detection

---

## Interview Answer

> Decision Tree is a supervised classification algorithm that predicts categorical outputs by recursively splitting data based on feature values. It creates a tree-like structure consisting of root nodes, internal nodes, branches, and leaf nodes. The best split is selected using impurity measures such as Entropy, Information Gain, or Gini Impurity. Decision Trees are easy to interpret, require minimal preprocessing, and can handle nonlinear relationships. However, they are prone to overfitting and high variance, which is why ensemble methods like Random Forest are often preferred in production environments.