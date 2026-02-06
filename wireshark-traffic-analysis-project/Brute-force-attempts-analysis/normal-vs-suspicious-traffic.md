##  Brute-Force Attack Indicators  
Brute-force behaviours in Wireshark are identified through:

### FTP  
```
ftp contains "530"
```
Repeated "Login incorrect" messages = brute-force attempt.

### SSH  
```
ssh contains "Failed"
```

### HTTP  
Repeated POST requests to login pages.

---
