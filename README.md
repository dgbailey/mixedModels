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

## Independence of errors
---

When the assumption of independent errors holds, the ordinary least squares (OLS) method for minimizing SSE is valid and efficient. OLS is a method that estimates the values of the regression coefficients by minimizing the sum of squared errors, which is a measure of the difference between the observed values and the predicted values of the response variable.

**If your residuals are still correlated is your predictor variable(s) really doing a good job predicting?** Is your model valid?

There are several situations where the residuals in a regression model might not be independent. Here's an example:

Suppose you are building a model to predict housing prices based on various features of a house, such as square footage, number of bedrooms, and location. You collect data from a real estate website and build a linear regression model to predict housing prices.

However, you notice that there is some correlation between the residuals of the model, which violates the assumption of independence. This could occur if the data from the real estate website is clustered by neighborhood, and there are unobserved neighborhood-level factors that affect housing prices, such as school quality or crime rates. If the model does not include these neighborhood-level factors, the residuals might be correlated within each neighborhood, leading to violation of the assumption of independence.

## Equal Variance of errors
---

**How well does your model predict across the entire range of possible observed values?**<br>
Heteroscedasticity can occur in various real-world scenarios where the variance of the error terms changes across the range of the independent variables. Here's an example:

Suppose you are analyzing the relationship between a person's age (independent variable) and their income (dependent variable). You collect data from a sample of individuals ranging in age from 18 to 65. You run a linear regression model to estimate the effect of age on income.

If the variance of the error term is not constant across all values of age, you may observe heteroscedasticity in the data. For example, you may find that the variance of the errors increases as age increases, indicating that the residuals are more spread out for older individuals. This could occur if older individuals have more diverse sources of income than younger individuals, leading to a wider range of income levels and greater variance in the errors.

## Normality of Errors
---
The assumption of normality of the residuals. 

When performing regression analysis, the estimated coefficients (also known as regression coefficients or beta coefficients) represent the estimated relationships between the independent variables and the dependent variable

To assess the uncertainty associated with these estimated coefficients, confidence intervals are constructed. A confidence interval provides a range of plausible values for the coefficient, along with an associated level of confidence. For example, a 95% confidence interval for a coefficient means that we are 95% confident that the true population coefficient lies within that interval.

In ordinary least squares (OLS) regression, the standard errors of the estimated coefficients are calculated based on the assumption that the errors (or residuals) follow a normal distribution with constant variance. These standard errors are then used to construct confidence intervals around the estimated coefficients.

**The estimated coefficients are obtained from a single sample of data, and they are used to make inferences about the population parameters.** However, because we only have one sample, there is uncertainty associated with the estimated coefficients. The sampling distribution helps us understand this uncertainty by considering the range of estimated coefficients that we would obtain if we were to repeat the sampling process multiple times.

The shape of the sampling distribution depends on various factors, including the properties of the data and the underlying assumptions of the regression model. Under the assumption of normality, the sampling distribution of the estimated coefficients is often assumed to be approximately normal, especially for large sample sizes. In such cases, we can use the properties of the normal distribution to construct confidence intervals and perform hypothesis tests.

### But I thought we were using partial derivitives to compute coefficients that minimize something? How does this fit in with standard errors? 
---
The partial derivatives are used to find the values of the regression coefficients that minimize the sum of squared residuals. Once the estimates of the coefficients are obtained, the standard errors are calculated to assess the uncertainty associated with these estimates.

The standard errors quantify the variability of the estimated coefficients and reflect the spread of the coefficient estimates around their true population values. They provide a measure of how much the estimated coefficients are likely to vary if the regression analysis were repeated on different samples from the same population.

The standard errors can be calculated using various methods, including the matrix algebra approach or the formula-based approach. The most common method is based on the assumption that the errors (residuals) are independently and normally distributed with constant variance. Under this assumption, the standard errors are estimated using the residuals and the properties of the observed data.

By estimating the standard errors, we obtain a measure of uncertainty associated with the estimated coefficients. These standard errors are then used in various statistical procedures, such as hypothesis testing and constructing confidence intervals, to make statistical inferences about the population parameters and assess the significance of the estimated relationships.


## Constant variance vs. correlated residuals

Constant variance and independence of residuals are related but distinct concepts in regression analysis.

Constant variance, also known as homoscedasticity, means that the variability of the residuals is consistent across all levels of the independent variables. In other words, the spread or dispersion of the residuals should be constant throughout the range of the predictors. This assumption is important because it ensures that the errors have a consistent level of variability and that the model's predictions are equally reliable across the entire range of the independent variables.

