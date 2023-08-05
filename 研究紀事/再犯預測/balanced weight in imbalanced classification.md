#imbalancedclassification

Balanced weight of majority and minority classes is modified to achieve better model results during model training process.

balanced weight methods penalize the wrong predictions on the minority class by giving more weight to the loss function.

```python
# 建立資料集  
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

