# Machine_Learning: Decision Tree Regression

## Why feature Scaling is not applied in Decision Tree Regression
_Feature scaling is not applied in decision trees because decision trees are scale-invariant. Here's why:_

> ## 1. Decision Trees Split Based on Thresholds
>Decision trees create splits in the dataset based on thresholds of feature values.
>These thresholds are determined by comparing feature values directly, not by their magnitudes or units.
> 
>For example:
>If a feature has values ranging from 10 to 1000, the tree may decide to split at value > 500. The magnitude of the values doesn’t affect the split.
