# Day 17: API Data Fetching & Collection

## Overview
Mastering real-world data collection by fetching movie data from The Movie Database (TMDB) API and building a comprehensive dataset through pagination.

## What I Learned
- **API Integration**: Working with RESTful APIs using Python requests
- **Data Pagination**: Efficiently collecting large datasets across multiple pages
- **Error Handling**: Managing API responses and handling missing data
- **Data Export**: Saving collected data to CSV for future analysis

## Key Implementation
```python
import pandas as pd
import requests

# Fetch data from TMDB API with pagination
for i in range(1, 10001):
    url = f'https://api.themoviedb.org/3/movie/popular?api_key={api_key}&page={i}'
    response = requests.get(url)
    # Process and concatenate data
```

## Dataset Created
- **Source**: The Movie Database (TMDB) API
- **Records**: 10,000+ popular movies
- **Features**: Movie ID, title, popularity, release date, overview, vote count, vote average
- **Output**: `tmdb_movies.csv`

## Skills Developed
- API authentication and requests
- Large-scale data collection strategies
- Data concatenation and cleaning
- Handling missing values in real-world data

## Next Steps
This dataset will be used for advanced EDA and machine learning projects