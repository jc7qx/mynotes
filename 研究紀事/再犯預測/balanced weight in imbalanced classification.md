#imbalancedclassification

Balanced weight of majority and minority classes is modified to achieve better model results during model training process.

balanced weight methods penalize the wrong predictions on the minority class by giving more weight to the loss function.

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


