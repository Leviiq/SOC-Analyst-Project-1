CASE WRITE-UP #02
================================
Title: DanaBot - Malicious JavaScript Delivery
Date: 2026-06-09
Severity: High
Platform: CyberDefenders

EXECUTIVE SUMMARY:
Investigated a DanaBot malware infection where
attacker delivered malicious JavaScript via HTTP
to compromise a victim machine and establish C2.

ATTACK TIMELINE:
- DNS query to portfolio.serveirc.com
- HTTP GET request to login.php
- Malicious file allegato_708.js downloaded
- wscript.exe executed the JavaScript
- resources.dll downloaded from soundata.top
- C2 communication established

MITRE ATT&CK:
- T1566    — Phishing Initial Access
- T1059.007 — JavaScript Execution
- T1218.011 — Rundll32 Execution
- T1071.001 — C2 Communication

IOCs:
- Attacker IP: 62.173.124.18
- Domain: portfolio.serveirc.com
- Domain: soundata.top
- File: allegato_708.js
- File: resources.dll

INVESTIGATION STEPS:
1. Filtered DNS traffic in Wireshark
2. Found suspicious domain portfolio.serveirc.com
3. Exported HTTP Objects and found login.php
4. Identified real filename allegato_708.js
5. Extracted hashes via PowerShell
6. Verified IOCs on VirusTotal

CONTAINMENT ACTIONS:
- Block IP: 62.173.124.18
- Block domains at web proxy
- Remove resources.dll from system
- Scan all endpoints

LESSONS LEARNED:
- Attackers hide malicious files behind PHP names
- Always check HTTP Object Export in Wireshark
- .js files executed silently via wscript.exe
================================
