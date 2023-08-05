[A Random Forest Classifier with Imbalanced Data](https://medium.com/analytics-vidhya/a-random-forest-classifier-with-imbalanced-data-7ef4d9ebedb8)

#standardize #normalize #standardscaler #onehotencoder #randomforest #imbalancedclassification 
Classifiers do not perform well on unbalanced datasets. They end up correctly classifying the majority class or classes at expense of the minority class.

One way to deal with unbalanced datasets is synthetic minority oversampling (SMOTE). It is an algorithm that generates new sample data by creating synthetic examples that are combinations of the closest minority cases.

For the numeric ones I will be using [StandardScaler from sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html), from the sklearn documentation it will ”Standardize features by removing the mean and scaling to unit variance.” While not necessary for Random Forests, I scaled the data for consistency with my other models.

For my nominal categorical features, I will be using[OneHotEncoder from sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html). This will take each categorical feature with _n_ unique values and create _n_ features corresponding to the _n_ unique values where for each instance the the new feature corresponding to the value of the original feature is given a value of 1, while all the other _n-1_ features are given a value of 0.

## pipeline and defined my preprocessor
數值資料標準化及類別資料正規化

```python
from sklearn.preprocessing import StandardScaler, OneHotEncoder  
from sklearn.compose import ColumnTransformer  
from imblearn.pipeline import Pipeline

numeric_transformer = Pipeline(
	steps=[('scaler', StandardScaler())]
)

categorical_transformer = Pipeline(
	steps=[('onehot', 
		OneHotEncoder(handle_unknown='ignore')
		)
	]
)

preprocessor = ColumnTransformer(
	remainder='drop', 
	transformers=[
		('num', numeric_transformer, cols_to_scale), 
		('cat', categorical_transformer, categorical_features)
	]
)
```