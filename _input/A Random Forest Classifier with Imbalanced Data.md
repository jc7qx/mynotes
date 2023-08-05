[A Random Forest Classifier with Imbalanced Data](https://medium.com/analytics-vidhya/a-random-forest-classifier-with-imbalanced-data-7ef4d9ebedb8)

Classifiers do not perform well on unbalanced datasets. They end up correctly classifying the majority class or classes at expense of the minority class.

One way to deal with unbalanced datasets is ==synthetic minority oversampling (SMOTE==). It is an algorithm that ==generates new sample data by creating synthetic examples that are combinations of the closest minority cases==.

For the numeric ones I will be using ==[StandardScaler from sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)====,== from the sklearn documentation it will ==”Standardize features by removing the mean and scaling to unit variance.”== While not necessary for Random Forests, I scaled the data for consistency with my other models.

