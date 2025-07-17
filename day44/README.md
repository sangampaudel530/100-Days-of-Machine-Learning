# Day 44: Outlier Detection using Percentile Method & Winsorization

## Overview
Explored outlier detection and treatment using the percentile method and winsorization technique on a weight-height dataset to handle extreme values effectively.

## What I Learned
- Using percentiles (1st and 99th) to define outlier boundaries
- Applying winsorization to cap extreme values instead of removing them
- Comparing trimming vs winsorization approaches for outlier handling
- Visualizing the impact of outlier treatment on data distribution

## Key Implementation
```python
# Define outlier boundaries using percentiles
upper_limit = df['Height'].quantile(0.99)
lower_limit = df['Height'].quantile(0.01)

# Winsorization - capping extreme values
df['Height_winsorized'] = np.where(df['Height'] > upper_limit, upper_limit,
                                  np.where(df['Height'] < lower_limit, lower_limit, df['Height']))

# Trimming - removing outliers
new_df = df[(df['Height'] < upper_limit) & (df['Height'] > lower_limit)]
```

## Skills Developed
- Percentile-based outlier detection
- Winsorization technique implementation
- Data preservation vs data removal strategies
- Effective outlier visualization

## Takeaway
Winsorization preserves dataset size while handling outliers, making it useful when you can't afford to lose data