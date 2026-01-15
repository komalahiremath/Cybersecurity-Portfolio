#  OSI Layers vs Possible Cyber Attacks & Controls

This document maps each OSI Layer to common cyber attacks and recommended security controls.  
A great reference for networking, SOC analysis, and Blue Team investigations.

---

##  7. Application Layer  
### **Possible Cyber Attacks**
- SQL Injection  
- Cross-site Scripting (XSS)  
- Remote Code Execution (RCE)

### **Security Controls**
- Regular patching  
- Remediate known vulnerabilities  
- Input validation  

---

##  6. Presentation Layer  
### **Possible Cyber Attacks**
- DAT format manipulation  
- Code injection  
- Serialization attacks  

### **Security Controls**
- Validate/sanitize user inputs  
- Use secure data serialization libraries  
- Prevent code injection  

---

##  5. Session Layer  
### **Possible Cyber Attacks**
- Session hijacking  
- Token-based attacks  
- Session sidejacking  

### **Security Controls**
- Randomize session IDs  
- Enforce secure logout mechanisms  
- Use secure tokens for user authentication  

---

##  4. Transport Layer  
### **Possible Cyber Attacks**
- SYN flood attacks  
- TCP session hijacking  
- UDP flooding  

### **Security Controls**
- Monitor/control firewall traffic at the transport layer  
- Mitigate SYN flood attacks  
- Implement secure data exchange  

---

##  3. Network Layer  
### **Possible Cyber Attacks**
- IP spoofing  
- ICMP attacks (ping flood, ping of death)  
- Denial-of-Service (DoS) attacks  

### **Security Controls**
- Firewall filtering  
- Use IDS (Intrusion Detection System) and IPS (Intrusion Prevention System)  
- Configure firewall rules; prevent IP address spoofing  

---

##  2. Data Link Layer  
### **Possible Cyber Attacks**
- MAC address spoofing  
- ARP spoofing  
- VLAN hopping  
- Ethernet frame manipulation  

### **Security Controls**
- Port security to limit MAC IDs per port  
- ARP spoofing detection  
- Enable VLAN trunking protocols  

---

##  1. Physical Layer  
### **Possible Cyber Attacks**
- Physical tampering  
- Eavesdropping  
- Man-in-the-middle at physical layer  
- Tapping network cables  
- Disrupting power supply  

### **Security Controls**
- Access controls  
- CCTV surveillance  
- Secure cabling  
- Regular inspection and monitoring  
- Prevent unauthorized access to network infrastructure  

---

##  Summary  
This mapping helps analysts understand:
- What attacks occur at each OSI layer  
- How attackers target the network stack  
- What defensive controls should be implemented
