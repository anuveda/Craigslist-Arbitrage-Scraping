# Craigslist Scraping Project

## Project Overview
This project involves scraping HTML content from Craigslist and saving it for analysis. The focus is on understanding the structure of the webpage, interacting with the page through sorting and pagination, and fetching listing URLs for further processing.

## Objectives
1. **Interact with the Page-Sorting**:
   - Modify the URL to trigger sorting changes directly.
   - Understand the type of request (GET) and the relevant URL variable ("sort").

2. **Interact with the Page-Pagination**:
   - Navigate through different pages by modifying the URL, specifically the number after "gallery~".

## Methods
1. **Fetching Listing URLs**:
   - Use BeautifulSoup to parse the HTML content and extract the listing URLs.
   - Implement a loop with a delay to avoid getting blocked by the server.

## Results
- Successfully extracted listing URLs from multiple pages on Craigslist.

## Conclusion
- Implemented a web scraping script using BeautifulSoup and requests to fetch and parse HTML content from Craigslist.
- The script can navigate through pages and sort listings by modifying the URL parameters.

## Code Snippet
```python
from bs4 import BeautifulSoup
import requests
import time

headers = {'User-Agent': 'Mozilla/5.0'}
url = 'https://sfbay.craigslist.org/search/zip#search=1~gallery~0~0'
page = requests.get(url, headers)
soup = BeautifulSoup(page.content, 'html.parser')

all_urls = [look_a['href'] for look_a in soup.select('li.cl
