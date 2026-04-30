# 🔍 SOC Investigation Report – Anomaly Detection Lab

## 🧾 Summary
Detected abnormal TCP SYN traffic indicating a possible SYN scan attack from Kali Linux to Windows VM.

---

## 🖥️ Environment
- Source (Attacker): Kali Linux
- Destination (Target): Windows VM
- Tool Used: Wireshark

---

## 📊 Baseline Behavior
Observed normal traffic:
- DNS queries
- ICMP (ping)
- HTTPS (TLS)

---

## 🚨 Detection
Used Wireshark filter:
tcp.flags.syn == 1 && tcp.flags.ack == 0

Observed:
- Multiple SYN packets without ACK
- High frequency of connection attempts

---

## 🔎 Analysis
- Pattern matches SYN scan behavior (Nmap)
- No full TCP handshake completed
- Indicates reconnaissance phase of attack

---

## 🎯 Conclusion
This activity is classified as:
➡️ **Network reconnaissance (SYN scan attack)**

---

## 🛡️ Recommendations
- Implement IDS/IPS rules
- Monitor SYN packet spikes
- Use firewall to block suspicious IPs
