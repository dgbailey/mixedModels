## Independence of errors
---
**What is this? Why is this important**

We are trying to predict or demonstrate a relationship between two observed quantities (dependent & independent).<br >

As one quantity changes (A) in two dimensions how can we model this relationship to (B) as a line ? Resulting in (A,B) coortinates in a Cartesian plane.

**What are these coordiantes (Observed values)**

Typically it is what you are interested in. For instance how does the size of an organization impact money spent in a SaaS product.<br>

But we are interested in predicting how each member added impacts dollars spent. So we use a line to assess incremental impact. A slope. A rise over run. <br> 

**How is the line drawn in Two dimensions**
The least squares regression line is a line that best fits the data points in a way that minimizes the sum of the squared vertical distances between the line and the points

the smaller the **standard error** the better you model is at predicting incremental dollar gain per new org member. The larger the standard error perhaps the worse.

**OLS**
The goal of OLS estimation is to find the values of the coefficients that minimize the sum of squared residuals (SSres) between the predicted values and the actual values in the dataset.

**What is a coefficient**
A coefficient represents the change in the response variable that is associated with a one-unit change in the predictor variable, while holding all other predictor variables constant. In a linear regression model, the coefficient represents the slope of the regression line and is often used to make predictions about the value of the response variable based on the value of the predictor variable.

```
Y = β0 + β1*X + ε
SSE = ∑(Yi - Ŷi)^2 // how much is prediction off

```

To estimate the coefficients, we can use the following formulas:

```
β1 = ∑(Xi - Xbar)(Yi - Ybar) / ∑(Xi - Xbar)^2 // slopish

β0 = Ybar - β1*Xbar


//where Xbar and Ybar are the sample means of X and Y, respectively.
```

The slope of a straight line is constant, so the derivative of a straight line with respect to its slope will always be a constant value. In the case of linear regression, the objective is to find the values of the regression coefficients (i.e., the intercept and slope of the line) that minimize the sum of squared errors.

```
Again SSE = ∑(Yi - Ŷi)^2
```

where Yi is the observed value of the response variable for the i-th observation, and Ŷi is the predicted value of the response variable based on the linear regression model, which is given by:

```
Ŷi = β0 + β1 * Xi
```

To find the values of β0 and β1 that minimize SSE, we can take partial derivatives of SSE with respect to β0 and β1, respectively, and set them equal to zero.

The partial derivative of SSE with respect to β0 can be written as:


```
∂SSE / ∂β0 = -2 ∑(Yi - Ŷi)
```

To find the value of β0 that minimizes SSE, we set this partial derivative equal to zero and solve for β0:

```
∂SSE / ∂β0 = -2 ∑(Yi - Ŷi) = 0
```

Solving for β0, we get:

```
β0 = Ybar - β1 * Xbar
```

where Ybar and Xbar are the sample means of Y and X, respectively.

Similarly, the partial derivative of SSE with respect to β1 can be written as:

```
∂SSE / ∂β1 = -2 ∑(Yi - Ŷi) * Xi
```

To find the value of β1 that minimizes SSE, we set this partial derivative equal to zero and solve for β1:

```
∂SSE / ∂β1 = -2 ∑(Yi - Ŷi) * Xi = 0
```
## Standard Error (ε)
---

Epsilon (ε) typically refers to the residual errors in a regression model. Residual errors are the differences between the actual observed values of the response variable and the predicted values of the response variable from the regression model. In other words, epsilon is a vector of individual errors, one for each observation in the dataset. The residual errors are denoted by εi, where i represents the i-th observation.

On the other hand, SSE (sum of squared errors) is a measure of the overall goodness of fit of the regression model. It is the sum of the squared residual errors across all observations in the dataset, i.e., SSE = Σ(εi)², where Σ represents the sum over all observations.

In summary, epsilon represents the residual errors for each observation in the dataset, while SSE is a measure of the overall goodness of fit of the regression model based on the sum of the squared residual errors.
In summary, correlated errors can occur when there are systematic patterns in the residuals that are related to some other variable in the dataset.

When the assumption of independent errors holds, the ordinary least squares (OLS) method for minimizing SSE is valid and efficient. OLS is a method that estimates the values of the regression coefficients by minimizing the sum of squared errors, which is a measure of the difference between the observed values and the predicted values of the response variable.