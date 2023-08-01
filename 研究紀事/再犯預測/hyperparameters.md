The best hyperparameters will vary between datasets, so we have to perform optimization (also called model tuning) separately on each datasets.

we might optimize in a random forest are the number of decision trees, the maximum depth of each decision tree, the maximum number of features considered for splitting each node, and the maximum number of data points required in a leaf node.

They strictly control the fit of the model and this means, for each dataset, there is a unique set of optimal hyperparameters to be found

a Grid search fits a model using every single combination of these hyperparameters. What is more, in each fit, the Grid search uses cross-validation to account for overfitting. After all combinations are tried, the search retains the parameters that resulted in the best score so that you can use them to build your final model.

Random search randomly samples hyperparameters and tries to get closer to the best set.

Scikit-learn provides `GridSearchCV` and `RandomizedSearchCV` classes that make this process a breeze.

You should never choose your hyperparameters according to the results of the `RandomSearchCV`. Instead, only use it to narrow down the value range for each hyperparameter so that you can provide a better parameter grid to `GridSearchCV`.

For large datasets, you need to take a different approach. Fortunately, ‘the different approach’ is already covered by Scikit-learn… again. That’s why my next post is going to be on `HalvingGridSearchCV` and `HalvingRandomizedSearchCV`.

**RandomSearchCV**
```python
from sklearn.model_selection import RandomizedSearchCV
forest = RandomForestClassifier()
rand_cv = RandomizedSearchCV(forest, param_grid, n_iter=100, cv=3, scoring="accuracy", n_jobs=-1)
```

**GridSearchCV**
```python
from sklearn.model_selection import GridSearchCV
forest = RandomForestClassifier()
grid_cv = GridSearchCV(forest, new_params, n_jobs=-1)
```




