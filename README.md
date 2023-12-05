# How to quantify how good your model is?
## Coefficient of determination (R-squared)
R-squared quantifies how strong that linear relationship is. It is defined as the proportion of the variance in the response variable that is predictable from the explanatory variable.
- 1: perfect fit
- 0: your model is no better than randomness

For simple linear regression it is simply the correlation between the explanatory and response variables, squared.

## Residual standard error (RSE)
The residual is the difference between a predicted value and an observed value. The RSE is a measure of how much the predictions are typically wrong. It has the same unit as the response variable. 

A related, but less commonly used metric is the mean squared error (MSE). As the name suggests, MSE is the squared residual standard error: $MSE = RSE^2$

## Root-mean-square error (RMSE)
The root-mean-square error performs the same task as residual standard error, namely quantifying how inaccurate the model predictions are, but is worse for comparisons between models. You need to be aware that RMSE exists, but typically you should use RSE instead.

# How to interpret if the model is a good fit?
If a linear regression model is a good fit, then the residuals are approximately normally distributed, with mean zero.

##  Residuals vs. fitted
The first diagnostic plot is of residuals versus fitted values. If residuals met the assumption that they are normally distributed with mean zero, then the trend line should closely follow the y equals zero line on the plot.

## Q-Q plot
The second diagnostic plot is called a Q-Q plot. It shows whether or not the residuals follow a normal distribution. On the x-axis, the points are quantiles from the normal distribution. On the y-axis, you get the sample quantiles, which are the quantiles derived from your dataset. If the points track along the straight line, they are normally distributed. If not, they aren't.

## Scale-location plot
The third plot shows the square root of the standardized residuals versus the fitted values. It's often called a scale-location plot. This plot shows whether the size of the residuals gets bigger or smaller compared to the fitted values.

## How much do the explanatory variables impact the model?
## Leverage
Leverage measures how unusual or extreme the explanatory variables are for each observation. Very roughly, high leverage means that the explanatory variable has values that are different from other points in the dataset. 

## Influence
Influence measures how much a model would change if each observation was left out of the model calculations, one at a time. That is, it measures how different the prediction line would look if you would run a linear regression on all data points except that point, compared to running a linear regression on the whole dataset.

The standard metric for influence is Cook's distance, which calculates influence based on the residual size and the leverage of the point.