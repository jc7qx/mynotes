The best hyperparameters will vary between datasets, so we have to perform optimization (also called model tuning) separately on each datasets.

we might optimize in a random forest are the number of decision trees, the maximum depth of each decision tree, the maximum number of features considered for splitting each node, and the maximum number of data points required in a leaf node.

They strictly control the fit of the model and this means, for each dataset, there is a unique set of optimal hyperparameters to be found

a Grid search fits a model using every single combination of these hyperparameters. What is more, in each fit, the Grid search uses cross-validation to account for overfitting. After all combinations are tried, the search retains the parameters that resulted in the best score so that you can use them to build your final model.

Random search randomly samples hyperparameters and tries to get closer to the best set.

Scikit-learn provides `GridSearchCV` and `RandomizedSearchCV` classes that make this process a breeze.

