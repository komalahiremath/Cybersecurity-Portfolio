
# Network Traffic Analysis Project  
*A cybersecurity project analysing normal and suspicious traffic patterns using Wireshark.*

---

## Overview

This project focuses on **network traffic analysis** using a **sample packet capture file** from an online learning resource.  
Using this sample packet, I learned how real network traffic looks and how different attack behaviours appear inside Wireshark.

The project explores:

- How **normal network traffic** behaves (DNS, HTTP, TCP, etc.)  
- How **suspicious or attack traffic** looks inside packet captures  
- How different types of attacks leave visible traces in traffic  
- How a SOC analyst identifies unusual patterns using Wireshark  

---

##  Project Focus

This project analyses **different attack behaviours** and compares them with normal traffic. Specifically, it demonstrates:

- Normal DNS and HTTP communication  
- Suspicious or abnormal DNS requests  
- Indicators of brute-force activity  
- Web-related suspicious behaviours  
- General differences between normal and malicious traffic  

Throughout the project, I used **Wireshark display filters** to isolate and analyse specific packets.  
(Only mentioned here — detailed filters are documented inside each section.)

---

##  Tools Used

- **Wireshark** — packet capture analysis  
- **Sample PCAP file** — (https://s3.amazonaws.com/tcpreplay-pcap-files/smallFlows.pcap)used for learning and traffic investigation  
- **Windows Host Machine** — analysis environment  

---

##  What This Project Includes

- Analysis performed on a **sample network packet file**  
- Understanding what normal traffic patterns look like  
- Identifying where suspicious behaviour appears  
- Recognising anomalies across DNS, HTTP, and TCP flows  
- Separating normal vs malicious indicators  
- Screenshots and short explanations inside each folder  

---

##  Summary

This project helped me understand:

- How **normal traffic** appears in Wireshark  
- How **attack patterns** differ from normal behaviour  
- How to recognise basic indicators of compromise  
- How Wireshark is used by SOC analysts for investigation  

The entire project is based on analysing a **sample PCAP file**, which allowed me to observe realistic traffic and learn how network-level attacks can be identified.
