# 💰 Gold Price Checker

Easily fetch the **current 18K gold price in Iran** using Python.  

---

## 📝 Sample Code

Here's a snippet of the script:

```python
import requests
from bs4 import BeautifulSoup
import re

URL = 'https://www.tgju.org/profile/geram18'
response = requests.get(URL)
response.encoding = 'utf-8'

soup = BeautifulSoup(response.text, "html.parser")
