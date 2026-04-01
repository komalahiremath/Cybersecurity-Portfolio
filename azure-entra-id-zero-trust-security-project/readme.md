#  Azure Entra ID Zero Trust Security Project

##  Overview
This project demonstrates the implementation of a Zero Trust-based Identity and Access Management (IAM) system using Microsoft Entra ID. It focuses on securing user identities, enforcing strict access controls, and monitoring suspicious activities through real-world attack simulations.

---

##  Objectives
- Implement Role-Based Access Control (RBAC)
- Enforce Multi-Factor Authentication (MFA)
- Configure Conditional Access Policies
- Monitor and analyse sign-in activity
- Simulate real-world cyber attack scenarios

---

##  Technologies Used
- Microsoft Entra ID (Azure Active Directory)
- Azure Portal
- Microsoft Authenticator
- VPN (for location-based attack simulation)

---

##  Project Architecture
This project follows the **Zero Trust Security Model**, where no user or device is trusted by default, and verification is required at every access point.

---

##  Implementation Steps

### 1️ User Creation
Created multiple users to simulate a real-world environment:
- **Admin User** – Full access
- **Normal User** – Limited access
- **Attacker User** – Used for testing attack scenarios

---

### 2️ Role-Based Access Control (RBAC)
- Assigned **Global Administrator** role to admin user
- Restricted access for normal users
- Implemented **least privilege principle**

---

### 3️ Multi-Factor Authentication (MFA)
- Enabled MFA for all users
- Configured:
  - Microsoft Authenticator
  - SMS-based verification

---

### 4️ Conditional Access Policies

####  Policy 1: Enforce MFA
- Applied to all users
- Required MFA for every login

####  Policy 2: Block Non-UK Locations
- Restricted access from outside the UK
- Simulated unauthorized login attempts

####  Policy 3: Device Compliance (Optional)
- Allowed access only from compliant devices

---

##  Monitoring & Detection

###  Sign-in Logs Analysis
Monitored the following:
- Failed login attempts
- Unknown locations
- Suspicious IP addresses
- User login behaviour

---

##  Attack Simulations

### 1 Location-Based Attack
- Used VPN to simulate login from outside the UK
- Access blocked using Conditional Access

### 2 MFA Bypass Attempt
- Attempted login without completing MFA
- Access denied successfully

---

##  Key Learnings
- Strong understanding of Zero Trust security model
- Hands-on experience with identity and access management
- Practical exposure to security monitoring and log analysis
- Experience in detecting and analysing suspicious activities

---

##  Future Improvements
- Integrate with Microsoft Sentinel (SIEM)
- Create automated alert rules
- Implement incident response workflows
- Perform advanced threat hunting

---

## Conclusion
This project demonstrates how modern identity security controls can be implemented using Microsoft Entra ID to protect systems against unauthorized access, aligning with Zero Trust principles.
