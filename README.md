# SOC-alert-investigation-
50+  soc alerts master playbook
# 🛡️ SOC Alerts Investigation - Master Playbook
### For SOC Analyst L1/L2 | Kadapa SOC Lab

> 50+ Real-Time Alerts Investigation Guide | Microsoft Sentinel

This repo contains complete investigation methodology for 50+ SOC alerts.

### 🚀 How to Investigate ANY Alert (4 Steps)

**STEP 1: ENTITIES TAB**
- NT SERVICE\MSExchange / MicrosoftDefenderForClouds / [::1] = REAL (Benign)
- mirage / Unknown / Tor / M247 = FRAUD (True Positive)

**STEP 2: INSIGHTS / THREAT INTELLIGENCE**
- No Results / Clean = REAL
- Red / Malicious / 10+ vendors = FRAUD

**STEP 3: TIMELINE & LOGS**
- Use AbuseIPDB.com, VirusTotal.com

**STEP 4: VERDICT**
- REAL -> Benign Positive
- FRAUD -> True Positive -> Reset + Block + Isolate

### 📋 50+ Alerts Master List

| Alert | Type | Verdict |
|---|---|---|
| Impossible Travel | Identity | VPN=Benign, Tor=Fraud |
| Suspicious Email Deletion | O365 | Own Inbox=Benign, Others=Fraud |
| CloudTrail Stop | AWS | Admin Confirm=Benign, mirage=CRITICAL TP |
| Cloud Discovery Anomaly | DLP | Dev=Benign, HR+Tor=FRAUD |
| OAuth Credential Add | OAuth | AD Team=Benign, Else=Hijack TP |
| Honeytoken Activity | Honeypot | ALWAYS 100% TP - Isolate Machine |
| ... + 44 more | See PDF | Full guide in repo |

Full 50 Alerts PDF will be uploaded soon.

### 🔍 KQL Queries

```kusto
SecurityAlert | where AlertName contains "Impossible"
SigninLogs | where ResultType != 0
AuditLogs | where OperationName contains "Delete"
