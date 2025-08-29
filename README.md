# Splunk Brute Force Detection Lab

## Overview
This project demonstrates how to detect Windows brute force login attempts using Splunk Enterprise.  
A Universal Forwarder installed on a Windows VM collects Windows Security Event Logs, forwarding them to Splunk Enterprise.  
A Hydra brute force attack from Kali Linux simulates failed login attempts which generate Event ID 4625 logs, captured and analyzed in Splunk.

---

## Project Workflow and Screenshots

### 1. Windows Event Viewer - Security Audit Enabled  
Audit policies enabled to log failed (4625) and successful (4624) logins on Windows VM.  
<img width="940" height="706" alt="image" src="https://github.com/user-attachments/assets/13dd3a83-1106-412e-bb5b-734b76e02ecd" />


### 2. Splunk Universal Forwarder on Windows VM  
Universal Forwarder installed and running, configured to forward Windows Security logs to Splunk.  
<img width="940" height="512" alt="image" src="https://github.com/user-attachments/assets/67926037-1d3f-4292-84e3-abd54cb20ec1" />


### 3. Splunk Enterprise Data Input Configuration  

<img width="1349" height="675" alt="image" src="https://github.com/user-attachments/assets/90b1037d-ee5b-45ec-a95a-08cb92c6f167" />
<img width="940" height="470" alt="image" src="https://github.com/user-attachments/assets/c5ac5f79-6182-4f24-ae3b-3954964103df" />


### 4. Hydra Brute Force Attack Command on Kali Linux  
Hydra running RDP brute force attack generating failed login attempts on Windows VM.  
<img width="940" height="640" alt="image" src="https://github.com/user-attachments/assets/ab3a399c-7546-4dfc-918a-9f4d2dbc9004" />


### 5. Splunk Search Results for Failed Logins (Event ID 4625)  
Splunk search results showing failed login attempts captured from Hydra attack logs.  
<img width="940" height="249" alt="image" src="https://github.com/user-attachments/assets/af00e87a-1ce5-488f-89b2-2c8978d3d551" />
<img width="940" height="444" alt="image" src="https://github.com/user-attachments/assets/277b7b55-4e07-4a4a-83d6-4ddf7d70b704" />

---

## Files Included
- Splunk universal forwarder configuration snippets (`inputs.conf`).
- Hydra username and password lists used in testing.
- Splunk search queries for detection.
- This README file.

---

## How to Use

1. Set up a Windows VM with Security auditing enabled for logon failures.  
2. Install Splunk Universal Forwarder on Windows VM, configure to forward Security logs.  
3. Create corresponding data input on Splunk Enterprise for forwarded Windows Event Logs.  
4. From Kali, run Hydra with appropriate username/password lists against Windows RDP service.  
5. Search Splunk for Event ID 4625 to review failed login attempts.  

