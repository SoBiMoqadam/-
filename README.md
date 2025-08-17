## 🏆 Gold Price Checker

With this Python snippet, you can easily fetch the **current price of 18K gold** in Iran directly from [TGJU](https://www.tgju.org/profile/geram18). 🚀

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
