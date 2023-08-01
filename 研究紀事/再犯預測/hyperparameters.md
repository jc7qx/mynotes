最佳超參數是隨者資料而改變，因此必須要針對每一個資料集來執行超參數的最佳化。對每一個資料集嚴格地以資料擬合模型，並以超參數調校方法獲取一組最佳超參數。例如，針對隨機森林(Random Forest)而言，超參數可能包括決策樹數量，每顆決策樹的最大深度，每個節點分支考量的最大影響因子數，及每個葉節點的最大資料數量。





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
a Grid search fits a model using every single combination of these hyperparameters. What is more, in each fit, the Grid search uses cross-validation to account for overfitting. After all combinations are tried, the search retains the parameters that resulted in the best score so that you can use them to build your final model.

For large datasets, you need to take a different approach. Fortunately, ‘the different approach’ is already covered by Scikit-learn… again. That’s why my next post is going to be on `HalvingGridSearchCV` and `HalvingRandomizedSearchCV`.



