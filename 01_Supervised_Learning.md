- Types of Supervised Learning
    1. Regression
    2. Classification
1. Regression means when the y output/ target/ dependent variable is continous like Real number/ Numerical value, the algorithm understand the relation between the independent and dependent varialble from the historical data and predicts the output y for a new input

| Regression Model             | Why is it Used?                                                                 | Formula / Core Idea                                                                | Typical Use Case                                                     |
| ---------------------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| **Linear Regression**        | Simple, fast, highly interpretable, good baseline model                         | y=\beta_0+\beta_1x_1+\beta_2x_2+\cdots+\beta_nx_n+\varepsilon                      | House price prediction, salary prediction, sales forecasting         |
| **Ridge Regression**         | Reduces overfitting by penalizing large coefficients; handles multicollinearity | Cost Function: RSS+\lambda\sum_{j=1}^{n}\beta_j^2                                  | Financial forecasting, datasets with many correlated features        |
| **Lasso Regression**         | Performs feature selection by shrinking some coefficients to zero               | Cost Function: RSS+\lambda\sum_{j=1}^{n}|\beta_j|                                  | Customer churn value prediction, marketing analytics                 |
| **Decision Tree Regression** | Captures nonlinear relationships and is easy to visualize                       | Splits data recursively into regions and predicts the mean value in each leaf node | Demand forecasting, inventory prediction, business analytics         |
| **Random Forest Regression** | Higher accuracy than a single tree; reduces overfitting using multiple trees    | Prediction = Average of outputs from multiple decision trees                       | Customer lifetime value prediction, sales forecasting, risk analysis |

