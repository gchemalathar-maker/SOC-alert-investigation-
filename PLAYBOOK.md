# 🛡️ 50+ SOC Alerts - Complete Investigation Playbook

### How to Investigate ANY Alert in 4 Steps

**STEP 1 - ENTITIES TAB:**
- NT SERVICE\MSExchange, MicrosoftDefenderForClouds, [::1] = REAL/Benign
- mirage, Tor, M247, Anonymous = FRAUD/True Positive

**STEP 2 - THREAT INTEL:**
- AbuseIPDB.com / VirusTotal.com lo IP/File check
- No Results = REAL, Red/Malicious = FRAUD

**STEP 3 - LOGS:**
- Sentinel -> SigninLogs, AuditLogs
- KQL: SigninLogs | where UserPrincipalName == "victim"

**STEP 4 - ACTION:**
- REAL = Close as Benign
- FRAUD = Reset Password + Block IP + Isolate Device

---

### TOP 50 ALERTS LIST

1. Impossible Travel
2. Anonymous IP / Tor
3. Brute Force / Password Spray
4. Suspicious Inbox Forwarding
5. Unfamiliar Sign-in Properties
6. Risky Sign-in
7. Phishing Email Reported
8. Malicious URL Clicked
9. Malware Detected
10. Ransomware Activity
11. Credential Access - Mimikatz
12. PowerShell Suspicious
13. Data Exfiltration
14. Privilege Escalation
15. Lateral Movement
16. MFA Fatigue Attack
17. Conditional Access Bypass
18. OAuth Consent Grant - Malicious App
19. SharePoint File Exfiltration
20. impossible etc...

Tools: Sentinel, AbuseIPDB, VirusTotal, Talos

Author: gchemalathar-maker | Kadapa SOC Lab
