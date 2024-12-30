# Machine_Learning: Decision Tree Regression

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
