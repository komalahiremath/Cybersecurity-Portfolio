# Active Directory Monitoring with Splunk – Home Lab

## Project Summary

This project demonstrates an Active Directory security monitoring lab using Splunk SIEM. It includes:

🔹 Setting up Windows Server and joining a domain  
🔹 Adding domain users  
🔹 Installing Splunk and configuring log ingestion  
🔹 Simulating brute-force attacks from an attacker VM  
🔹 Analysing Windows Security Event logs in Splunk  
🔹 Running Atomic Red Team techniques and observing generated telemetry

The screenshots in this repo illustrate key stages of setup and attack detection.

---

## Screenshot Overview

### 1. Splunk Installation

![Splunk Server Installed](screenshots/01.Splunk-server-installed.png)  
Shows successful installation of **Splunk Enterprise**.

---

### 2. Active Directory Setup

 **Adding machines and users to the domain**

- `02.Adding_PC_to_Domain.png` – Windows client joined to the domain  
- `03.Adding_User_to_Domain.png` – Creating domain users

These steps show how domain machines and users were provisioned.

---

### 3. Brute Force Attack Detection

Screenshots:

- `04.Bruteforce_FailedLogin.png`  
- `05.Bruteforce_Success_LOG_Splunk.png`  
- `09.EventID-4625,4624(Bruteforce_Attempt).png`

These show:

 Failed RDP login attempts  
 Corresponding events in Splunk (Event ID 4625/4624)  
This demonstrates that events are successfully being ingested and can be monitored.

---

### 4. Splunk Inputs & Log Sources

![Input Configurations](screenshots/11.Source_Type_SPlunk_InputConf.png)  
Shows config for Splunk Universal Forwarder (`inputs.conf`), indicating which logs are forwarded.

---

### 5. Atomic Red Team Attack Telemetry

Shows images like:

- `12.T1059_ART.png`  
- `14.T1136.001(ATR).png`

This illustrates the lab running **Atomic Red Team simulations** and capturing activity logs in Splunk.

---

