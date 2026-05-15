# 🧪 SOC Investigation Report  
## Wireshark Traffic Analysis + Splunk SIEM Monitoring

---

## 1. Investigation Overview

This investigation documents a practical SOC analyst workflow performed in a home lab environment.

The project was divided into two major phases:

- **Phase 1:** Network traffic analysis using Wireshark  
- **Phase 2:** SIEM monitoring and detection using Splunk Enterprise  

The main goal was to simulate suspicious activity, collect evidence, analyze logs, create detections, build dashboards, and document findings like a real SOC investigation.

---

## 2. Lab Environment

| Component | Details |
|---|---|
| Host Machine | MacBook Air |
| Virtualization | UTM |
| Attacker Machine | Kali Linux VM |
| Victim Machine | Windows VM |
| SIEM Tool | Splunk Enterprise |
| Packet Analysis Tool | Wireshark |
| Log Source | Windows Security Event Logs |

---

## 3. Phase 1 — Wireshark Network Investigation

### Objective

The goal of Phase 1 was to understand network traffic behavior and identify suspicious TCP/SYN activity using Wireshark.

### Activity Performed

Network traffic was captured and analyzed between the attacker and victim machines.

The investigation focused on:

- TCP packets
- SYN packets
- source and destination IP addresses
- suspicious scanning behavior
- packet-level evidence

### Key Findings

- TCP communication was observed between systems.
- SYN packets were identified during traffic analysis.
- Suspicious traffic patterns were reviewed using Wireshark filters.
- Packet captures helped understand how reconnaissance/scanning activity appears at the network level.

### Wireshark Skills Practiced

- Packet capture
- TCP analysis
- SYN flag analysis
- Traffic filtering
- Network investigation
- Baseline traffic understanding

---

## 4. Phase 2 — Splunk SIEM Investigation

### Objective

The goal of Phase 2 was to ingest Windows Security logs into Splunk and detect suspicious authentication activity.

### Log Source

Windows Security Event Logs were added to Splunk as a data input.

The monitored logs included:

- authentication events
- failed login attempts
- account activity
- security event records

---

## 5. Detection Use Case — Failed Login Attempts

### Event Code Monitored

```text
EventCode 4625
EventCode 4624

Meaning
EventCode 4625 represents a failed login attempt in Windows Security logs.
Why This Matters
Multiple failed login attempts may indicate:
brute-force attack
password guessing
password spraying
unauthorized access attempt
account targeting
6. Splunk Queries Used
Failed Login Detection
Spl
index=main EventCode=4625
Purpose:
Detects failed login events from Windows Security logs.
Failed Login Count by Account
Spl
index=main EventCode=4625
| stats count by Account_Name
Purpose:
Groups failed login attempts by account name to identify targeted users.
Failed Login Timeline
Spl
index=main EventCode=4625
| timechart count
Purpose:
Shows failed login activity over time to identify spikes or suspicious trends.
Targeted Account Analysis
Spl
index=main EventCode=4625
| stats count by Account_Name
| sort -count
Purpose:
Displays accounts with the highest number of failed login attempts.
7. Dashboard Created
Dashboard Name
Plain text
SOC Monitoring Dashboard
Dashboard Panels
Failed Login Trends
Used to visualize failed login attempts over time.
Targeted Accounts
Used to identify which accounts received failed login attempts.
Dashboard Value
The dashboard helps a SOC analyst quickly understand:
when failed logins happened
which accounts were targeted
whether activity is increasing
whether further investigation is needed
8. Alert Created
Alert Name
Plain text
Multiple Failed Login Detection
Alert Purpose
To detect suspicious failed login activity and simulate SOC alerting.
Trigger Logic
Spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
Trigger Condition
Alert triggers when the search returns results.
Alert Action
The alert was configured to appear in triggered alerts.
9. Investigation Findings
During the investigation:
Windows Security logs were successfully ingested into Splunk.
Failed login events were detected using EventCode=4625.
Account-based failed login analysis was performed.
Dashboard panels were created for visual monitoring.
A scheduled alert was configured for suspicious failed login activity.
Screenshots and evidence were stored for GitHub documentation.
10. Evidence Collected
Evidence collected during this project includes:
Phase 1 Evidence
Wireshark TCP packet screenshots
SYN packet analysis screenshots
traffic capture evidence
Phase 2 Evidence
Splunk log ingestion screenshots
failed login detection screenshots
dashboard screenshots
alert configuration screenshots
account analysis screenshots
11. Security Impact
Repeated failed login attempts can be an early sign of credential-based attacks.
Possible risks include:
unauthorized access
account compromise
credential brute forcing
lateral movement after successful login
Monitoring failed login activity is important for early detection.
12. Recommended Response Actions
A SOC analyst should:
review targeted accounts
check source IP or host details
verify whether the activity is expected
check successful login events after failed attempts
escalate if repeated failures continue
recommend stronger password and account lockout policies
13. Skills Demonstrated
This investigation demonstrates:
Wireshark packet analysis
TCP/SYN traffic investigation
Splunk log ingestion
SPL query writing
failed login detection
dashboard creation
alert configuration
incident reporting
SOC workflow documentation
14. Future Improvements
Future improvements planned:
brute-force simulation
Sysmon integration
PowerShell monitoring
MITRE ATT&CK mapping
exported Splunk reports
incident response workflow
advanced detection rules
15. Conclusion
This investigation successfully demonstrated a beginner SOC workflow by combining network-level analysis with SIEM-based log monitoring.
Phase 1 showed how suspicious activity can be observed through packet analysis using Wireshark.
Phase 2 showed how Windows security events can be ingested into Splunk, analyzed using SPL queries, visualized through dashboards, and monitored using alerts.
This project provides practical experience for SOC Analyst learning, cybersecurity portfolio development, and interview preparation

---

# Phase 3 — Advanced Detection & Incident Response

Phase 3 expanded the SOC lab into advanced threat hunting and incident response workflows.

The phase included:
- IOC hunting
- PowerShell monitoring
- suspicious process investigation
- MITRE ATT&CK mapping
- incident response documentation
- Splunk threat hunting dashboards

Advanced threat hunting datasets were imported into Splunk SIEM to simulate realistic attacker activity and SOC analyst investigations.

The investigation demonstrated:
- detection engineering
- incident analysis
- IOC hunting
- dashboard monitoring
- SOC workflow documentation
