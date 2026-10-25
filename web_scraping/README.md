# Web Scraping & Data Collection

Techniques for collecting data from websites and web services.

## 📂 Structure

```
web_scraping/
├── concepts/       # Web scraping techniques and tutorials
└── scraped_data/   # Collected data from web scraping
```

## 🎯 Topics

### Web Scraping Fundamentals
- HTML parsing with BeautifulSoup
- Extracting data from web pages
- Handling forms and authentication
- Dealing with JavaScript-heavy sites
- Respecting robots.txt and terms of service

### Data Collection Methods
- **Static HTML scraping**: Parse HTML directly
- **API consumption**: Use JSON endpoints
- **Selenium**: Automate browser interactions
- **Requests library**: HTTP requests in Python

## ⚖️ Legal & Ethical Considerations

Before scraping any website:

1. **Check robots.txt**: `website.com/robots.txt`
2. **Read Terms of Service**: Many sites prohibit scraping
3. **Respect Rate Limits**: Don't overload servers
4. **Use delays**: Add `time.sleep()` between requests
5. **Identify yourself**: Set proper User-Agent headers
6. **Ask for permission**: Contact site owners if unsure

**Good candidates for scraping**:
- Public data repositories
- Government datasets
- Academic resources
- Your own website

**Avoid scraping**:
- Private user data
- Copyrighted content (without permission)
- Sites with explicit "no scraping" policies
- High-frequency API calls without authorization

## 🔗 Common Libraries

```python
# HTML parsing
from bs4 import BeautifulSoup
import requests

# More advanced
from selenium import webdriver  # Browser automation
import scrapy  # Full web scraping framework
```

## 📝 Basic Example

```python
import requests
from bs4 import BeautifulSoup
import time

# Fetch webpage
url = "https://example.com/data"
headers = {"User-Agent": "Your Name (learning project)"}
response = requests.get(url, headers=headers)

# Parse HTML
soup = BeautifulSoup(response.content, 'html.parser')

# Extract data
items = soup.find_all('div', class_='item')
data = []

for item in items:
    title = item.find('h2').text
    price = item.find('span', class_='price').text
    data.append({'title': title, 'price': price})
    
# Be respectful - add delay between requests
time.sleep(2)

# Convert to DataFrame
import pandas as pd
df = pd.DataFrame(data)
df.to_csv('../scraped_data/output.csv', index=False)
```

## 🛠️ Common Patterns

### Extract Text
```python
element.text  # All text content
element.get_text(strip=True)  # Cleaned text
```

### Extract Attributes
```python
element['href']  # href attribute
element.get('class')  # class attribute
```

### Navigate HTML
```python
parent = element.parent
children = element.children
siblings = element.next_sibling
```

### Select Elements
```python
soup.find('div', class_='content')  # First match
soup.find_all('p')  # All paragraphs
soup.select('div.header > span')  # CSS selectors
```

## 📊 Real-World Workflow

1. **Inspect the website**: Understand HTML structure
2. **Identify patterns**: Find repeating elements to extract
3. **Write scraper**: Extract data systematically
4. **Handle errors**: Network issues, missing elements
5. **Clean data**: Remove extra whitespace, normalize
6. **Save locally**: Store in CSV or JSON
7. **Analyze**: Feed into your ML pipeline

## 💡 Tips

- **Test on a single page first**: Before scraping entire sites
- **Save raw HTML**: For debugging and reproducibility
- **Add error handling**: Networks are unreliable
- **Log progress**: When scraping large sites
- **Cache responses**: Don't re-scrape identical pages
- **Validate data**: Check for expected fields/formats

## 🚫 Anti-scraping Measures

Websites use these to prevent scraping:
- Rate limiting (limit requests per IP)
- CAPTCHA challenges
- JavaScript rendering (content loaded dynamically)
- IP blocking
- Session-based authentication

**Workarounds**:
- Selenium for JavaScript sites
- Proxies for IP blocking
- Slower request rates
- Proper headers and authentication

## ⚠️ Debugging Tips

```python
# Check response status
print(response.status_code)  # Should be 200

# View raw HTML
print(response.text[:500])

# Check if element exists before accessing
element = soup.find('div', class_='missing')
if element:
    print(element.text)
else:
    print("Element not found")

# Save HTML locally for inspection
with open('page.html', 'w') as f:
    f.write(response.text)
```

## 📚 Resources

- BeautifulSoup Documentation: https://www.crummy.com/software/BeautifulSoup/bs4/doc/
- Requests Library: https://docs.python-requests.org/
- Scrapy Framework: https://scrapy.org/
- Selenium Documentation: https://selenium-python.readthedocs.io/

---

**Last updated**: 2026-06-14
