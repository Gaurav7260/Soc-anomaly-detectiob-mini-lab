# MITRE ATT&CK Mapping

---

# Detection 1 — PowerShell Activity

## Technique ID
T1059.001

## Technique Name
PowerShell

## Tactic
Execution

## Description
PowerShell activity was identified during advanced threat hunting activities in Splunk.

PowerShell is commonly abused by attackers for:
- malicious scripting
- remote command execution
- malware deployment
- persistence mechanisms
- post-exploitation activity

Monitoring PowerShell activity is an important SOC detection use case because attackers frequently use PowerShell for stealthy operations.

## Detection Query

```spl
index=main powershell
| timechart count
```

## SOC Investigation Notes
The detection identified PowerShell-related events within imported threat hunting datasets. Event activity was visualized through Splunk dashboards for monitoring and investigation purposes.

---

# Detection 2 — Suspicious Temp Activity

## Technique ID
T1204

## Technique Name
User Execution

## Tactic
Execution

## Description
Suspicious activity originating from temporary directories was detected using Splunk threat hunting queries.

Attackers commonly use temporary folders for:
- malware staging
- payload execution
- evasion techniques
- temporary script execution

Monitoring temp directory activity helps SOC analysts identify suspicious behavior associated with malware infections and attacker execution chains.

## Detection Query

```spl
index=main temp
| timechart count
```

## SOC Investigation Notes
The detection highlighted suspicious temporary execution activity. Timeline visualization panels were created in Splunk dashboards to support threat hunting and security monitoring.

---

# Importance of MITRE ATT&CK Mapping

MITRE ATT&CK mapping helps SOC analysts:
- classify attacker behavior
- understand attack techniques
- improve detection engineering
- enhance incident response workflows
- standardize threat intelligence analysis

MITRE ATT&CK is widely used by:
- SOC teams
- threat hunters
- security engineers
- incident responders
- cybersecurity researchers

---

# Analyst Conclusion

This phase demonstrated:
- advanced Splunk threat hunting
- detection engineering
- dashboard monitoring
- PowerShell activity analysis
- suspicious temp activity detection
- MITRE ATT&CK technique mapping

The project continues to evolve toward a realistic SOC monitoring and threat detection lab environment.