On the other hand, independence of residuals refers to the lack of correlation or dependence between the residuals. It assumes that the residuals for different observations are not systematically related to each other. In other words, the value of the residual for one observation does not provide any information about the value of the residual for another observation. Independence is crucial because it allows us to make valid statistical inferences, conduct hypothesis tests, and construct reliable confidence intervals.

## Efficiency 

**precision and reliability of the estimated coefficients.**

In the context of regression analysis, efficiency refers to the statistical efficiency of an estimator, specifically the regression coefficient estimates. An efficient estimator is one that achieves the smallest possible variance among all unbiased estimators.

In ordinary least squares (OLS) regression, the estimated coefficients are the least squares estimates that minimize the sum of squared residuals. ***These estimates are unbiased, meaning that on average, they are equal to the true population values**. However, among all unbiased estimators, the OLS estimates are also the most efficient when certain assumptions are met.

When the assumptions of OLS regression, such as linearity, independence, constant variance, and normality of errors, are met, **the OLS estimators are not only unbiased but also the most efficient. In this case, they achieve the smallest possible variances, making them highly desirable for inference and hypothesis testing.**

## Sampling distributions for confidence intervals
Normality helps establih a probabalistic range of possible coefficient values?
## Tests

1. Graphical

it's worth considering graphical methods, such as histograms, Q-Q plots, and kernel density plots, to visually assess the normality of residuals.


## Test Statistics

In hypothesis testing, we start with a null hypothesis, which is a statement we want to test. The test statistic is calculated based on the observed sample data and is designed to summarize the evidence against the null hypothesis.

A test statistic quantifies the evidence against the null hypothesis by summarizing the relationship between the observed data and the hypothesis being tested. It provides a standardized measure that allows for statistical decision-making in hypothesis testing.

The test statistic is chosen in such a way that it has a known distribution under the null hypothesis. This distribution is typically derived based on theoretical considerations or statistical assumptions. The choice of the test statistic depends on the nature of the hypothesis being tested and the specific statistical test being performed.

*So in regression, the coefficients are the test statistics*

No, in regression, the coefficients themselves are not considered test statistics. The coefficients in regression analysis represent the estimated parameters that describe the relationship between the independent variables and the dependent variable.

In hypothesis testing in regression analysis, the test statistics are typically derived from the coefficients to assess their significance. These test statistics are used to determine whether the estimated coefficients are statistically different from zero.

The most commonly used test statistic in regression analysis is the t-statistic. The t-statistic is calculated by dividing the estimated coefficient by its standard error. **It measures the number of standard errors the estimated coefficient is away from zero.(no relationship)**

The t-statistic follows a t-distribution, which has a specific shape determined by the degrees of freedom. The degrees of freedom depend on the sample size and the number of independent variables in the regression model.

To determine the significance of a coefficient, you compare the absolute value of the t-statistic to critical values from the t-distribution or calculate the associated p-value. If the absolute value of the t-statistic exceeds the critical value or if the p-value is smaller than the predetermined significance level (e.g., 0.05), the coefficient is considered statistically significant, indicating that it is unlikely to be zero in the population.

### Are coefficients effect sizes?

No, coefficients in regression analysis are not effect sizes. Effect sizes and coefficients serve different purposes and convey different information.

In regression analysis, coefficients represent the estimated parameters that quantify the relationship between the independent variables and the dependent variable. They indicate the change in the dependent variable associated with a one-unit change in the corresponding independent variable, while holding other variables constant.

The interpretation of coefficients depends on the specific context and scale of the variables. For example, in a simple linear regression with one independent variable, the coefficient represents the slope of the regression line, indicating the change in the dependent variable for each unit change in the independent variable.

Effect sizes, on the other hand, measure the magnitude of the relationship between variables. They provide a standardized measure that allows for comparisons across different studies or different variables. Effect sizes capture the strength or magnitude of the relationship, regardless of the scale of the variables.

Commonly used effect size measures in regression analysis include the coefficient of determination (R-squared), which represents the proportion of variance in the dependent variable explained by the independent variables, and the standardized regression coefficients (beta coefficients), which indicate the standardized change in the dependent variable for a one-standard-deviation change in the independent variable.




Do you do two sided hypothesis tests for regression?


---

## Limitations of test statistic evaluation (p values)

Dependence on sample size: The p-value is influenced by the sample size. Large sample sizes tend to yield small p-values even for small effect sizes. This can result in statistically significant findings that may not have practical significance.

