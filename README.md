# Simple Machine Learning Model implemented in Python 

We present in this repository, a simple Machine Learning Model implemented in Python, we will train a Linear Regression Model and expect to perfom correct on a fresh input. 

## Sample Training Set

As described below, we have X as input and Y as output:

| **X1** | **X2** | **X3** | **Y** |
| :---: | :---: | :---: | :---: |
| 1 | 2 | 3 | **14** |
| 4 | 5 | 6 | **32** |
| 10 | 10 | 10 | **60** |

Given the training set you could easily guess that the output Y is **X1 + 2 * X2 + 3 * X3**.

## How can we generate a Training Set in Python?

```python
from random import randint
TRAIN_SET_LIMIT = 1000
TRAIN_SET_COUNT = 100

TRAIN_INPUT = list()
TRAIN_OUTPUT = list()

for i in range (TRAIN_SET_COUNT):
    a = randint(0, TRAIN_SET_LIMIT)
    b = randint(0, TRAIN_SET_LIMIT)
    c = randint(0, TRAIN_SET_LIMIT)
    function = a + 2*b + 3*c
    TRAIN_INPUT.append([a, b, c])
    TRAIN_OUTPUT.append(function)
```

## Machine Learning Model under Linear Regression

Before we implement a linear regression model, do not forget to install **scikit-learn**, it provides easy to use functions and predefined models which saves a lot of time and work. If you are using a Linux Terminal, type:
```
$ pip install scikit-learn
```
Working with linear regression model is very simple. Create a model, train it and then use it, as described the schematic below:

<p align="center">
  <img src="https://user-images.githubusercontent.com/25873978/64200840-4cf54900-ce5b-11e9-921c-1c7e57bf6c0d.png">
</p>

## Train The Model

As described the code above, we have the training set ready, so create a Linear Regression Model and pass it the training data:

```python
from sklearn.linear_model import LinearRegression

predictor = LinearRegression(n_jobs = -1)
predictor.fit(X = TRAIN_INPUT, y = TRAIN_OUTPUT)
```

## Testbench

For a defined set as **X = [[10, 20, 30]]**, the outcome should be **10 + 2 * 20 + 3 * 30 = 140**. Let's see what we got with a simple testbench:

```python
X_TEST = [[10, 20, 30]]
outcome = predictor.predict(X=X_TEST)
coefficients = predictor.coef_

print('Outcome : {}\nCoefficients : {}'.format(outcome, coefficients))
```
> Outcome: [140.]

> Coefficients: [1. 2. 3.]

The model had access to the training data, through which it calculated the weights to assign to the inputs to arrive at the desired output. On giving test data, it successfully managed to get right answer. 

