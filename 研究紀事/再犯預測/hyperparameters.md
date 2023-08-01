最佳超參數是隨者資料而改變，因此必須要針對每一個資料集來執行超參數的最佳化。

we might optimize in a random forest are the number of decision trees, the maximum depth of each decision tree, the maximum number of features considered for splitting each node, and the maximum number of data points required in a leaf node.

They strictly control the fit of the model and this means, for each dataset, there is a unique set of optimal hyperparameters to be found

a Grid search fits a model using every single combination of these hyperparameters. What is more, in each fit, the Grid search uses cross-validation to account for overfitting. After all combinations are tried, the search retains the parameters that resulted in the best score so that you can use them to build your final model.



Scikit-learn 提供 `GridSearchCV` and `RandomizedSearchCV` 類別可以運用

**RandomSearchCV**
```python
from sklearn.model_selection import RandomizedSearchCV
forest = RandomForestClassifier()
rand_cv = RandomizedSearchCV(forest, param_grid, n_iter=100, cv=3, scoring="accuracy", n_jobs=-1)
```
Random search randomly samples hyperparameters and tries to get closer to the best set. You should never choose your hyperparameters according to the results of the `RandomSearchCV`. Instead, only use it to narrow down the value range for each hyperparameter so that you can provide a better parameter grid to `GridSearchCV`.

**GridSearchCV**
```python
from sklearn.model_selection import GridSearchCV
forest = RandomForestClassifier()
grid_cv = GridSearchCV(forest, new_params, n_jobs=-1)
```

For large datasets, you need to take a different approach. Fortunately, ‘the different approach’ is already covered by Scikit-learn… again. That’s why my next post is going to be on `HalvingGridSearchCV` and `HalvingRandomizedSearchCV`.



