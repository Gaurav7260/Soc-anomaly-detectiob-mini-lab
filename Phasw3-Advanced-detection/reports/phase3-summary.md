# Phase 3 Summary — Advanced Detection & Incident Response

---

# Objective

The objective of Phase 3 was to simulate advanced SOC detection engineering and incident response workflows using Splunk SIEM.

This phase focused on:
- IOC hunting
- PowerShell monitoring
- suspicious process detection
- MITRE ATT&CK mapping
- incident investigation
- SOC documentation

---

# Activities Performed

## IOC Hunting
Threat hunting queries were used to identify suspicious indicators including:
- PowerShell activity
- suspicious process execution
- temporary directory activity
- attacker-like execution behavior

---

## MITRE ATT&CK Mapping
Detected activities were mapped to MITRE ATT&CK techniques including:
- T1059.001 — PowerShell
- T1059 — Command and Scripting Interpreter
- T1204 — User Execution

---

## Incident Response Workflow
A SOC-style incident investigation workflow was simulated including:
- event investigation
- log analysis
- dashboard monitoring
- incident documentation
- analyst observations
- security recommendations

---

# Splunk Queries Used

```spl
index=main powershell
```

```spl
index=main process
```

```spl
index=main temp
```

```spl
index=main powershell OR cmd.exe OR temp
```

---

# Key Learning Outcomes

This phase improved practical understanding of:
- SIEM monitoring
- threat hunting
- detection engineering
- incident response
- IOC analysis
- MITRE ATT&CK mapping
- Splunk dashboarding
- SOC workflows

---

# Conclusion

Phase 3 successfully simulated realistic SOC analyst investigation procedures using Splunk SIEM and threat hunting datasets.

The project now demonstrates:
- detection engineering
- advanced log analysis
- IOC hunting
- incident response workflows
- MITRE ATT&CK integration
- professional SOC documentation