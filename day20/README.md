# Day 20: Exploratory Data Analysis (EDA) - Univariate Analysis

## Overview
Comprehensive univariate analysis on both Titanic and TMDB movie datasets, mastering visualization techniques for categorical and numerical data to uncover patterns and insights.

## What I Learned
- **Univariate Analysis**: Single variable exploration techniques
- **Categorical Visualization**: Bar charts, count plots, and pie charts
- **Numerical Visualization**: Histograms, distribution plots, and box plots
- **Outlier Detection**: Using box plots to identify anomalies
- **Data Type Handling**: Converting date columns and data cleaning

## Key Implementation
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Categorical Data Visualization
df['Survived'].value_counts().plot(kind='bar')
sns.countplot(x='Pclass', data=df)
df['Survived'].value_counts().plot(kind='pie', autopct='%.2f%%')

# Numerical Data Visualization
plt.hist(df['Fare'])
sns.displot(df['Age'], kde=True)
sns.boxplot(df['Fare'], orient='h')

# Data preprocessing
df['release_date'] = pd.to_datetime(df['release_date'])
numerical_cols = df.select_dtypes(include=['int','float']).columns
```

## Datasets Analyzed
- **Titanic Dataset**: Passenger survival analysis
  - Categorical: Survived, Pclass distribution
  - Numerical: Age, Fare distributions
- **TMDB Movies Dataset**: Movie characteristics analysis
  - Categorical: Movie titles frequency
  - Numerical: ID, popularity, vote_count, vote_average

## Visualization Techniques Mastered
- **Bar Charts**: Category frequency analysis
- **Pie Charts**: Proportion visualization with percentages
- **Histograms**: Distribution shape analysis
- **Distribution Plots**: Kernel density estimation
- **Box Plots**: Quartile analysis and outlier detection

## Key Insights Discovered
- **Titanic**: More passengers died than survived, majority in 3rd class
- **Age Distribution**: Normal distribution with some missing values
- **Fare Distribution**: Right-skewed with high variability
- **Movies**: Anomalies detected in vote_average below 4.5
- **Outliers**: Successfully identified using box plot analysis

## Skills Developed
- Statistical visualization interpretation
- Outlier detection and analysis
- Data distribution understanding
- Chart selection for different data types
- Pattern recognition in univariate data

## Next Steps
This univariate foundation will enable bivariate and multivariate analysis for deeper insights and