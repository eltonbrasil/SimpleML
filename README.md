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
