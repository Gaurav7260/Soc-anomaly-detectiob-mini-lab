# IOC Hunting Report

## Objective

The objective of this phase was to perform IOC (Indicators of Compromise) hunting using Splunk threat hunting datasets.

The investigation focused on identifying:
- suspicious process execution
- PowerShell activity
- command-line execution
- temporary directory activity
- attacker-related artifacts

---

# Queries Used

## PowerShell Activity

```spl
index=main powershell
```

## Suspicious Process Activity

```spl
index=main process
```

## Combined IOC Hunt

```spl
index=main powershell OR cmd.exe OR temp
```

---

# IOC Findings

The investigation identified multiple suspicious indicators including:
- PowerShell execution activity
- suspicious temporary directory activity
- possible command execution behavior
- attacker-like execution patterns

These indicators may represent:
- malware staging
- attacker persistence
- malicious scripting activity
- post-exploitation behavior

---

# Analyst Observations

The imported threat hunting datasets provided realistic attacker simulation data for SOC monitoring and investigation workflows.

IOC hunting activities improved understanding of:
- threat hunting methodology
- suspicious behavior analysis
- detection engineering
- SIEM investigation workflows

---

# Conclusion

This phase demonstrated practical IOC hunting using Splunk SIEM.

The investigation included:
- advanced search queries
- suspicious activity identification
- dashboard visualization
- MITRE ATT&CK mapping
- SOC investigation documentation

The project continues to evolve into a realistic SOC analyst threat hunting lab.
---

# Screenshots Collected

The following investigation screenshots were collected during IOC hunting activities:

- suspicious-process-detection.png
- powershell-activity-detection.png
- combined-ioc-hunting-dashboard.png

These screenshots demonstrate:
- suspicious process execution
- PowerShell activity
- attacker-like behavior
- SIEM-based investigation workflows
- Splunk IOC hunting techniques