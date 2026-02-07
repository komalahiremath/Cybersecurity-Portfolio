# DNS Normal vs Suspicious Activity (Wireshark)

## Objective
The objective of this analysis is to understand the difference between **normal DNS traffic** and **unusual / potentially malicious DNS activity** using Wireshark. This helps in identifying early indicators of compromise such as malware beaconing, DNS tunneling, or command-and-control (C2) communication.

---

## Screenshot 1: Normal TCP & DNS Traffic

### Observation
In the first screenshot, we observe:
- Standard TCP connections with **SYN, ACK** flags
- Normal client-server communication on common ports:
  - HTTP (Port 80)
  - HTTPS (Port 443)
- DNS queries resolving **legitimate, well-known domains**, such as:
  - `login.live.com`
  - `messenger.hotmail.com`
  - `rad.msn.com`
  - `contacts.msn.com`
  - `smartadserver.com`

### Key Indicators of Normal DNS Traffic
- Queries are made to **popular, trusted domains**
- DNS responses return valid **A records and CNAME records**
- Traffic volume is moderate and spread out over time
- No repeated failed queries or abnormal patterns
- IP addresses belong to known CDNs (Akamai, Microsoft, etc.)

### Conclusion
This traffic represents **normal user activity**, such as:
- Logging into email or messaging services
- Browsing websites
- Background OS or application updates

There are **no indicators of malicious behavior** in this traffic.

---

## Screenshot 2: Unusual / Suspicious DNS Activity

### Observation
In the second screenshot, DNS traffic shows:
- **Very high frequency of DNS queries**
- Repeated queries from the same source IP
- Multiple DNS requests occurring within short time intervals
- Similar query patterns repeated continuously

### Suspicious Indicators
- Excessive DNS queries without corresponding user activity
- Repeated lookups that may indicate:
  - DNS tunneling
  - Malware beaconing
  - Command-and-Control (C2) communication
- Automated behavior rather than human-driven browsing
- DNS used as a communication channel instead of normal web traffic

### Why This Is Concerning
Attackers often use DNS because:
- DNS traffic is usually allowed through firewalls
- It blends in with legitimate traffic
- It can be used to exfiltrate data or receive commands

This pattern differs clearly from normal browsing behavior.

---

## Comparison: Normal vs Suspicious DNS

| Feature | Normal DNS Traffic | Suspicious DNS Traffic |
|------|-------------------|------------------------|
| Query Frequency | Low to moderate | Very high |
| Domain Types | Well-known domains | Repetitive or unusual |
| Timing | Spread over time | Bursty / automated |
| User Behavior | Human-driven | Scripted or malware-driven |
| Risk Level | Low | High |

---

## Final Conclusion
- **Normal DNS traffic** shows legitimate domain lookups related to user activity.
- **Suspicious DNS traffic** shows abnormal frequency and patterns that may indicate malicious behavior.

This analysis demonstrates how Wireshark can be used to:
- Detect unusual DNS behavior
- Identify early signs of malware activity
- Support SOC Level 1 investigations

---
