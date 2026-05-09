# 🔐 SOC Anomaly Detection Mini Lab

## 📌 Project Overview

This project demonstrates a hands-on Security Operations Center (SOC) monitoring and detection workflow using Wireshark and Splunk SIEM.

The lab focuses on:
- Network traffic analysis
- Attack simulation
- Log monitoring
- Failed login detection
- Dashboard visualization
- Alert generation
- Incident documentation

The environment was built using Kali Linux, Windows VM, Splunk Enterprise, and UTM virtualization on Mac.

---

# 🎯 Objectives

- Understand baseline network traffic
- Capture and analyze packets using Wireshark
- Simulate attacks using Kali Linux
- Detect abnormal traffic patterns
- Monitor Windows security logs
- Detect failed login attempts
- Create SOC dashboards and alerts
- Document security incidents

---

# 🛠️ Tools & Technologies

- Kali Linux
- Windows 11 VM
- Wireshark
- Splunk Enterprise
- Windows Event Logs
- UTM Virtualization
- VS Code
- GitHub

---

# 🧪 Phase 1 — Wireshark Traffic Analysis

## Activities Performed

- Captured live network traffic
- Analyzed TCP and SYN packets
- Detected suspicious scanning behavior
- Investigated abnormal traffic patterns

## Skills Learned

- Packet inspection
- Network protocol analysis
- Traffic baseline creation
- SYN scan detection

---

# 📊 Phase 2 — Splunk SIEM Monitoring

## Activities Performed

- Ingested Windows Event Logs into Splunk
- Monitored failed login attempts
- Created Splunk dashboards
- Generated SOC alerts
- Built incident reports
- Visualized security events using charts

## Splunk Queries Used

```spl
index=main EventCode=4625
| stats count by Account_Name
