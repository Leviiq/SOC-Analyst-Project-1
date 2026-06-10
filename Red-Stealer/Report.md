CASE WRITE-UP #02
================================
Title: Red Stealer - Trojan C2 Communication
Date: 2026-06-09
Severity: High
Platform: CyberDefenders

EXECUTIVE SUMMARY:
Investigated a Trojan executable (WEXTRACT)
identified as RedLine Stealer that communicates
with a C2 server and escalates privileges via DLL.

ATTACK TIMELINE:
- Malicious executable WEXTRACT discovered
- First seen on VirusTotal: 2023-10-06 04:41
- Malware collected data from local system
- DNS query to facebook.com to blend in
- C2 communication to 77.91.124.55:19071
- Privilege escalation via ADVAPI32.dll

MITRE ATT&CK:
- T1005  — Data Collection from Local System
- T1055  — Privilege Escalation via DLL
- T1071  — C2 Communication

IOCs:
- File: WEXTRACT (Trojan)
- C2 IP: 77.91.124.55
- C2 Port: 19071
- YARA Rule: detect_Redline_Stealer
- Alias: RECORDSTEALER
- DLL: ADVAPI32.dll

INVESTIGATION STEPS:
1. Searched file hash on VirusTotal
2. Identified malware as Trojan/WEXTRACT
3. Found MITRE ATT&CK technique T1005
4. Identified C2 IP and port
5. Found YARA rule on MalwareBazaar
6. Confirmed alias on ThreatFox

CONTAINMENT ACTIONS:
- Block C2 IP: 77.91.124.55 at Firewall
- Block Port: 19071
- Remove malware from affected system
- Monitor ADVAPI32.dll unusual usage

LESSONS LEARNED:
- VirusTotal gives complete malware details
- MalwareBazaar useful for YARA rules
- ThreatFox links IPs to malware families
- Malware used facebook.com DNS to hide traffic
================================
