CASE WRITE-UP #01
================================
Title: Phishing Email - PayPal Campaign
Date: 2026-06-01
Severity: High
Platform: LetsDefend

EXECUTIVE SUMMARY:
Investigated a phishing email impersonating 
PayPal targeting users to harvest credentials
via a fake login page.

ATTACK TIMELINE:
- Email delivered to target
- User received suspicious PayPal email
- Email contained malicious link
- Link redirected to credential harvesting page

MITRE ATT&CK:
- T1566.002 — Spearphishing Link
- T1078 — Valid Accounts

IOCs:
- Domain: storage.googleapis.com (malicious path)
- Return-Path: bounce@designclub.uk.com
- SHA-256: 13945ecc33afee74ac7f72e1d5bb73050894356c4bf63d02a1a53e76830567f5

INVESTIGATION STEPS:
1. Analyzed email headers
2. Identified spoofed sender domain
3. Checked URL on VirusTotal
4. Confirmed DNS Shadowing attack

CONTAINMENT ACTIONS:
- Block malicious URL
- Reset affected passwords
- Enable MFA

LESSONS LEARNED:
- Legitimate domains used for phishing
- Always inspect full URL not just domain
- DNS Shadowing bypasses traditional filters
================================
