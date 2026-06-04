- Types of Supervised Learning
    1. Regression
    2. Classification
1. Regression means when the y output/ target/ dependent variable is continous like Real number/ Numerical value, the algorithm understand the relation between the independent and dependent varialble from the historical data and predicts the output y for a new input

| Regression Model             | Why is it Used?                                              | Formula                                                                     | Typical Use Case                                             |   |                                        |
| ---------------------------- | ------------------------------------------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------ | - | -------------------------------------- |
| **Linear Regression**        | Simple, fast, interpretable baseline model                   | $y = \beta_0 + \beta_1x_1 + \beta_2x_2 + \cdots + \beta_nx_n + \varepsilon$ | House price prediction, salary prediction, sales forecasting |   |                                        |
| **Ridge Regression**         | Reduces overfitting and handles multicollinearity            | $\text{Cost} = RSS + \lambda \sum_{j=1}^{n}\beta_j^2$                       | Financial forecasting, correlated features                   |   |                                        |
| **Lasso Regression**         | Performs feature selection by shrinking coefficients to zero | $\text{Cost} = RSS + \lambda \sum_{j=1}^{n}|\beta_j|$ | Marketing analytics, feature selection |
| **Decision Tree Regression** | Learns nonlinear relationships through recursive splits      | $\hat{y} = \frac{1}{N_{leaf}}\sum_{i \in leaf} y_i$                         | Demand forecasting, inventory prediction                     |   |                                        |
| **Random Forest Regression** | Reduces overfitting by averaging multiple decision trees     | $\hat{y} = \frac{1}{T}\sum_{t=1}^{T} h_t(x)$                                | Customer lifetime value, risk analysis                       |   |                                        |

