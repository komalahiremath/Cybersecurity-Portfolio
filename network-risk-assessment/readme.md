# Network risk assessement on Enterprise Network (STP – Capslock)

## Overview
  
The task was to perform a **Risk assessement on an simulated orgranisation network**, focusing on:

- Understanding the network architecture  
- Identifying critical assets and environments  
- Analysing potential threats and attack paths  
- Recommending security controls and tools to mitigate the risks :contentReference[oaicite:0]{index=0}

## Objectives

- Evaluate and select an appropriate **risk assessment framework** for a network-focused use case  
- Identify **network environments and assets** that are critical to the organisation  
- Analyse **threat scenarios, attack paths, and impacts**  
- Understand the **network topology** and related weaknesses  
- Recommend **security controls and tools** aligned with the identified risks  


## Scenario

The fictional organisation used in this assessment has:

- Multiple **divisions** connected via the cloud  
- A **star topology** network design  
- Office-level networks where all devices connect to a central router and then to the cloud  

This structure introduces dependencies on central components and potential paths for lateral movement if the network is not properly segmented.


## Methodology (High-Level Steps)

1. **Reviewed and selected a suitable risk framework**  
2. **Identified network environments and assets**  
3. **Analysed threats and potential attack paths**  
4. **Analysed the network topology for weaknesses**  
5. **Recommended security controls and tools**

Each step is explained in more detail below.


## 1. Framework Review and Selection

**Goal:** Choose a risk assessment framework suitable for analysing **network-related risks** in a multi-division organisation.

### Frameworks Reviewed

- **OCTAVE-S**  
- **FAIR**  
- **ISO 27001**  
- **OCTAVE Allegro**   

### Key Reasoning

- **OCTAVE-S**: Good for smaller organisations, but too broad and less suitable for targeted network-specific analysis.  
- **FAIR**: Strong for **financial risk quantification**, but heavily quantitative and less aligned to qualitative, network-centric scenarios.  
- **ISO 27001**: Excellent for building an **Information Security Management System (ISMS)**, but more focused on governance and compliance than a practical, scenario-based risk analysis.  
- **OCTAVE Allegro (Selected)**:  
  - Asset-focused and flexible  
  - Better suited for **information and network asset risk analysis**  
  - Allows creation of **threat scenarios** around specific network environments  

 **Outcome:** Selected **OCTAVE Allegro** as the primary framework for the risk assessment.


## 2. Identification of Network Environments & Assets

**Goal:** Understand what parts of the network are important and need protection.

### Network Environments Considered

- Office networks  
- Cloud-connected divisions  
- Wireless network environments  

### Key Assets Identified

- **Servers**  
- **Routers**  
- **Switches**  
- **Wireless access points / wireless networks** 

These were treated as **critical network assets** within the scenario, forming the basis for risk and threat analysis.


## 3. Threat & Attack Path Analysis

**Goal:** Determine what could go wrong and how attackers might move through the network.

### Questions Considered

- What could go wrong in this network?  
- How could an attacker gain access or move laterally?  
- What would be the impact on operations and reputation?

### Example Threat Scenarios

- **Wireless network compromise** (e.g. weak encryption, rogue APs)  
- **Router/switch misconfiguration** leading to exposure or unauthorised access  
- **Cloud connection exploited** to pivot between divisions  
- **Malware spreading** across a flat or poorly segmented network  
- **Star topology single point of failure**, where a central device outage impacts all divisions :contentReference[oaicite:3]{index=3}  

These scenarios were used to qualitatively assess **likelihood and impact** for different parts of the network.


## 4. Network Topology Analysis

**Goal:** Understand how the structure of the network affects risk and resilience.

### Topology Assessed

- **Enterprise-level topology:**  
  - Star topology, with all divisions connected to the cloud via a central hub  
- **Office-level topology:**  
  - Devices connected to a central router and then to the cloud  

### Observations

- **Single Point of Failure**:  
  - Failure of the **core router or central link** can disrupt all offices.  
- **Lateral Movement Risk**:  
  - Without proper segmentation, compromise in one area could allow attackers to move to other divisions or offices.  

 This analysis supports both **risk assessment** and **SOC monitoring priorities**, highlighting where detection and controls are most needed.


## 5. Recommended Security Controls & Tools

**Goal:** Propose realistic mitigations and tools to reduce identified risks.

### Security Controls

- **Network Segmentation**  
  - Reduces lateral movement and limits blast radius of a compromise.  
- **Network Access Control (NAC)**  
  - Ensures only authorised and compliant devices can connect.  
- **Intrusion Detection / Prevention Systems (IDS / IPS)**  
  - Monitors network traffic for malicious patterns or anomalies.  
- **Malware Scanning and Endpoint Protection**  
  - Helps detect and block malware at the endpoint level. 

### Example Tools Recommended

- **NAC Solutions**  
  - FortiNAC  
  - NordLayer  

- **Network Intrusion Detection Systems (NIDS)**  
  - Snort  
  - CrowdSec  

- **Intrusion Detection & Prevention / HIDS**  
  - OSSEC  
  - Cisco Secure IPS  

These recommendations link the **theoretical risk assessment** to practical **defensive controls** and **SOC-relevant tooling**.


## Key Outcomes

- Developed a **structured understanding** of network risks in a star-topology, cloud-connected environment.  
- Identified **critical assets, environments, and attack paths** in a scenario-based network.  
- Recommended **practical security controls and tools** to mitigate risks and improve visibility.  
- Applied the **OCTAVE Allegro framework** to organise risk analysis activities and outcomes.


## Skills Demonstrated

- Network risk assessment  
- Framework evaluation (**OCTAVE-S, FAIR, ISO 27001, OCTAVE Allegro**)  
- Threat modelling and attack path reasoning  
- Understanding of network topologies (star topology, office-level layout)  
- Mapping threats to mitigations (segmentation, NAC, IDS/IPS)  
- Awareness of SOC-relevant tools (Snort, CrowdSec, OSSEC, FortiNAC, NordLayer)
