# Day 18: Web Scraping with Python & BeautifulSoup

## Overview
Mastering web scraping techniques to extract real-world sports data from ESPN using Python's requests library and BeautifulSoup for HTML parsing.

## What I Learned
- **HTTP Requests**: Making web requests with proper headers and user agents
- **HTML Parsing**: Using BeautifulSoup to parse and navigate HTML structures
- **Element Selection**: Finding specific elements using tags, classes, and attributes
- **Data Extraction**: Extracting text content from web pages programmatically

## Key Implementation
```python
import requests
from bs4 import BeautifulSoup

# Set up proper headers to avoid blocking
headers = {
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36"
}

# Fetch and parse ESPN data
response = requests.get(url, headers=headers)
soup = BeautifulSoup(response.text, 'html.parser')

# Extract specific elements
team_info = soup.find_all('h2')
navigation = soup.find_all('span', {'class': 'Nav__Text'})
```

## Data Sources Scraped
- **ESPN Soccer Teams**: Team information and details
- **Brazilian League Table**: League standings and statistics
- **Sports Navigation**: Menu items and site structure

## Skills Developed
- Web scraping ethics and best practices
- HTML structure analysis and navigation
- CSS selector usage for element targeting
- Handling dynamic web content

## Next Steps
This foundation will enable scraping more complex sports data and building comprehensive dataset for analysis.