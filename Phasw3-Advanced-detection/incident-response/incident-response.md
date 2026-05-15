# Incident Response Report

---

# Incident Summary

During SOC monitoring activities, suspicious process execution and PowerShell-related activity were identified within Splunk SIEM datasets.

The investigation focused on:
- suspicious process creation
- temporary directory execution
- PowerShell activity
- attacker-like behavior
- potential post-exploitation activity

---

# Detection Source

## SIEM Platform
Splunk Enterprise

## Log Sources
- Windows security logs
- simulated attack datasets
- process execution logs
- PowerShell activity logs

---

# Investigation Queries

## Suspicious Process Investigation

```spl
index=main process
```

## PowerShell Investigation

```spl
index=main powershell
```

## Combined Incident Investigation

```spl
index=main powershell OR temp OR process
```

---

# Investigation Findings

The investigation identified:
- suspicious process execution
- PowerShell activity
- temporary directory execution
- attacker-like command behavior

Several events indicated possible malicious execution techniques commonly associated with:
- malware staging
- command execution
- attacker persistence
- post-exploitation activity

---

# Analyst Actions Taken

The following SOC analyst activities were performed:

- reviewed suspicious logs
- analyzed process execution events
- investigated PowerShell activity
- visualized events using Splunk dashboards
- documented investigation findings
- mapped behaviors to MITRE ATT&CK techniques

---

# MITRE ATT&CK Techniques Observed

| Technique ID | Technique Name | Tactic |
|---|---|---|
| T1059.001 | PowerShell | Execution |
| T1204 | User Execution | Execution |
| T1059 | Command and Scripting Interpreter | Execution |

---

# Incident Severity

## Severity Level
Medium

## Reason
The activity demonstrated suspicious execution behavior commonly associated with attacker operations and malware execution.

---

# Recommendations

Recommended SOC response actions include:
- monitor PowerShell activity
- restrict suspicious script execution
- investigate temporary directory execution
- deploy Sysmon monitoring
- improve endpoint visibility
- enhance detection engineering rules

---

# Conclusion

This phase demonstrated a practical SOC incident response workflow using Splunk SIEM.

Activities included:
- threat hunting
- IOC analysis
- attacker behavior investigation
- SIEM monitoring
- MITRE ATT&CK mapping
- incident documentation

The project successfully simulated realistic SOC analyst investigation procedures within a controlled lab environment.