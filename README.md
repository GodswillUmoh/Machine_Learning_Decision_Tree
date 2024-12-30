# Machine_Learning: Decision Tree Regression
_Note: Decision Tree regression is not best for single independent variable. It is more adapted to high dimensional variable_

## Why feature Scaling is not applied in Decision Tree Regression
_Feature scaling is not applied in decision trees because decision trees are scale-invariant. Here's why:_

### 1. Decision Trees Split Based on Thresholds
>Decision trees create splits in the dataset based on thresholds of feature values.
>These thresholds are determined by comparing feature values directly, not by their magnitudes or units.
> 
>For example:
>If a feature has values ranging from 10 to 1000, the tree may decide to split at value > 500. The magnitude of the values doesn’t affect the split.

### 2. Feature Scaling Doesn't Affect Information Gain
> Whether a feature's range is [0, 1] or [100, 1000], the splits and decisions remain the same.

### 3. No Distance-Based Computations
> Models like Support Vector Machines (SVM), k-Nearest Neighbors (k-NN), and gradient descent-based algorithms depend on distance computations, where scaling ensures that one feature doesn't dominate due to its range.
> Decision trees, however, don’t rely on distances, so scaling is unnecessary.
>

## Python codes for building Decision Tree model

### Importing the libraries
```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
```

### Importing the dataset
```python
dataset = pd.read_csv('Position_Salaries.csv')
X = dataset.iloc[:, 1:-1].values
y = dataset.iloc[:, -1].values
```

### Training the Decision Tree Regression model on the whole dataset
```python
# This code can work for more than one features
from sklearn.tree import DecisionTreeRegressor
regressor = DecisionTreeRegressor(random_state = 0)
regressor.fit(X, y)
```

### Predicting a new result
```python
# predicting a single level of 6.5
regressor.predict([[6.5]])
```

### Visualising the Decision Tree Regression results (higher resolution)
```python
X_grid = np.arange(min(X), max(X), 0.1)
X_grid = X_grid.reshape((len(X_grid), 1))
plt.scatter(X, y, color = 'red')
plt.plot(X_grid, regressor.predict(X_grid), color = 'blue')
plt.title('Truth or Bluff (Polynomial Regression)')
plt.xlabel('Position level')
plt.ylabel('Salary')
plt.show()
```

+ [To view Code in Terminal, Click Here](https://colab.research.google.com/drive/1ppQAms1Pas2OG2_whiKTmVmDuzNWJnNq#scrollTo=awOyDi-RrJMH)
  
