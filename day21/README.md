# Day 21: Bivariate & Multivariate Analysis - Advanced EDA

## Overview
Advanced exploratory data analysis focusing on relationships between variables using the Iris, Titanic, and Flight datasets. Mastering bivariate and multivariate visualization techniques.

## What I Learned
- **Bivariate Analysis**: Exploring relationships between two variables
- **Multivariate Analysis**: Understanding complex interactions among multiple variables
- **Advanced Visualizations**: Scatter plots, pair plots, heatmaps, and distribution plots
- **Categorical-Numerical Relationships**: Bar plots, box plots, and KDE plots

## Key Implementation
```python
import pandas as pd
import seaborn as sns

# Scatter plots for numerical relationships
sns.scatterplot(x='SepalLengthCm', y='SepalWidthCm', hue='Species', data=df)

# Comprehensive pair plot analysis
sns.pairplot(df, hue='Species')

# Categorical-numerical relationships
sns.barplot(x='Species', y='SepalLengthCm', data=df)
sns.boxplot(x='Species', y='SepalLengthCm', data=df)

# Heatmap for categorical relationships
sns.heatmap(pd.crosstab(titanic['Survived'], titanic['Pclass']))

# Distribution comparison
sns.kdeplot(data=titanic, x='Age', hue='Survived', fill=True)
```

## Datasets Analyzed
- **Iris Dataset**: Species classification patterns
- **Titanic Dataset**: Survival analysis across multiple factors
- **Flight Dataset**: Time series trend analysis

## Visualization Techniques Mastered
- **Scatter Plots**: Numerical-numerical relationships with categorical grouping
- **Pair Plots**: Comprehensive variable relationship matrix
- **Bar Plots**: Categorical-numerical summaries
- **Box Plots**: Distribution comparison across categories
- **Heatmaps**: Categorical relationship intensity
- **KDE Plots**: Probability density comparisons
- **Line Plots**: Temporal trend analysis

## Key Insights Discovered
- **Iris**: Clear species separation in petal measurements
- **Titanic**: Age and class strongly influence survival rates
- **Flight**: Temporal patterns in passenger volume
- **Correlations**: Strong relationships between related measurements

## Skills Developed
- Multi-dimensional data exploration
- Pattern recognition across variable combinations
- Statistical relationship interpretation
- Advanced plotting customization
- Insight extraction from complex visualizations

## Next Steps
These multivariate analysis skills will enhance feature engineering and model selection in upcoming machine learning phases.