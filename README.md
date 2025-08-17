<div align="center">

<h1 style="font-family:monospace; color:#FFD700; font-size:48px; text-shadow: 2px 2px #ff8c00;">
💰 Gold Price Tracker
</h1>

<p style="font-family:monospace; font-size:18px; color:#ffe599;">
Track the current gold price in Iran instantly 🚀
</p>

</div>

---

## Sample Code (main.py)

<div style="position:relative; background:#1e1e1e; border-radius:12px; overflow:hidden; font-family:monospace; font-size:14px; line-height:1.6; color:#d4d4d4; padding:20px; margin:20px 0;">

  <!-- Animated top line -->
  <div style="position:absolute; top:0; left:0; height:4px; width:100%; background: linear-gradient(90deg, #FFD700, #FFA500, #FFD700); animation: slide 2s linear infinite;"></div>

  <pre style="margin:0; padding-top:10px;">
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

<div style="background: linear-gradient(135deg, #333, #555); border-radius:12px; padding:20px; font-family:monospace; font-size:14px; color:#fff; line-height:1.6; box-shadow: 0 5px 15px rgba(0,0,0,0.3); margin:20px 0;">
Clone the repository and run the script:

<pre>
git clone https://github.com/SoBiMoqadam/Gold-Price.git
cd Gold-Price
python main.py
</pre>
</div>

<style>
@keyframes slide {
  0% {background-position: 0 0;}
  100% {background-position: 200% 0;}
}
</style>
