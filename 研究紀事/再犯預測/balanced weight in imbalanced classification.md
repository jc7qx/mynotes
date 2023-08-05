#imbalancedclassification

Balanced weight of majority and minority classes is modified to achieve better model results during model training process.

balanced weight methods penalize the wrong predictions on the minority class by giving more weight to the loss function.

## required packages
```python
# Synthetic dataset  
from sklearn.datasets import make_classification
# Data processing  
import pandas as pd  
import numpy as np  
from collections import Counter
# Data visualization  
import matplotlib.pyplot as plt  
import seaborn as sns
# Model and performance  
from sklearn.model_selection import train_test_split, cross_validate, StratifiedKFold  
from sklearn.ensemble import RandomForestClassifier  
from sklearn.linear_model import LogisticRegression  
from sklearn.utils import class_weight  
from sklearn.metrics import classification_report
```

## use `make_classification` to create an imbalanced dataset
```python
# Create an imbalanced dataset  
X, y = make_classification(n_samples=100000, 
	n_features=2, n_informative=2,  
	n_redundant=0, n_repeated=0, n_classes=2, 
	n_clusters_per_class=1,  weights=[0.995, 0.005],
	class_sep=0.5, random_state=0)
# Convert the data from numpy array to a pandas dataframe  
df = pd.DataFrame({'feature1': X[:, 0], 'feature2': X[:, 1], 'target': y})
# Check the target distribution  
df['target'].value_counts(normalize = True)
```
The output shows that we have about 1% of the data in the minority class and 99% in the majority class.
```
0     0.9897
1     0.0103
Name: target, dtype:float64
```

## visulaized the imbalanced data
```python
# Visualize the data  
plt.figure(figsize=(12, 8))  
sns.scatterplot(x = 'feature1', y = 'feature2', hue = 'target', data = df)
```

## Train Test Split
```python
# Train test split  
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
# Check the number of records  
print('training dataset資料比數', X_train.shape[0])  
print('test dataset資料比數', X_test.shape[0])  
print(f"training dataset有{sorted(Counter(y_train).items())[0][1]} 筆資料屬於majority class and {sorted(Counter(y_train).items())[1][1]} 筆資料屬於minority class.")
```

## baseline model
使用cross-validation評估模式效能
使用minority class的recall為效能量度
```python
# Train the random forest model using the imbalanced dataset  
rf = RandomForestClassifier(random_state=0, n_jobs=-1)  
baseline_model_cv = cross_validate(rf, X_train, y_train, cv=StratifiedKFold(n_splits=5), n_jobs=-1, scoring="recall")
# Check the model performance  
print(f"{baseline_model_cv['test_score'].mean():.3f} +/- {baseline_model_cv['test_score'].std():.3f}")
# 0.043 +/- 0.016
```

## weights for dataset
weights for the majority class=$\frac{1}{\frac{79183}{79183+817}}$=1.010
weights for the minority class=$\frac{1}{\frac{817}{79183+817}}$=97.919

