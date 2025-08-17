<div align="center">

<h1 style="font-family:monospace; color:#FFD700; font-size:42px;">
💰 Gold Price Tracker
</h1>

<p style="font-family:monospace; font-size:18px; color:#ffe599;">
Easily get the current gold price in Iran with this Python script 🚀
</p>

</div>

---

## Sample Code (main.py)

<div style="background:#1e1e1e; color:#d4d4d4; border-radius:10px; padding:20px; overflow-x:auto; font-family:monospace; font-size:14px; line-height:1.5;">

<pre>
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
</pre>
</div>

---

## 🛠 Installation / Setup

<div style="background:#f0f0f0; border-radius:10px; padding:20px; font-family:monospace; font-size:14px; line-height:1.5;">
Clone the repository and run the script:

<pre>
git clone https://github.com/SoBiMoqadam/Gold-Price.git
cd Gold-Price
python main.py
</pre>
</div>

---

## Download

<div style="display:flex; justify-content:center; margin:20px 0;">
  <a href="https://github.com/SoBiMoqadam/Gold-Price/raw/main/main.py" 
     download
     style="
        padding:12px 30px;
        font-size:16px;
        font-weight:bold;
        color:white;
        text-decoration:none;
        border-radius:8px;
        background: linear-gradient(135deg, #FFD700, #FFA500);
        box-shadow: 0 5px 15px rgba(0,0,0,0.3);
        transition: transform 0.2s, box-shadow 0.2s;
     "
     onmouseover="this.style.transform='translateY(-3px)'; this.style.boxShadow='0 10px 20px rgba(0,0,0,0.4)';"
     onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 5px 15px rgba(0,0,0,0.3)';"
  >
      ⬇️ Download main.py
  </a>
</div>
