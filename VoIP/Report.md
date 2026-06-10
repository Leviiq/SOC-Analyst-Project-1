CASE WRITE-UP #03
================================
Challenge: VoIP (Vishing)
Date: 2026-06-09
Severity: High
Platform: LetsDefend
================================

Hypothesis:
An external attacker conducted a voice phishing (Vishing) attack by impersonating a bank and targeting employee James (extension 7001) in order to obtain sensitive personal information.

================================
Investigation Steps:
1. Opened the PCAP file using Wireshark.
2. Filtered SIP traffic to identify call initiation events (SIP INVITE).
3. Identified the first call attempt and extracted timestamps and caller details.
4. Analyzed VoIP signaling and RTP streams to confirm call flow and audio content.
5. Verified impersonation details and sensitive information disclosed during the call.

================================
Evidence:
| Evidence Type | Description |
|---------------|-------------|
| SIP INVITE | Incoming call from 01326947697 to extension 7001 at 2024-05-03 20:36:36 UTC |
| VoIP Audio | Caller impersonated "Bank of Wealth" during the conversation |
| Call Content | Sensitive information including Social Number (5678) was disclosed |

================================
Tools Used:
- Wireshark

================================
MITRE ATT&CK Mapping:
- T1566 - Phishing (Initial Access) 
- T1598 - Phishing for Information (Reconnaissance)

================================
IOCs:
- 01326947697 (Malicious caller phone number)
- 7001 (Target extension - James)
- Bank of Wealth (Impersonated organization)
- 2024-05-03 20:36:36 UTC (Call initiation timestamp)

================================
Classification:
True Positive

================================
Containment Actions:
- Blocked the malicious phone number (01326947697) in the VoIP system.
- Terminated the suspicious call targeting extension 7001.
- Flagged call records and logs for further SOC monitoring and investigation.

================================
Time to Complete:
00:10:00

================================
Lessons Learned:
- VoIP systems can be exploited using social engineering techniques such as Vishing.
- Users should be trained to verify callers before sharing any sensitive information.
- Official communication channels should always be used to confirm banking requests.
- Continuous monitoring of VoIP traffic helps in early detection of phishing attempts.

