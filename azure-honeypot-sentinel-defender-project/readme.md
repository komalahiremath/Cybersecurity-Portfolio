#  Cloud Security Monitoring Honeypot (Azure)

##  Overview
This project demonstrates a cloud-based honeypot built on Microsoft Azure to simulate and monitor real-world cyber attacks. The environment captures brute-force login attempts and visualizes attacker activity globally using SIEM tools.

The project integrates:
- Microsoft Sentinel (SIEM)
- Microsoft Defender for Cloud (Security posture & threat protection)
- Log Analytics Workspace
- KQL (Kusto Query Language)

---

##  Objectives
- Simulate a vulnerable system exposed to the internet
- Capture real-world attack attempts (e.g., brute-force logins)
- Monitor and analyze logs using SIEM tools
- Visualize attacker geolocation using dashboards
- Understand cloud security posture using Defender

---

##  Architecture
- Azure Virtual Machine (Windows) configured as a honeypot
- SecurityEvent logs collected via Log Analytics
- Microsoft Sentinel for monitoring and visualization
- GeoIP Watchlist for IP enrichment
- Microsoft Defender for Cloud for security posture and threat detection

---

##  Implementation Steps

1. Created a Windows Virtual Machine in Azure
2. Opened RDP (port 3389) to allow external attack attempts
3. Connected VM to Log Analytics Workspace
4. Enabled Microsoft Sentinel
5. Configured GeoIP watchlist for IP enrichment
6. Wrote KQL queries to detect failed login attempts (EventID 4625)
7. Built Workbook dashboards to visualize attacker locations
8. Enabled Microsoft Defender for Cloud:
   - Monitored Secure Score
   - Reviewed security recommendations
   - Observed threat alerts

---

##  Key Features

-  Detection of brute-force login attempts
-  Global attacker map visualization
-  Log analysis using KQL
-  Security posture monitoring via Defender
-  Threat insights and recommendations

---

##  What I Learned

- How SIEM tools like Microsoft Sentinel collect and analyze logs
- Writing and optimizing KQL queries for security analysis
- Building interactive dashboards (Workbooks)
- Understanding real-world attack patterns (brute-force attempts)
- Importance of log enrichment (GeoIP) for threat intelligence
- Difference between:
  - Detection (Microsoft Defender for Cloud)
  - Monitoring & analysis (Microsoft Sentinel)
- How to monitor and improve cloud security posture using Secure Score
- Practical exposure to cloud security and SOC workflows

---

##  Tools & Technologies

- Microsoft Azure
- Microsoft Sentinel
- Microsoft Defender for Cloud
- Log Analytics Workspace
- KQL (Kusto Query Language)

---

##  Outcome

Successfully built a working cloud honeypot that:
- Captured real attack traffic
- Visualized attacker locations globally
- Demonstrated integration of SIEM and cloud security tools

---

##  Future Improvements

- Add automated alert rules in Sentinel
- Integrate incident response workflows
- Enhance dashboards with more analytics (top countries, timelines)
- Simulate advanced attack scenarios

---

##  Author

This project was built as part of my cybersecurity learning journey, focusing on SOC operations, threat detection, and cloud security.

          city = cityname,
          country = countryname,
          friendly_location = strcat(cityname, " (", countryname, ")")
