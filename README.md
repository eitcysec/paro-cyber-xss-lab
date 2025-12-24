# paro-cyber-xss-lab
To identify and exploit a reflective Cross-Site Scripting (XSS) vulnerability in a web application by injecting malicious JavaScript code and observing how user input is improperly handled.<br>

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

Perform a Reflected XSS attack at Medium security level.<br><br>
<img width="310" height="50" alt="image" src="https://github.com/user-attachments/assets/713b93f4-5993-4153-8ecd-4ec88ae80c9b" /><br><br>

Again, enter the following payload in the What's your name? box and click Submit.<br>
<script>alert("1")</script><br>
You will see a Hello response, but this time no pop up will appear. This indicates that the script did not execute.<br><br>
<img width="343" height="83" alt="image" src="https://github.com/user-attachments/assets/368298f7-4f0c-43bd-9920-935c3573ee11" /><br><br>
This source code creates a filter, with str_replace() function, that removes the <script> tag in our payload and replaces it with a null value. <br><br>
Because this script is only filtering out <script> in lower case, we can try and get around the filter by using a different tag in the payload. We will use <ScRipt> <br>
<ScRipt>alert("1")</ScRipt><br><br>

<img width="535" height="353" alt="image" src="https://github.com/user-attachments/assets/1e84d065-5d71-4ea8-8b5a-249c0b063aa4" /><br><br>
Filter bypassed and we get a pop up<br><br>

 Perform a Reflective XSS attack at High security level.<br><br>
 <img width="246" height="41" alt="image" src="https://github.com/user-attachments/assets/3499084f-c165-4393-99a4-9e3688f405d9" /> <br><br>

 The same attack will be attempted, but this time the security level of the website will be High.<br><br>
<img width="340" height="158" alt="image" src="https://github.com/user-attachments/assets/b6ad6be1-f842-447a-9dde-e8cc9d9051c8" /><br><br>
There is a Hello message and no alert pop up box. The developer used a regular expression to replace any form of the <script> tag, no matter what case of the characters is used, with a null value.<br>
To bypass this filter, we must use another HTML tag instead of <script> to attack the site.<br>
<br>
<img src=x onerror=alert("1")><br><br>

<img width="823" height="385" alt="image" src="https://github.com/user-attachments/assets/89c081db-8446-4761-896c-7f6831916830" /> <br><br>

The XSS popup box will appear this time. We successfully bypassed the filter and exploited the Reflected XSS vulnerability in DVWA at High level security.









