# Day 38: Random Sample Imputation & Missing Indicator

## Overview
Explored advanced missing value imputation techniques, focusing on random sample imputation for both numerical and categorical data, and introduced missing indicator features to enhance model performance.

## What I Learned
- **Random Sample Imputation**: Filling missing values by randomly sampling from existing non-missing values in the same column, preserving the original data distribution.
- **Numerical & Categorical Handling**: Applied random sample imputation to both types of features.
- **Missing Indicator**: Created binary features indicating where data was missing, allowing models to learn from the missingness pattern.
- **Comparison & Visualization**: Compared distributions before and after imputation using KDE plots, boxplots, and variance analysis.

## Key Implementation
```python
# Random sample imputation for numerical columns
X_train['Age_Imputed'][X_train['Age_Imputed'].isnull()] = (
    X_train['Age'].dropna().sample(X_train['Age'].isnull().sum(), random_state=42).values
)

# Random sample imputation for categorical columns
X_train['GarageQual_Imputed'][X_train['GarageQual_Imputed'].isnull()] = (
    X_train['GarageQual'].dropna().sample(X_train['GarageQual'].isnull().sum()).values
)

# Adding missing indicator
from sklearn.impute import MissingIndicator
mi = MissingIndicator()
X_train_missing = mi.fit_transform(X_train)
X_train['Age_Na'] = X_train_missing
```

## Skills Developed
- Advanced imputation strategies for missing data
- Preserving data distribution during imputation
- Creating and using missing indicators in ML pipelines
- Visualizing and comparing imputed vs original data

## Next Steps
Apply KNN and multivariate imputation techniques for even more robust handling of missing data in future projects.