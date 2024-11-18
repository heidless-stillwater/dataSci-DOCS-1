
# Mathematical Notation

$$
mean\ absolute\ error = \sum_{i=1}^D|x_i - y_i |
$$

## linear regression equation
## 5-1-1/linear regression

$$
\mu\{Y|X\} = \beta_0 + \beta_1X\\\
\\\
\mu = mean\\\
\beta_0 = intercept\\\
\beta_1 = slope\\\
\mu\ and\ the\ Betas (\beta_i)\ are\ Population\ Parameters
$$
NB: We can never know the true value of Population Parameters

Differentiate between Population Parameters and their esimates we use the '^' symbol

$$
\hat{\mu}\{Y|X\} = \hat{\beta_0} + \hat{\beta_1}X\\\
\\\
	y = \hat{\beta_0} + \hat{\beta_1}X
$$


$$
\hat{\mu}\{Y|X\} = \hat{\beta}_0 + \hat{\beta}_1X
$$

The calculation is Beta 0 hat, Beta 1 hat, and mu hat, are all parameter estimates

Simplified representation:

$$
y = \hat{\beta}_0 + \hat{\beta}_1X
$$


$$
\mu\{Y|X\} = \beta_0 + \beta_1X\\\
\\\
\mu = mean\\\
\beta_0 = intercept\\\
\beta_1 = slope\\\
\mu\ and\ the\ Betas (\beta_i)\ are\ Population\ Parameters
$$

#### categorical data
- i.e.is subscription (yes or no)

<span style="color: #7fff7f">estimating the the PROBABILITY of an outcome</span>
$$
\mu\{Y|X\} = Prob(Y=1|X) = p
$$
$$
g(p) = \beta_0 + \beta_1X
$$



## residual
$$
Redidual = Observed - Predicted\\\
\\\
\epsilon_i = y_i - \hat{y_i}
$$


### Sum of Squared Residuals (SSR)
The sum of squared residuals, or SSR, is the sum of the squared differences between each observed value and the associated predicted value.
$$
\Sigma^n_{i=1}(Observed - Predicted)^2\\\
\\\
	\Sigma^n_{i=1}(y_i - \hat{y_i})^2
$$

### Ordinary Least Squares estimation
OLS, is a method that minimizes the sum of squared residuals to estimate parameters in a linear regression model.

<span style="color: #7fff7f">**The SUM of the residuals is always equal to 0 for OLS estimators**
</span>
$$
\hat{y} = \widehat{\beta_0} + \widehat{\beta_1}X
$$

We will NEVER know the exact parameter.

Parameters (Betas) are a characteristic of a POPULATION

# Explore ordinary least squares
[coursera: Explore ordinary least squares](https://www.coursera.org/learn/regression-analysis-simplify-complex-data-relationships/supplement/WC5CJ/explore-ordinary-least-squares)

[Parameter Estimation - Ordinary Least Squares Method
](https://www.geo.fu-berlin.de/en/v/soga-py/Basics-of-statistics/Linear-Regression/Simple-Linear-Regression/Parameter-Estimation/index.html)

## Formula and notation review
An estimate based on simple linear regression can be represented mathematically as:
$$
\hat{y} = \hat{intercept} + \hat{slope}*X
$$
$$
\hat{y} = \hat{\beta_0} + \hat{\beta_1}X
$$

Remember that the hat symbol indicates that the<span style="color: #7fff7f"> **beta coefficients are just estimates.**</span> As a result, the <span style="color: #7fff7f">**y-values**</span> derived from the regression model are also just estimates. 

A common technique for calculating the coefficients of a linear regression model is called ordinary least squares, or OLS. 

<span style="color: #7fff7f">Ordinary Least Squares</span> estimates the beta coefficients in a linear regression model by minimizing a measure of error called <span style="color: #7fff7f">The Sum of Squared Residuals</span>. 

You can calculate the sum of squared residuals via this formula:
$$
\Sigma^n_{i=1}(Observed - Predicted)^2\\\
\\\
\Sigma^n_{i=1}(y_i - \hat{y_i})^2\\\
\\\
\Sigma\ denotes\ sum
$$

## Minimizing the sum of squared residuals (SSR)
Find the best-fit line within a scatterplot of observations. 

For different values of ${\beta_0}$ & ${\beta_1}$
- calculate the predicted value
- calculate the residuals for each point
- square each of the residuals by multiplying them by themselves, and then adding them all together to calculate the <span style="color: #7fff7f">**sum of squared residuals.**</span>

Try out different values for ${\beta_0}$ & ${\beta_1}$ to iterate closer to the best-fit line.

The lower the SSR the BETTER

Manually, this is trial & error.

Python can iterate through many possible lines to find the best fit 

## Estimating beta coefficients

Through advanced math, some formulas have been derived to <span style="color: #7fff7f">**find the beta coefficients that minimize error.**</span>

There are multiple ways to write out the formulas for finding the beta coefficients. For simple linear regression, one way to write the formulas is as follows:

$$
\hat{\beta_1} = 
	\frac
	{\Sigma^N_{i=1}(X_i-\bar{X})(Y_i-\bar{Y})}
	{\Sigma^N_{i=1}(x_i - \bar{x})^2}
\\\
\\\
\hat{\beta_0} = \bar{Y} - \hat{\beta_1}\bar{x}
$$