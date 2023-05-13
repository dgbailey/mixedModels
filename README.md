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