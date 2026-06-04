# Linear Regression

## Definition

**Linear Regression** is a supervised machine learning algorithm used to predict a **continuous numerical value** by finding the best-fit linear relationship between input features (X) and target variable (Y).

---

## Applications

- Business - Sales forecasting,Revenue prediction,Demand forecasting
- Finance - House price prediction, Loan amount estimation, Insurance premium prediction
- HR Analytics - Salary prediction, Employee performance prediction
- Manufacturing - Production cost estimation, Maintenance cost prediction

---

## Pictorial Representation

```text
Salary
  ^
  |
10|                           *
  |
  |
 8|                     *
  |
  |
 6|               *
  |
  |
 4|         *
  |
  |
 3|    *
  |
  +---------------------------------> Experience
      1    2    3    4    5
```

The algorithm draws the **best-fit line** through these points.

---

## Mathematical Expression

### Simple Linear Regression

$$
y = w_0 + w_1x
$$

Where:

- **y** = Predicted output
- **x** = Input feature
- **w₀** = Bias (Intercept)
- **w₁** = Weight (Slope)

### Multiple Linear Regression

$$
y = w_0 + w_1x_1 + w_2x_2 + \cdots + w_nx_n
$$

Where:

- **x₁, x₂, ..., xₙ** = Input features
- **w₁, w₂, ..., wₙ** = Corresponding weights

---

## Bias and Weights

### Weight (w)

- Determines feature importance.
- Controls how much influence a feature has on the prediction.

Example:

$$
Salary = 2 + 1.5 \times Experience
$$

Here:

- Bias = 2
- Weight = 1.5

Meaning:

- Every additional year of experience increases salary by 1.5 LPA.

### Bias (Intercept)

Bias shifts the regression line up or down.

Without bias:

$$
Salary = 1.5 \times Experience
$$

With bias:

$$
Salary = 2 + 1.5 \times Experience
$$

Bias helps fit real-world data more accurately.

---

## Cost Function (Mean Squared Error)

The model minimizes prediction error using **Mean Squared Error (MSE)**.

$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
$$

Where:

Where:

- y<sub>i</sub> = Actual value
- ŷ<sub>i</sub> = Predicted value
- n = Number of samples

Lower MSE indicates better model performance.

Lower MSE indicates better model performance.

---

## How Training Works

1. Initialize weights and bias.
2. Predict output.
3. Calculate error.
4. Calculate loss (MSE).
5. Update weights and bias using Gradient Descent.
6. Repeat until error is minimized.

---

## Assumptions of Linear Regression

1. Linear relationship between X and Y.
2. No multicollinearity among features.
3. Errors are normally distributed.
4. Constant variance of errors (Homoscedasticity).
5. Observations are independent.

---

## Advantages

- Simple
- Fast Training
- Highly Interpretable
- Less Computational Cost
- Good Baseline Model

## Disadvantages

- Assumes Linearity
- Sensitive to Outliers
- Underfitting Risk
- Multicollinearity Issues
- Poor Performance on Complex Patterns

---

## Interview Answer

> Linear Regression is a supervised learning algorithm used to predict continuous numerical values. It establishes a linear relationship between independent variables and the dependent variable using the equation:
>
> $$
> y = w_0 + w_1x
> $$
>
> where \(w_0\) is the bias and \(w_1\) is the weight. The model learns these parameters by minimizing the Mean Squared Error (MSE) using optimization techniques such as Gradient Descent. It is commonly used for salary prediction, house price estimation, sales forecasting, and demand prediction. Its advantages are simplicity, interpretability, and fast training, while its limitations include sensitivity to outliers and inability to model complex nonlinear relationships.