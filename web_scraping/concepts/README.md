# Web Scraping Concepts & Techniques

Hands-on notebooks for collecting, parsing, and extracting structured information from web pages using **BeautifulSoup**, **Requests**, and HTML parsers.

---

## 📂 Notebooks in this Directory

| Notebook | Focus | Key Topics |
| :--- | :--- | :--- |
| `web_scraping_prac.ipynb` | Fundamentals | HTTP GET requests, response status codes, HTML parsing, tag inspection, CSS selectors |
| `data_collection.ipynb` | Pipeline & Extraction | Automated extraction workflows, extracting tabular structures, text sanitization, saving to CSV/JSON |

---

## 🛠️ Typical Scraping Pipeline

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

# 1. Fetch HTML content with custom User-Agent headers
url = "https://example.com"
headers = {"User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64)"}
response = requests.get(url, headers=headers)

if response.status_code == 200:
    # 2. Parse HTML
    soup = BeautifulSoup(response.content, "html.parser")
    
    # 3. Extract items by CSS selectors or tag attributes
    items = []
    for card in soup.find_all("div", class_="product-card"):
        title = card.find("h2").get_text(strip=True)
        price = card.find("span", class_="price").get_text(strip=True)
        items.append({"title": title, "price": price})
        
    # 4. Convert to DataFrame
    df = pd.DataFrame(items)
```

---

## 💡 Best Practices

1. **Inspect Network Tabs**: Check if the website has an internal JSON API before parsing complex nested HTML.
2. **Rate Limiting**: Use `time.sleep()` between requests to avoid overloading target servers and getting IP blocked.
3. **Respect `robots.txt`**: Always verify scraping permissions and terms of service.
