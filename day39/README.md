# Day 39: KNN Imputer for Missing Data

## Overview
Implemented K-Nearest Neighbors (KNN) imputation to handle missing values in the Titanic dataset and compared its effectiveness with SimpleImputer.

## What I Learned
- How KNNImputer fills missing values using the average of nearest neighbors.
- The importance of choosing the right number of neighbors (`n_neighbors`).
- SimpleImputer (mean/median) can sometimes outperform KNNImputer depending on data structure.
- Always compare imputation strategies using model accuracy.

## Key Implementation
```python
from sklearn.impute import KNNImputer, SimpleImputer
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

# KNN Imputation
knn = KNNImputer(n_neighbors=2)
X_train_knn = knn.fit_transform(X_train)
X_test_knn = knn.transform(X_test)
clf = LogisticRegression()
clf.fit(X_train_knn, y_train)
y_pred_knn = clf.predict(X_test_knn)
acc_knn = accuracy_score(y_test, y_pred_knn)

# Simple Imputer for comparison
si = SimpleImputer()
X_train_si = si.fit_transform(X_train)
X_test_si = si.transform(X_test)
clf1 = LogisticRegression()
clf1.fit(X_train_si, y_train)
y_pred_si = clf1.predict(X_test_si)
acc_si = accuracy_score(y_test, y_pred_si)
```

## Skills Developed
- Advanced missing value imputation with KNN
- Model evaluation and comparison of imputation methods
- Understanding when to use KNN vs simple strategies

## Key Takeaway
KNNImputer can capture local patterns but may not always outperform simpler methods. Always validate imputation strategies for your