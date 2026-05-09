# Dashboard Analysis

## Dashboard Name
SOC Monitoring Dashboard

---

## Dashboard Purpose
Monitor suspicious authentication activity and failed login attempts using Splunk.

---

## Dashboard Panels

### 1. Failed Login Trends
Query:
index=main EventCode=4625
| timechart count

Purpose:
Displays failed login attempts over time to identify spikes or unusual authentication activity.

---

### 2. Targeted Accounts
Query:
index=main EventCode=4625
| stats count by Account_Name

Purpose:
Identifies accounts receiving failed login attempts.

---

## Security Relevance
These dashboard panels help security analysts:
- Monitor authentication anomalies
- Detect possible brute-force attacks
- Identify targeted user accounts
- Investigate suspicious login activity

---

## Tools Used
- Splunk Enterprise
- Windows Security Event Logs
- SPL Queries

---

## Detection Focus
Windows EventCode 4625 (Failed Login Attempt)