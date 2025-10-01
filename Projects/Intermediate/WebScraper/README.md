# Web Scraper Project

Build a web scraping tool to extract data from websites and save it in structured formats.

## Project Overview

**What you'll build**: A web scraper that can extract specific data from websites, handle different page structures, and save results in various formats.

**What you'll learn**:
- HTTP requests and response handling
- HTML parsing and navigation
- Data extraction and cleaning
- Working with external libraries
- Error handling and retry logic
- Ethical scraping practices

## Project Features

### Core Features
- Send HTTP requests to websites
- Parse HTML content
- Extract specific data elements
- Save data to files (CSV, JSON)
- Handle basic error conditions
- Simple progress tracking

### Advanced Features
- Handle JavaScript-rendered content
- Manage sessions and cookies
- Implement rate limiting and delays
- Handle different file formats
- Batch processing of multiple URLs
- Data validation and cleaning

## Implementation Guide

### Phase 1: Basic Web Requests
**Time**: 2-3 hours

Start with simple HTTP requests:
- Make requests to websites
- Parse HTML with BeautifulSoup
- Extract basic text content
- Save to text files

**Key concepts**: HTTP requests, HTML parsing, file operations

### Phase 2: Structured Data Extraction
**Time**: 3-4 hours

Extract specific data:
- Target specific HTML elements
- Extract multiple data points
- Structure data in dictionaries/lists
- Save to CSV and JSON formats

**Key concepts**: CSS selectors, data structures, file formats

### Phase 3: Error Handling and Robustness
**Time**: 3-4 hours

Make scraper more reliable:
- Handle network errors
- Implement retry logic
- Add rate limiting
- Validate extracted data

**Key concepts**: Exception handling, retry mechanisms, validation

### Phase 4: Advanced Features
**Time**: 4-5 hours

Add sophisticated functionality:
- Handle dynamic content (Selenium)
- Process multiple pages
- Implement data cleaning
- Create configurable scrapers

**Key concepts**: Browser automation, configuration management, data processing

## Getting Started

### Required Libraries
```bash
pip install requests beautifulsoup4 lxml pandas selenium
```

### Basic Setup
```python
import requests
from bs4 import BeautifulSoup
import csv
import json
import time
from urllib.parse import urljoin, urlparse

class WebScraper:
    def __init__(self, base_url, headers=None):
        self.base_url = base_url
        self.session = requests.Session()
        self.headers = headers or {
            'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36'
        }
        self.session.headers.update(self.headers)
```

## Core Functionality

### Making HTTP Requests
```python
def fetch_page(self, url, timeout=10):
    try:
        response = self.session.get(url, timeout=timeout)
        response.raise_for_status()  # Raise exception for bad status codes
        return response
    except requests.RequestException as e:
        print(f"Error fetching {url}: {e}")
        return None
```

### HTML Parsing
```python
def parse_html(self, html_content):
    return BeautifulSoup(html_content, 'html.parser')

def extract_data(self, soup, selectors):
    data = {}
    for key, selector in selectors.items():
        elements = soup.select(selector)
        if elements:
            data[key] = [elem.get_text(strip=True) for elem in elements]
        else:
            data[key] = []
    return data
```

## Example Scrapers

### News Article Scraper
```python
class NewsArticleScraper(WebScraper):
    def __init__(self):
        super().__init__("https://example-news-site.com")
        self.selectors = {
            'title': 'h1.article-title',
            'author': '.author-name',
            'date': '.publish-date',
            'content': '.article-content p'
        }
    
    def scrape_article(self, article_url):
        response = self.fetch_page(article_url)
        if not response:
            return None
        
        soup = self.parse_html(response.text)
        return self.extract_data(soup, self.selectors)
```

### Product Information Scraper
```python
class ProductScraper(WebScraper):
    def __init__(self):
        super().__init__("https://example-store.com")
        self.selectors = {
            'name': '.product-title',
            'price': '.price',
            'rating': '.rating',
            'description': '.product-description'
        }
    
    def scrape_products(self, category_url):
        products = []
        response = self.fetch_page(category_url)
        if not response:
            return products
        
        soup = self.parse_html(response.text)
        product_links = soup.select('.product-link')
        
        for link in product_links:
            product_url = urljoin(self.base_url, link.get('href'))
            product_data = self.scrape_product(product_url)
            if product_data:
                products.append(product_data)
            time.sleep(1)  # Rate limiting
        
        return products
```

## Data Storage and Export

### Save to CSV
```python
def save_to_csv(self, data, filename):
    if not data:
        return
    
    with open(filename, 'w', newline='', encoding='utf-8') as csvfile:
        fieldnames = data[0].keys()
        writer = csv.DictWriter(csvfile, fieldnames=fieldnames)
        writer.writeheader()
        writer.writerows(data)
```

### Save to JSON
```python
def save_to_json(self, data, filename):
    with open(filename, 'w', encoding='utf-8') as jsonfile:
        json.dump(data, jsonfile, indent=2, ensure_ascii=False)
```

