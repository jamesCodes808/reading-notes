# Linear Regression

### Can you explain the basic concept of linear regression and its purpose in the context of machine learning and data analysis?

The basic concept of linear regression is its a way to find a straight line, or relationships, within a set of scattered data points and variables, which is then used to predict new data points. Following are some common terms used when working with linear regression:


- Best Fit – the straight line in a plot that minimizes the deviation between related scattered data points.

- Coefficient – also known as a parameter, is the factor a variable is multiplied by. In linear regression, a coefficient represents changes in a Response Variable (see below).

- Coefficient of Determination – the correlation coefficient denoted as 𝑅². Used to describe the precision or degree of fit in a regression. 

- Correlation – the relationship between two variables in terms of quantifiable strength and degree, often referred to as the ‘degree of correlation’.  Values range between -1.0 and 1.0. 

- Dependent Feature – a variable denoted as y in the slope equation y=ax+b. Also known as an Output, or a Response. 

- Estimated Regression Line – the straight line that best fits a set of scattered data points.

- Independent Feature – a variable denoted as x in the slope equation y=ax+b. Also known as an Input, or a predictor. 

- Intercept – the location where the Slope intercepts the Y-axis denoted b in the slope equation y=ax+b. 

- Least Squares – a method of estimating a Best Fit to data, by minimizing the sum of the squares of the differences between observed and estimated values.

- Mean – an average of a set of numbers, but in linear regression, Mean is modeled by a linear function.

- Ordinary Least Squares Regression (OLS) – more commonly known as Linear Regression. 

- Residual – vertical distance between a data point and the line of regression (see Residual in Figure 1 below).

- Regression – estimate of predictive change in a variable in relation to changes in other variables (see Predicted Response in Figure 1 below).

- Regression Model – the ideal formula for approximating a regression.

- Response Variables – includes both the Predicted Response (the value predicted by the regression) and the Actual Response, which is the actual value of the data point (see Figure 1 below).

- Slope – the steepness of a line of regression. Slope and Intercept can be used to define the linear relationship between two variables: y=ax+b.

- Simple Linear Regression – a linear regression that has a single independent variable.

Within the context of machine learning and data analysis, linear regression is used when we need to predict data based on other variables or features. Such as predicting how a person's happiness relates to their education level.

### Describe the process of implementing a linear regression model using Python’s Scikit Learn library, including the necessary steps and functions.

1. We first need to import the LinearRegression Class from sklearn.linear_model, numpy and matplotlib.pylot. This LinearRegression Class has default parameters.
```python
from sklearn.linear_model import LinearRegression
import numpy as np
import matplotlib.pyplot as plt

# default parameters for show
sklearn.linear_model.LinearRegression(fit_intercept=True, normalize=False, copy_X=True)
``` 

    - ```fit_interceptbool, default=True``` : Calculate the intercept for the model. If set to False, no intercept will be used in the calculation.

    - ```normalizebool, default=False``` : Converts an input value to a boolean. 

    - ``` copy_Xbool, default=True ``` : Copies the X value. If True, X will be copied; else it may be overwritten.

2. we need a random array of data, in this we're using a numpy array. And plotting with matplotlib 

```python
rnstate = np.random.RandomState(1)
x = 10 * rnstate.rand(50)
y = 2 * x - 5 + rnstate.randn(50)
plt.scatter(x, y);
plt.show()
```

3. Create a linear regression model based the positioning of the data and Intercept, and predict a Best Fit::

```python
model = LinearRegression(fit_intercept=True)
model.fit(x[:, np.newaxis], y)

xfit = np.linspace(0, 10, 1000)
yfit = model.predict(xfit[:, np.newaxis])

```

4. Plot the estimated linear regression line with matplotlib::

```python
plt.scatter(x, y)
plt.plot(xfit, yfit);
plt.show()
```


### What is the purpose of splitting the dataset into train and test sets, and how does this contribute to the evaluation of a machine learning model’s performance?

The purpose of splitting the dataset into train and tests sets is because we want the training data to contain a known output which a model learns, and the test data is used in order to test the model's predictions.

In a machine learning model's performance, when we split the dataset, we are doing this to prevent overfitting or underfitting, which will affect the predictability in the model. Overfitting/underfitting refers to the process of fitting the model on the train data. 

When we have overfitting it means that the model is trained too well and is fit too close to the training dataset, when underfitting its not trained well enough and misses predictability and trends with the data.

## Things I want to know more about

- I'd like to learn more machine learning and data analytic concepts. Maybe build a foundation to understand what I am doing here better.


>References
>
>[How To Run Linear Regressions In Python Scikit-learn](https://www.activestate.com/resources/quick-reads/how-to-run-linear-regressions-in-python-scikit-learn/)
>
>[Linear Regression in Python](https://realpython.com/linear-regression-in-python/)
>
>[Train/Test Split and Cross Validation in Python](https://towardsdatascience.com/train-test-split-and-cross-validation-in-python-80b61beca4b6)