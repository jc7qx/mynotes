Each model in the ensemble is then used to generate a prediction for a new sample and these m predictions are averaged to give the forest’s prediction. Since the algorithm randomly selects predictors at each split, tree correlation will necessarily be lessened.

random forest is very effective on a wide range of problems, but like bagging, performance of the standard algorithm is not great on imbalanced classification problems. In learning extremely imbalanced data, there is a significant probability that a bootstrap sample contains few or even none of the minority class, resulting in a tree with poor performance for predicting the minority class.

1. Standard Random Forest
	`model = RandomForestClassifier(n_estimators=10)`
	`cv = RepeatedStratifiedKFold(n_splits=10, n_repeats=3, random_state=1)`
	`scores = cross_val_score(model, X, y, scoring='roc_auc', cv=cv, n_jobs=-1)`
	`print('Mean ROC AUC: %.3f' % mean(scores))`
2. Random Forest With Class Weighting
	**modifying a decision tree for imbalanced classification is to change the weight that each class has when calculating the “_impurity_” score of a chosen split point. Impurity measures how mixed the groups of samples are for a given split in the training dataset and is typically measured with Gini or entropy. The calculation can be biased so that a mixture in favor of the minority class is favored, allowing some false positives for the majority class. Another approach to make random forest more suitable for learning from extremely imbalanced data follows the idea of cost sensitive learning. Since the RF classifier tends to be biased towards the majority class, we shall place a heavier penalty on misclassifying the minority class. The argument value of ‘_balanced_‘ can be provided to automatically use the inverse weighting from the training dataset, giving focus to the minority class.**
	`model = RandomForestClassifier(n_estimators=10,class_weight='balanced')`
	`cv = RepeatedStratifiedKFold(n_splits=10, n_repeats=3, random_state=1)`
	`scores = cross_val_score(model, X, y, scoring='roc_auc', cv=cv, n_jobs=-1)`
	`print('Mean ROC AUC: %.3f' % mean(scores))`
3. Random Forest With Bootstrap Class Weighting
	 **it might be interesting to change the class weighting based on the class distribution in each bootstrap sample, instead of the entire training dataset. achieved by setting the _class_weight_ argument to the value ‘_balanced_subsample_‘.**
	`model = RandomForestClassifier(n_estimators=10, class_weight='balanced_subsample')`
	`cv = RepeatedStratifiedKFold(n_splits=10, n_repeats=3, random_state=1)`
	`scores = cross_val_score(model, X, y, scoring='roc_auc', cv=cv, n_jobs=-1)`
	`print('Mean ROC AUC: %.3f' % mean(scores))`
4. Random Forest With Random Undersampling
	**Another useful modification to random forest is to perform data resampling on the bootstrap sample in order to explicitly change the class distribution.The [BalancedRandomForestClassifier class](https://imbalanced-learn.org/stable/generated/imblearn.ensemble.BalancedRandomForestClassifier.html) from the imbalanced-learn library implements this and performs random undersampling of the majority class in reach bootstrap sample. This is generally referred to as Balanced Random Forest.**
	`from imblearn.ensemble import BalancedRandomForestClassifier`
	`model = BalancedRandomForestClassifier(n_estimators=10)`
	`cv = RepeatedStratifiedKFold(n_splits=10, n_repeats=3, random_state=1)`
	`scores = cross_val_score(model, X, y, scoring='roc_auc', cv=cv, n_jobs=-1)`
	`print('Mean ROC AUC: %.3f' % mean(scores))`
	