## Error Handling and Best Practices

### Retry Logic
```python
def fetch_with_retry(self, url, max_retries=3, delay=1):
    for attempt in range(max_retries):
        try:
            response = self.fetch_page(url)
            if response:
                return response
        except Exception as e:
            print(f"Attempt {attempt + 1} failed: {e}")
            if attempt < max_retries - 1:
                time.sleep(delay * (2 ** attempt))  # Exponential backoff
    return None
```

### Rate Limiting
```python
class RateLimiter:
    def __init__(self, delay=1):
        self.delay = delay
        self.last_request = 0
    
    def wait(self):
        elapsed = time.time() - self.last_request
        if elapsed < self.delay:
            time.sleep(self.delay - elapsed)
        self.last_request = time.time()
```

### Respecting robots.txt
```python
import urllib.robotparser

def can_fetch(self, url):
    rp = urllib.robotparser.RobotFileParser()
    rp.set_url(urljoin(url, '/robots.txt'))
    rp.read()
    return rp.can_fetch(self.headers.get('User-Agent', '*'), url)
```

## Advanced Features

### JavaScript Rendering with Selenium
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

class JavaScriptScraper:
    def __init__(self):
        self.driver = webdriver.Chrome()  # Requires ChromeDriver
    
    def scrape_dynamic_content(self, url, wait_selector):
        self.driver.get(url)
        wait = WebDriverWait(self.driver, 10)
        wait.until(EC.presence_of_element_located((By.CSS_SELECTOR, wait_selector)))
        return self.driver.page_source
    
    def close(self):
        self.driver.quit()
```

### Configuration-Driven Scraping
```python
scraper_config = {
    "name": "news_scraper",
    "base_url": "https://example-news.com",
    "selectors": {
        "title": "h1.title",
        "content": ".article-body p"
    },
    "rate_limit": 2,
    "output_format": "json"
}

class ConfigurableScraper:
    def __init__(self, config):
        self.config = config
        self.scraper = WebScraper(config['base_url'])
        self.rate_limiter = RateLimiter(config.get('rate_limit', 1))
```

## Testing Your Scraper

### Test Targets
- Start with simple, static websites
- Test with different HTML structures
- Handle missing elements gracefully
- Test rate limiting and error handling
- Validate extracted data

### Sample Test Sites
- http://quotes.toscrape.com/ (beginner-friendly)
- https://books.toscrape.com/ (practice site)
- https://httpbin.org/ (HTTP testing)

## Ethical Considerations

### Best Practices
- Always check robots.txt
- Respect rate limits and don't overload servers
- Use appropriate User-Agent headers
- Don't scrape copyrighted content without permission
- Consider using official APIs when available

### Legal Considerations
- Review website terms of service
- Understand copyright and data protection laws
- Consider fair use principles
- Respect website owners' wishes

## Extensions and Improvements

### Beginner Extensions
- Email alert when new content is found
- Simple data analysis and visualization
- Scheduled scraping with cron jobs
- Basic duplicate detection

### Intermediate Extensions
- Distributed scraping with multiple workers
- Database storage for large datasets
- Web interface for configuration
- Integration with data analysis tools

### Advanced Extensions
- Machine learning for content classification
- Proxy rotation for large-scale scraping
- Real-time scraping with websockets
- Cloud deployment and scaling

## Common Issues and Solutions

**Issue**: Scraper gets blocked by anti-bot measures
**Solution**: Rotate User-Agents, use proxies, implement longer delays

**Issue**: JavaScript content not loading
**Solution**: Use Selenium or similar browser automation tools

**Issue**: Data extraction returns empty results
**Solution**: Inspect HTML structure, update selectors, handle dynamic content

**Issue**: Memory usage grows too large
**Solution**: Process data in batches, use generators, clear variables

## Learning Outcomes

After completing this project, you'll understand:
- HTTP protocol and web communication
- HTML structure and parsing techniques
- Error handling and retry strategies
- Data extraction and cleaning methods
- Ethical considerations in web scraping
- Working with external libraries and APIs

## File Structure

```
web_scraper/
├── scrapers/
│   ├── base_scraper.py    # Base scraper class
│   ├── news_scraper.py    # News website scraper
│   └── product_scraper.py # E-commerce scraper
├── utils/
│   ├── rate_limiter.py    # Rate limiting utilities
│   ├── data_cleaner.py    # Data cleaning functions
│   └── file_handler.py    # File operations
├── config/
│   ├── scrapers.json      # Scraper configurations
│   └── settings.py        # Global settings
├── data/
│   ├── raw/               # Raw scraped data
│   └── processed/         # Cleaned data
├── logs/
│   └── scraper.log        # Scraping logs
└── README.md              # Project documentation
```

## Next Steps

Once you've completed your web scraper:
1. Practice on different types of websites
2. Build scrapers for your specific needs
3. Learn about data analysis with pandas
4. Explore API alternatives to scraping
5. Try the Quiz Game project next for more interactive programming

Great job on building a powerful data collection tool!