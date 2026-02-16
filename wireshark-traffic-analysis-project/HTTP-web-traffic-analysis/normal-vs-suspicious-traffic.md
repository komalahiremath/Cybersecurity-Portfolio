# HTTP Network Traffic Analysis  
## Normal Traffic vs Suspicious Web Application Attack
### Overview
This analysis compares normal HTTP web traffic with suspicious HTTP traffic indicative of a web application attack using packet capture (PCAP) analysis in Wireshark.

## Normal HTTP Traffic (First screenshot – HTTP 200 OK)
### What you see
HTTP responses: 200 OK
Content types: text/html, image/jpeg
Legitimate servers (Apache, Akamai, Skype assets)
Normal request–response flow
TCP reassembly working correctly

### Key indicators
Status Code: 200
Predictable URIs (images, webpages)
Reasonable response sizes
No abnormal retries or errors

### Example
HTTP/1.1 200 OK
Content-Type: image/jpeg
Server: Apache
This represents normal user browsing behavior where web resources are successfully retrieved.

## Suspicious HTTP Traffic (Second screenshot – HTTP 408 Request Timeout)
### What you see
HTTP Status Code: 408 Request Timeout
Repeated requests from same source
Server: AkamaiGHost
Incomplete or slow HTTP requests

### Key indicators
Status Code: 408
Delayed / incomplete HTTP headers
Possible connection exhaustion
Client not completing request in time

### Example
HTTP/1.0 408 Request Time-out
Server: AkamaiGHost

### Why this is suspicious
HTTP 408 errors are commonly associated with:
Slow HTTP attacks (Slowloris-style)
Malformed or intentionally delayed requests
Reconnaissance or DoS attempts

### Is this an HTTP Web Application Attack?
Yes — potentially
This traffic pattern aligns with:
Application-layer DoS
Slow HTTP Request Attack
Resource exhaustion attempt

### Technique	Explanation
Slow HTTP	Attacker sends partial headers slowly
DoS (Layer 7)	Targets web server resources
Timeout abuse	Forces server to hold connections
This is not a vulnerability exploit (like SQLi or XSS), but an availability attack.

### How a SOC Analyst should flag this
Detection logic
Multiple 408 responses
Same source IP
Short time window
No successful content delivery

### Suspicious HTTP Traffic (Web Application Attack)
- Characteristics
HTTP Status Code: 408 Request Timeout
Incomplete or delayed requests
Repeated failures from same source
Potential resource exhaustion
- Example
HTTP/1.0 408 Request Time-out
Server: AkamaiGHost
Repeated HTTP 408 responses suggest a possible Slow HTTP / Application-layer DoS attack, where the attacker deliberately delays requests to exhaust server resources.

### Attack Type Identification
Attack Type	Description
Slow HTTP Attack	Partial headers sent slowly
Application-layer DoS	Targets web server availability
Timeout Abuse	Forces server to hold open connections

### SOC Detection Perspective
Indicators of Compromise (IoCs)
Multiple HTTP 408 responses
Same source IP
Short time window
No completed transactions

### Conclusion

Normal HTTP traffic shows successful content delivery, while repeated HTTP 408 errors indicate suspicious behavior consistent with a web application availability attack. Early detection can prevent service disruption.
