<div align="center">

<h1 style="font-family:monospace; color:#00FFFF; font-size:42px;">
💰 Gold Price Checker
</h1>

<p style="font-family:monospace; font-size:18px; color:#9be7ff;">
Fetch the current 18K gold price in Iran instantly using Python 🚀
</p>

</div>

---

## 📝 About

This script scrapes the **current 18K gold price** from [TGJU](https://www.tgju.org/profile/geram18) and prints it in the console.  
Perfect for learning web scraping with Python and keeping track of live gold rates.

### What You’ll Learn:
- Using `requests` to fetch web pages  
- Parsing HTML with `BeautifulSoup`  
- Extracting data with `regex`  
- Printing formatted results in Python  

---

## 📄 Sample Code

```python
import requests
from bs4 import BeautifulSoup
import re

URL = 'https://www.tgju.org/profile/geram18'
response = requests.get(URL)
response.encoding = 'utf-8'

soup = BeautifulSoup(response.text, "html.parser")

for h3 in soup.find_all("h3"):
    text = h3.get_text(strip=True)
    if 'نرخ فعلی' in text:
        match = re.search(r'نرخ فعلی[:\s]*[:\-]*\s*([\d,]+)', text)
        if match:
            rate = match.group(1)
            print(" نرخ فعلی گرم ۱۸ عیار:", rate, "ریال")
        else:
            print(" نرخ پیدا نشد داخل متن:", text)
        break
