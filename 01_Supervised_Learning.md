# Types of Supervised Learning

1. Regression
2. Classification

## 1. Regression

Regression is used when the output (Y), target variable, or dependent variable is **continuous**, such as a real number or numerical value. The algorithm learns the relationship between the independent variables (features) and the dependent variable from historical data, then predicts the output value for new inputs.

| Regression Model             | Why is it Used?                                              | Formula                                                                     | Typical Use Case                                             |   |                                        |
| ---------------------------- | ------------------------------------------------------------ | --------------------------------------------------------------------------- | ------------------------------------------------------------ | - | -------------------------------------- |
| **Linear Regression**        | Simple, fast, interpretable baseline model                   | $y = \beta_0 + \beta_1x_1 + \beta_2x_2 + \cdots + \beta_nx_n + \varepsilon$ | House price prediction, salary prediction, sales forecasting |   |                                        |
| **Ridge Regression**         | Reduces overfitting and handles multicollinearity            | $\text{Cost} = RSS + \lambda \sum_{j=1}^{n}\beta_j^2$                       | Financial forecasting, correlated features                   |   |                                        |
| **Lasso Regression**         | Performs feature selection by shrinking coefficients to zero | $\text{Cost} = RSS + \lambda \sum_{j=1}^{n}\beta_j^2$                       | Marketing analytics, feature selection |
| **Decision Tree Regression** | Learns nonlinear relationships through recursive splits      | $\hat{y} = \frac{1}{N_{leaf}}\sum_{i \in leaf} y_i$                         | Demand forecasting, inventory prediction                     |   |                                        |
| **Random Forest Regression** | Reduces overfitting by averaging multiple decision trees     | $\hat{y} = \frac{1}{T}\sum_{t=1}^{T} h_t(x)$                                | Customer lifetime value, risk analysis                       |   |                                        |

## 2. Classification

Classification is used when the output (Y), target variable, or dependent variable is {0,1} or {-1,+1}, find decession boundaries to which divides data into classes or catagory


| Classification Model             | Why is it Used?                                                                                   | Formula                                                          | Typical Use Case             |
| -------------------------------- | ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- | ---------------------------- |
| **Logistic Regression**          | Simple, fast, interpretable, and serves as a strong baseline classifier.                          | $P(Y=1)=\frac{1}{1+e^{-(\beta_0+\beta_1X_1+\cdots+\beta_nX_n)}}$ | Customer Churn Prediction    |
| **Decision Tree**                | Easy to understand, visualize, and explain decision-making.                                       | $Entropy(S)=-\sum_{i=1}^{c} p_i \log_2(p_i)$                     | Loan Approval Classification |
| **Random Forest**                | Reduces overfitting by combining multiple decision trees, improving accuracy and robustness.      | $\hat{y}=\text{Mode}(Tree_1,Tree_2,\ldots,Tree_n)$               | Credit Risk Classification   |
| **Support Vector Machine (SVM)** | Effective for high-dimensional data and complex classification boundaries.                        | $w^Tx+b=0$                                                       | Email Spam Detection         |
| **XGBoost**                      | High predictive accuracy, handles complex patterns, and performs well on structured/tabular data. | $F_m(x)=F_{m-1}(x)+\eta h_m(x)$                                  | Fraud Detection              |

