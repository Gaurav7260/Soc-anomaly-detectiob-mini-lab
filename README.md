# 🔐 SOC Anomaly Detection Lab1

## 📌 Project Overview
This project demonstrates a basic Security Operations Center (SOC) workflow using Wireshark to analyze network traffic, establish a baseline, and detect anomalies.

---

## 🎯 Objectives
- Understand normal network traffic (baseline)
- Capture and analyze packets using Wireshark
- Simulate attacks using Kali Linux
- Detect abnormal traffic patterns

---

## 🛠️ Tools & Technologies
- Wireshark
- Kali Linux
- Windows VM
- UTM (Virtualization)

---

## 🧪 Lab Setup
- Host: Mac
- VM 1: Windows (target system)
- VM 2: Kali Linux (attacker)

---

## 📊 Project Workflow

### 1️⃣ Baseline Traffic Analysis
Captured normal traffic:
- DNS queries
- ICMP (ping)
- TLS/HTTPS traffic

📸 Example:
![DNS Baseline](screenshots/baseline/dns_baseline.png)

---

### 2️⃣ Attack Simulation
Simulated SYN scan using Nmap:
```bash
nmap -sS <target-ip>
