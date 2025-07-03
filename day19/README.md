# Day 19: Data Understanding & Exploration - Titanic Dataset

## Overview
Deep dive into data exploration fundamentals using the famous Titanic dataset, focusing on understanding data structure, identifying patterns, and handling data quality issues.

## What I Learned
- **Data Profiling**: Comprehensive dataset examination techniques
- **Missing Value Analysis**: Identifying and quantifying data gaps
- **Statistical Summary**: Understanding data distributions and relationships
- **Data Quality Assessment**: Detecting duplicates and inconsistencies
- **Correlation Analysis**: Finding relationships between variables

## Key Implementation
```python
import pandas as pd

# Load and explore dataset
df = pd.read_csv('tested.csv')

# Data profiling
df.info()                           # Dataset structure
df.describe()                       # Statistical summary
df.isnull().sum()                   # Missing values count
df.duplicated().sum()               # Duplicate detection

# Correlation analysis
df.select_dtypes(include='number').corr()['Survived']

# Data cleaning
df['Age'].fillna(df['Age'].median()).astype('int64')
```

## Dataset Analysis Results
- **Size**: Titanic passenger data with multiple features
- **Missing Values**: Identified gaps in Age, Cabin, and other columns
- **Data Types**: Mixed numerical and categorical variables
- **Correlations**: Discovered survival relationships with passenger features
- **Duplicates**: Assessed data uniqueness

## Skills Developed
- Systematic data exploration methodology
- Missing value identification strategies
- Statistical analysis of relationships
- Data cleaning and preprocessing techniques
- Correlation interpretation and insights

## Key Insights
- Age has missing values requiring imputation
- Survival correlates with passenger class and demographics
- Cabin column has significant missing data
- No duplicate records found in the dataset

## Next Steps
This foundational analysis sets the stage for advanced feature engineering and machine learning model