# 🔐 SOC Anomaly Detection & SIEM Monitoring Mini Lab

A hands-on cybersecurity home lab project focused on Security Operations Center (SOC) monitoring, traffic analysis, threat detection, SIEM operations, and incident investigation using Wireshark and Splunk Enterprise.

This project simulates real SOC analyst activities including:
- packet analysis
- attack detection
- log ingestion
- SIEM monitoring
- alert generation
- dashboard creation
- incident documentation
- security investigations

---

# 📌 Project Goals

The purpose of this project is to develop practical SOC Analyst skills through:
- network traffic monitoring
- attack simulation
- Windows log analysis
- SIEM configuration
- security alerting
- dashboard visualization
- incident response workflow

This project was built as a learning-focused SOC environment to gain experience similar to real-world Security Operations Center activities.

---

# 🖥️ Lab Environment

## 💻 Host Machine
- MacBook Air M1

## 🧪 Virtualization
- UTM Virtualization Software

## ⚔️ Attacker Machine
- Kali Linux VM

## 🎯 Victim Machine
- Windows 11 VM

## 📊 SIEM Platform
- Splunk Enterprise

---

# 🛠️ Technologies & Tools Used

| Tool | Purpose |
|------|----------|
| Wireshark | Packet capture & traffic analysis |
| Splunk Enterprise | SIEM monitoring & log analysis |
| Kali Linux | Attack simulation |
| Windows Event Logs | Security event generation |
| UTM | Virtualization |
| VS Code | Documentation |
| GitHub | Project hosting |
| CMD/PowerShell | System interaction |

---

# 🎯 Skills Demonstrated

## 🔍 SOC Analyst Skills
- Security monitoring
- Threat detection
- Incident analysis
- Log investigation
- Event correlation
- Alert tuning
- Dashboard analysis
- Incident reporting

## 🌐 Networking Skills
- TCP/IP analysis
- SYN packet detection
- Traffic inspection
- Port scan analysis

## 📊 SIEM Skills
- Log ingestion
- Splunk query writing
- Dashboard creation
- Alert engineering
- Visualization analysis

---

# 🧪 PHASE 1 — Wireshark Traffic Analysis

---

## 📌 Objective

To understand normal network behavior and identify suspicious traffic using packet analysis.

---

## ⚔️ Attack Simulation

Attack traffic was generated from:
- Kali Linux VM

Target:
- Windows 11 VM

Simulated activities included:
- TCP communication
- SYN scanning
- abnormal packet activity

---

## 📊 Traffic Analysis Performed

### ✅ Baseline Traffic Monitoring
Normal network behavior was observed to understand:
- packet flow
- protocol usage
- communication patterns

### ✅ TCP Packet Analysis
Captured and analyzed:
- TCP handshake
- source/destination IPs
- packet sequence behavior

### ✅ SYN Scan Detection
Detected suspicious SYN traffic which may indicate:
- reconnaissance
- port scanning activity

---

## 🧠 Skills Learned in Phase 1

- Packet inspection
- Wireshark filtering
- Traffic baseline creation
- Suspicious packet identification
- TCP/SYN analysis
- Initial SOC investigation workflow

---

# 📊 PHASE 2 — Splunk SIEM Monitoring

---

## 📌 Objective

To ingest Windows security logs into Splunk and perform SIEM-based monitoring and detection.

---

# 🔄 Log Flow Architecture

```text
Windows Event Logs
        ↓
Splunk Forwarding/Input
        ↓
Splunk Enterprise
        ↓
Search Queries
        ↓
Dashboards & Alerts
        ↓
Incident Investigation

# 📥 Log Ingestion

Security logs from the Windows VM were successfully ingested into Splunk SIEM for monitoring and investigation.

### Logs Included
- Authentication events
- Failed login attempts
- Windows security events
- Account activity logs

---

# 🚨 Security Use Cases Implemented

## ✅ Failed Login Detection

### Monitored Event
- `EventCode 4625`

### Purpose
- Detect authentication failures
- Identify suspicious login attempts
- Monitor abnormal login behavior

---

## ✅ Multiple Failed Login Monitoring

Repeated failed logins were monitored to identify potentially malicious behavior.

### Potential Indicators
- Brute-force attacks
- Password spraying
- Account targeting
- Unauthorized authentication attempts

---

# 🔎 Splunk Queries Used

## 📌 Failed Login Detection

```spl
index=main EventCode=4625
---

# 🧪 PHASE 3 — Advanced Detection & Incident Response

## 📌 Objective

The objective of Phase 3 was to simulate advanced SOC threat hunting and incident response workflows using Splunk SIEM and imported attack datasets.

This phase focused on:
- IOC hunting
- PowerShell monitoring
- suspicious process analysis
- MITRE ATT&CK mapping
- incident response workflows
- advanced threat hunting

---

# 🔎 IOC Hunting Activities

Threat hunting queries were used to identify suspicious indicators including:
- PowerShell activity
- suspicious process execution
- temporary directory activity
- attacker-like execution behavior

---

# 🚨 Detection Queries Used

## PowerShell Detection

```spl
index=main powershell
```

## Suspicious Process Detection

```spl
index=main process
```

## Temporary Directory Activity

```spl
index=main temp
```

## Combined IOC Hunt

```spl
index=main powershell OR cmd.exe OR temp
```

---

# 🛡️ MITRE ATT&CK Mapping

The following ATT&CK techniques were mapped:

| Technique ID | Technique Name | Tactic |
|---|---|---|
| T1059.001 | PowerShell | Execution |
| T1059 | Command and Scripting Interpreter | Execution |
| T1204 | User Execution | Execution |

---

# 🚨 Incident Response Workflow

The investigation simulated:
- threat hunting
- IOC analysis
- suspicious activity investigation
- dashboard monitoring
- incident response documentation
- SOC analyst workflow

---

# 📊 Dashboards & Visualizations

Dashboards were created for:
- PowerShell monitoring
- suspicious process tracking
- temporary directory activity
- IOC hunting visualizations

---

# 📸 Evidence Collected

Phase 3 evidence included:
- Splunk dashboards
- IOC hunting screenshots
- PowerShell detections
- MITRE ATT&CK reports
- incident response reports
- suspicious activity analysis

---

# 📈 Skills Demonstrated

- Threat hunting
- IOC analysis
- Detection engineering
- PowerShell monitoring
- MITRE ATT&CK mapping
- Incident response workflow
- Splunk SIEM investigation
- Dashboard analysis
- SOC documentation

---
