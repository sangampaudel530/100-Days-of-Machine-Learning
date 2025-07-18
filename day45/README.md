# Day 45: Feature Construction and Splitting

## Overview
Explored advanced feature engineering techniques including feature construction and feature splitting to improve model performance on the Titanic dataset.

## What I Learned
- **Feature Construction**: Creating new meaningful features from existing ones
- **Feature Splitting**: Extracting valuable information from text/complex columns
- **Feature Engineering Impact**: Measuring improvement in model accuracy
- **Domain Knowledge Application**: Using business logic to create informative features

## Key Implementation
```python
# Feature Construction - Creating FamilySize
df['FamilySize'] = df['SibSp'] + df['Parch'] + 1

# Creating categorical FamilyType from FamilySize
def family_type(num):
    if num == 1:
        return 0  # single
    elif num <= 4:
        return 1  # small family
    else:
        return 2  # big family

df['FamilyType'] = df['FamilySize'].apply(family_type)

# Feature Splitting - Extracting Salutation from Name
new_df['Salutation'] = new_df['Name'].str.split(',', expand=True)[1].str.split('.', expand=True)[0]

# Analyzing survival rates by salutation
new_df.groupby('Salutation')['Survived'].mean().sort_values(ascending=False)
```

## Skills Developed
- Creating composite features from multiple columns
- Converting numerical features to categorical
- Text processing and string manipulation
- Feature impact evaluation using cross-validation

## Key Insights
- Family size affects survival probability
- Salutations (titles) provide valuable social status information
- Feature engineering can significantly improve model performance
- Domain knowledge is crucial for effective feature creation

## Takeaway
Smart feature engineering often provides more value than complex algorithms - understanding your data deeply leads to