Multiple comparisons problem: Conducting multiple hypothesis tests increases the chance of obtaining false positives. When multiple tests are performed simultaneously, there is a higher likelihood of finding statistically significant results by chance alone. Adjustments such as the Bonferroni correction or controlling the family-wise error rate can be used to address this issue.

Misinterpretation and miscommunication: P-values are often misunderstood or misinterpreted, leading to incorrect conclusions or exaggerated claims. There is a risk of treating p-values as measures of truth or evidence, rather than as tools for quantifying the strength of evidence against the null hypothesis.

**Let's explore the mathematical reasoning behind the influence of sample size on the p-value.**

In hypothesis testing, the p-value is calculated as the probability of obtaining a test statistic as extreme as, or more extreme than, the observed value, assuming the null hypothesis is true. In many cases, the test statistic follows a known distribution under the null hypothesis.

For simplicity, let's consider a one-sample t-test where we are testing the mean of a population (null hypothesis) based on a sample mean. The test statistic in this case is the t-statistic. The formula to calculate the t-statistic is:
```
t = (x̄ - μ) / (s / √n)
```

where:

x̄ is the sample mean
μ is the hypothesized population mean under the null hypothesis
s is the sample standard deviation
n is the sample size
To calculate the p-value, we need to determine the probability of observing a t-statistic as extreme as, or more extreme than, the observed value, assuming the null hypothesis is true.

As the sample size (n) increases, the denominator of the t-statistic (s / √n) decreases. This means the t-statistic becomes larger for the same difference between the sample mean and the null hypothesis mean.

A larger t-statistic leads to a smaller p-value because the tails of the distribution (e.g., t-distribution) become narrower, and the probability of observing values as extreme as, or more extreme than, the observed t-statistic decreases. This is because larger sample sizes provide more precise estimates, reducing sampling variability and making it easier to detect small deviations from the null hypothesis.

In other words, with a larger sample size, it becomes easier to achieve statistical significance (i.e., small p-value) because the increased precision allows for a more accurate estimation of the population parameter.

In regression analysis, the influence of sample size on the p-values is similar to other hypothesis tests. However, there are a few specific considerations to keep in mind.

---


### How does this apply to regression analysis?

In linear regression, the p-values are typically associated with the significance of the regression coefficients (β coefficients) that represent the relationship between the predictor variables and the response variable.

When performing hypothesis tests on regression coefficients, such as t-tests or F-tests, the test statistics are calculated based on the estimated coefficients, their standard errors, and the distribution assumptions.

The t-test for a regression coefficient tests the null hypothesis that the true population coefficient is zero. The test statistic is calculated as:

```
t = (β - 0) / SE(β)
```

where:

β is the estimated coefficient
SE(β) is the standard error of the coefficient
The p-value associated with the t-test represents the probability of observing a t-statistic as extreme as, or more extreme than, the observed value under the assumption that the true coefficient is zero.

Similar to other hypothesis tests, as the sample size (n) increases in regression analysis, the standard errors tend to decrease. Smaller standard errors result in larger t-statistics, leading to smaller p-values.

With a larger sample size, the precision of the coefficient estimates improves, reducing sampling variability. This increased precision makes it easier to detect small effects, resulting in smaller p-values and potentially finding statistically significant relationships even for small effect sizes.

### Formalizations of standard error

The formula for the standard error (SE) of a regression coefficient in linear regression depends on the specific regression model being used. In the case of simple linear regression (with one predictor variable), the formula for the standard error of the coefficient is:

```
SE(β) = sqrt(Σ(y - ŷ)^2 / ((n - 2) * Σ(x - x̄)^2))
```

where:

Σ represents the sum of the values<br>
y is the observed response variable<br>
ŷ is the predicted response variable based on the regression model<br>
n is the sample size<br>
x is the predictor variable<br>
x̄ is the mean of the predictor variable<br>
In multiple linear regression (with multiple predictor variables), the standard error of each coefficient is calculated based on the residual sum of squares (RSS) and the design matrix. The formula is more complex and involves matrix algebra. It can be represented as:<br>

```
SE(β) = sqrt(diag(inv(X'X) * RSS / (n - k)))
```

where:

X is the design matrix containing the predictor variables<br>
X' is the transpose of the design matrix<br>
inv() represents the matrix inverse
diag() extracts the diagonal elements of a matrix<br>
RSS is the residual sum of squares<br>
n is the sample size<br>
k is the number of predictor variables in the model<br>


## General linear models