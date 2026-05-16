# MITRE ATT&CK Mapping — Phase 4

---

# Detection 1 — Brute Force Authentication Attempts

## Technique ID
T1110

## Technique Name
Brute Force

## Tactic
Credential Access

---

# Description

Repeated failed login attempts were detected using Windows Security EventCode 4625 within Splunk SIEM.

The activity simulated brute-force authentication behavior targeting Windows user accounts.

SOC monitoring identified:
- repeated failed authentication attempts
- targeted accounts
- suspicious login behavior
- authentication attack patterns

---

# Detection Query

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
```

---

# Investigation Notes

SOC investigation activities included:
- reviewing failed login events
- identifying targeted accounts
- analyzing login timelines
- validating alert conditions
- dashboard monitoring

---

# Potential Threats

The activity may indicate:
- brute-force attacks
- password spraying
- credential guessing
- unauthorized authentication attempts

---

# ATT&CK Mapping Summary

| Technique ID | Technique Name | Tactic |
|---|---|---|
| T1110 | Brute Force | Credential Access |

---

# SOC Relevance

Brute-force authentication attacks are among the most common security incidents monitored by SOC teams.

Monitoring failed login events helps identify:
- account targeting
- credential attacks
- unauthorized access attempts
- attacker reconnaissance behavior

---

# Conclusion

This phase successfully demonstrated:
- brute-force attack detection
- Windows authentication monitoring
- Splunk SIEM analysis
- dashboard visualization
- SOC alert triage
- MITRE ATT&CK mapping