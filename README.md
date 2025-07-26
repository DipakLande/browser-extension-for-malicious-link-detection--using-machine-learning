# browser-extension-for-malicious-link-detection--using-machine-learning
The Browser Extension for Malicious Link Detection project aims to enhance user security by providing real-time analysis and warning of potentially harmful URLs encountered during web browsing.


                           How To Run
Backend
1.	Install Node.js dependencies:
bash
cd backend
npm install
2.	Install Python dependencies (in a Python 3 env):
bash
pip install flask joblib scikit-learn pandas
3.	Train ML model (if you have dataset):
bash
python train_ml.py
4.	Start ML Flask server:
bash
python flask_predict.py
5.	Start Node.js backend:
bash
node server.js

Run curl by calling the actual binary (if installed), not the PowerShell alias:
powershell
curl.exe -X POST http://localhost:3000/api/check `
    -H "Content-Type: application/json" `
    -d '{"url": "https://www.bbc.com"}'
•	Note the use of ` (backtick) for line continuation in PowerShell instead of \.
•	The curl.exe calls the real curl binary that supports Unix-style flags.
Option 2: Use PowerShell-native Invoke-RestMethod or Invoke-WebRequest
Equivalent command in PowerShell using Invoke-RestMethod:
powershell
Invoke-RestMethod -Uri "http://localhost:3000/api/check" `
  -Method POST `
  -ContentType "application/json" `
  -Body '{"url": "https://www.bbc.com"}'
This will send the same POST request and return parsed JSON.
Option 3: Use Windows Terminal with WSL or Git Bash
If you have Windows Subsystem for Linux (WSL) or Git Bash installed, use those shells to run the original curl command as-is (with \ line continuation).
Summary Table for PowerShell:
Original curl flag	PowerShell equivalent
-X POST	-Method POST
-H "Content-Type..."	-ContentType "application/json"
-d '{"json..."}'	-Body '{"json..."}'
\ line continuation	PowerShell uses backtick `
Example full PowerShell command with Invoke-RestMethod:
powershell
Invoke-RestMethod -Uri "http://localhost:3000/api/check" `
  -Method POST `
  -ContentType "application/json" `
  -Body '{"url": "https://www.bbc.com"}'

Extension
1.	Load the extension/ folder as unpacked extension in Chrome/Firefox.
2.	Make sure backend is running on http://localhost:3000.
3.	Use the popup to scan URLs, see history, and clear history.
4.	For production, update API URLs and host backend on a public server.


Sample Malicious URLs
These URLs are often associated with phishing, malware, or scams (for testing only):
1.	http://malicious-example.com/phishing/login.php
2.	http://192.168.1.1/fakebank/verify.html
3.	http://badsite.ru/malware.exe
4.	http://test-malware.site/downloads/virus.exe
5.	http://phishing-site.net/security-update
6.	http://fake-paypal-login.com/
7.	http://evilwebsite.biz/steal-info.php
8.	http://spammyemailsite.org/subscribe-now
9.	http://dangerous-domain.tk/fraudpage
10.	http://trojan-download.su/file.exe
Sample Non-Malicious (Safe) URLs
Legitimate and trusted websites generally used for normal browsing:
1.	https://www.google.com
2.	https://www.wikipedia.org
3.	https://www.github.com
4.	https://www.stackoverflow.com
5.	https://www.microsoft.com
6.	https://www.amazon.com
7.	https://www.nytimes.com
8.	https://www.bbc.com
9.	https://www.linkedin.com
10.	https://www.apple.com

