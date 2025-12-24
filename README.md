# paro-cyber-xss-lab
To identify and exploit a Cross-Site Scripting (XSS) vulnerability in a web application by injecting malicious JavaScript code and observing how user input is improperly handled.<br>

**Lab Environment**<br>
Attacker Machine: Kali Linux<br>
Target: DVWA running on Apache (Localhost)<br>
Browser: Firefox<br>
Security Levels: Low/Medium/High (DVWA)<br>

**Step 1: Launch the Lab**<br>
Start Kali Linux and DVWA<br>
Log into DVWA<br>
Set DVWA Security → Low<br>

<img width="817" height="458" alt="image" src="https://github.com/user-attachments/assets/6adf3871-70d5-4ed3-8ce6-3dffb0047343" />
<br><br>

Navigate to:<br>
Vulnerabilities → XSS (Reflected)<br>
<br>
<img width="836" height="420" alt="image" src="https://github.com/user-attachments/assets/fb716dce-14a8-480f-884c-59681de567d6" />

<br><br>

**Step 2: Identify Input Field**<br>
A text input field accepts a name parameter.<br>
The value is reflected back in the page response.<br><br>

<img width="836" height="448" alt="image" src="https://github.com/user-attachments/assets/5bf78417-32c2-4652-bc79-86fc23a8b8d8" />
<br>

Test for XSS Vulnerability<br>
Basic Test Payload<br>
<script>alert(1)</script><br>
<br>
Result:<br><br>

JavaScript alert pops up.<br>
Confirms Reflected XSS vulnerability.<br>
<br>
<img width="837" height="449" alt="image" src="https://github.com/user-attachments/assets/228fed48-1bbb-4fdf-a90d-a32abf928121" />
<br><br>
