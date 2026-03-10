# Active Directory Home Lab – SOC Analyst Security Monitoring Project

## Overview
This project demonstrates how to build a fully functional **Active Directory (AD) home lab** designed for cybersecurity learning and security monitoring practice. The lab simulates a real-world enterprise environment where defenders monitor attacker activity.

The environment includes a domain controller, endpoint machines, an attacker system, and a SIEM platform to collect and analyze telemetry. Attacks such as brute-force login attempts are simulated and detected using log analysis and threat simulation tools.

This project helps develop hands-on skills required for **SOC Analyst, Cybersecurity Analyst, and Blue Team roles**.

---

## Learning Objectives

Through this lab you will learn how to:

- Design and deploy an **Active Directory environment**
- Install and configure **Windows Server Domain Controller**
- Set up **Windows endpoints joined to a domain**
- Deploy **Splunk SIEM** for log ingestion and monitoring
- Configure **Sysmon telemetry** for detailed endpoint logging
- Simulate attacker behavior using **Kali Linux**
- Perform **brute-force attacks** and detect them using logs
- Simulate adversary techniques using **Atomic Red Team**
- Analyze security events and build detection queries

---

## Lab Architecture

The environment contains the following machines:

| System | Role |
|------|------|
| Windows Server 2022 | Domain Controller + Splunk Forwarder |
| Windows 10 | Target endpoint joined to domain |
| Ubuntu Server | Splunk Enterprise SIEM |
| Kali Linux | Attacker machine |

### Domain

Blueteam.local


## Network Design

Example logical network diagram:

```
                ┌────────────────────┐
                │     Splunk SIEM    │
                │   Ubuntu Server    │
                └─────────┬──────────┘
                          │
        ┌─────────────────┼─────────────────┐
        │                                   │
┌───────────────┐                 ┌────────────────┐
│ Windows Server │                 │  Windows 10    │
│ Domain Control │                 │ Target Machine │
└───────────────┘                 └────────────────┘
        │
        │
┌────────────────┐
│   Kali Linux    │
│ Attacker System │
└────────────────┘
```

---

## Hardware Requirements

Recommended system specifications:

- **16 GB RAM minimum**
- **250 GB disk space**
- Virtualization platform: **VirtualBox**
- Multiple VMs running simultaneously

---

## Software Components

- Windows Server 2022
- Windows 10
- Kali Linux
- Ubuntu Server
- Splunk Enterprise
- Splunk Universal Forwarder
- Sysmon
- Atomic Red Team
- Crowbar (Brute-force tool)

---

# Project Setup

## Part 1 – Lab Design

Before deployment:

- Design the **logical network architecture**
- Define **IP addressing**
- Create **network diagrams** using Draw.io

Host Roles:

| Machine | Role |
|------|------|
| Domain Controller | Active Directory + logging |
| Target Machine | Domain endpoint |
| Splunk Server | SIEM log analysis |
| Kali Linux | Attacker system |

---

## Part 2 – Installing Virtual Machines

Download the following ISO images:

- Windows Server 2022
- Windows 10
- Kali Linux
- Ubuntu Server

Create virtual machines using **VirtualBox**.

Recommended configuration:

| VM | RAM |
|----|----|
| Splunk Server | 6 GB |
| Domain Controller | 4 GB |
| Windows Target | 4 GB |
| Kali Linux | 2–4 GB |

After installation, update Kali Linux:

```bash
sudo apt update && sudo apt upgrade
```

Install brute-force tool:

```bash
sudo apt install crowbar
```

---

## Part 3 – Telemetry & Logging Setup

### Install Sysmon

Install Sysmon on:

- Domain Controller
- Windows Target Machine

Sysmon provides detailed endpoint telemetry including:

- Process creation
- Network connections
- File activity

---

### Install Splunk Forwarder

Install **Splunk Universal Forwarder** on:

- Windows Server
- Windows Target

Configure forwarding to the **Splunk Enterprise server**.

---

### Configure Splunk

On the Ubuntu Server:

- Install **Splunk Enterprise**
- Configure log ingestion
- Create initial search queries

Example monitored event IDs:

| Event ID | Description |
|--------|------------|
| 4624 | Successful login |
| 4625 | Failed login |

Example Splunk search query:

```
index=wineventlog EventCode=4625
```

---

## Part 4 – Active Directory Setup

Steps:

1. Promote Windows Server to **Domain Controller**
2. Create domain:

```
Blueteam.local
```

3. Create domain users:

- tsmith
- jenny

4. Enable **Remote Desktop (RDP)** on the target machine
5. Join Windows 10 machine to the domain
6. Assign RDP permissions to users

Verify access from Kali Linux.

---

## Part 5 – Attack Simulation

### Brute Force Attack

Using Kali Linux and Crowbar:

```bash
crowbar -b rdp -s <target_ip> -u tsmith -C passwords.txt
```

Use password list:

```
/usr/share/wordlists/rockyou.txt
```

Monitor activity in **Splunk** to detect failed login attempts.

---

## Threat Detection

Monitor these events in Splunk:

- Failed login attempts
- Brute-force patterns
- Suspicious authentication activity

Example query:

```
index=wineventlog EventCode=4625
| stats count by Account_Name
```

---

## Atomic Red Team

Install **Atomic Red Team** on the Windows target machine.

Set PowerShell execution policy:

```powershell
Set-ExecutionPolicy Bypass -Scope CurrentUser
```

Add Defender exclusion:

```powershell
Add-MpPreference -ExclusionPath C:\
```

Run installation script:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/redcanaryco/invoke-atomicredteam/master/install-atomicredteam.ps1'); Install-AtomicRedTeam -GetAtomics
```

Run Atomic Red Team tests to simulate adversary techniques and observe telemetry.

---

## Detection & Analysis

This lab allows detection of:

- Brute-force login attempts
- Suspicious authentication activity
- Adversary simulation techniques
- Endpoint telemetry events

This helps build practical skills in:

- Security monitoring
- Log analysis
- Threat detection
- SOC investigation workflows

---

## Best Practices

- Perform attacks **only in controlled lab environments**
- Use **VM snapshots** to save working lab states
- Slow brute-force attempts to avoid account lockouts
- Extend monitoring with **Splunk dashboards**

---

## Skills Demonstrated

- Active Directory administration
- SIEM deployment and monitoring
- Endpoint telemetry collection
- Attack simulation
- Threat detection
- SOC investigation workflow

---

## Tools Used

- VirtualBox
- Kali Linux
- Windows Server
- Windows 10
- Splunk Enterprise
- Sysmon
- Atomic Red Team
- Crowbar

---

## Future Improvements

Possible extensions:

- Implement automated alerting
- Build Splunk dashboards
- Add IDS/IPS monitoring
- Integrate threat intelligence feeds
- Simulate lateral movement attacks

---

## Disclaimer

This lab environment is intended **strictly for educational purposes**.  
All attack simulations must be performed only within authorized environments and never against real systems without permission.
