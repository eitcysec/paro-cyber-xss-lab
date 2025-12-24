# paro-cyber-xss-lab
To identify and exploit a Cross-Site Scripting (XSS) vulnerability in a web application by injecting malicious JavaScript code and observing how user input is improperly handled.

**Lab Environment**
Attacker Machine: Kali Linux
Target: DVWA running on Apache (Localhost)
Browser: Firefox
Security Levels: Low/Medium/High (DVWA)

**Step 1: Launch the Lab**
Start Kali Linux and DVWA
Log into DVWA
Set DVWA Security → Low

Navigate to:
Vulnerabilities → XSS (Reflected)


<img width="817" height="458" alt="image" src="https://github.com/user-attachments/assets/6adf3871-70d5-4ed3-8ce6-3dffb0047343" />


**Step 2: Identify Input Field**
A text input field accepts a name parameter.
The value is reflected back in the page response.

<img width="836" height="448" alt="image" src="https://github.com/user-attachments/assets/5bf78417-32c2-4652-bc79-86fc23a8b8d8" />


Test for XSS Vulnerability
Basic Test Payload
<script>alert(1)</script>

Result:

JavaScript alert pops up.
Confirms Reflected XSS vulnerability.

<img width="837" height="449" alt="image" src="https://github.com/user-attachments/assets/228fed48-1bbb-4fdf-a90d-a32abf928121" />
