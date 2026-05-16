# Incident Response Report — Phase 4

---

# Incident Title

Brute Force Authentication Attack Simulation

---

# Incident Severity

Medium

---

# Incident Summary

During SOC monitoring activities, repeated failed login attempts were detected against Windows user accounts within the lab environment.

The activity simulated brute-force authentication attacks commonly investigated by SOC analysts.

The investigation identified:
- repeated failed login attempts
- targeted account activity
- suspicious authentication behavior
- attack timeline patterns

---

# Detection Source

## SIEM Platform
Splunk Enterprise

## Log Source
Windows Security Logs

## Event ID
4625 — Failed Login Attempt

---

# Detection Queries

## Failed Login Detection

```spl
index=main EventCode=4625
```

---

## Targeted Account Analysis

```spl
index=main EventCode=4625
| stats count by Account_Name
| sort -count
```

---

## Failed Login Timeline

```spl
index=main EventCode=4625
| timechart count
```

---

## Brute Force Detection Logic

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
```

---

# Investigation Findings

The investigation identified repeated authentication failures targeting user accounts within the Windows VM environment.

Observed behavior included:
- multiple failed login attempts
- repeated account targeting
- authentication attack patterns
- suspicious login timelines

The activity demonstrated behavior commonly associated with:
- brute-force attacks
- password spraying
- unauthorized access attempts
- credential guessing attacks

---

# SOC Analyst Actions Performed

The following SOC activities were completed:

- reviewed Windows authentication logs
- investigated failed login events
- identified targeted accounts
- analyzed attack trends
- created Splunk dashboards
- configured detection alerts
- validated alert triggers
- documented investigation findings
- mapped activity to MITRE ATT&CK

---

# Dashboards Created

The following Splunk dashboards were created:

- Failed Login Timeline
- Top Targeted Accounts
- Authentication Activity Monitoring

Dashboard visualizations included:
- line charts
- bar charts
- event statistics
- login trend analysis

---

# Alerts Configured

## Alert Name
Multiple Failed Login Detection

## Trigger Logic

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
```

## Trigger Condition
Number of Results > 0

---

# MITRE ATT&CK Mapping

| Technique ID | Technique Name | Tactic |
|---|---|---|
| T1110 | Brute Force | Credential Access |

---

# Risk Assessment

## Potential Risks

- account compromise
- unauthorized access
- credential attacks
- password spraying
- brute-force authentication attempts

---

# Recommendations

Recommended defensive measures include:

- enable account lockout policies
- enforce strong password policies
- monitor failed login attempts
- investigate authentication anomalies
- implement SIEM alerting
- improve authentication visibility

---

# Conclusion

This phase successfully simulated brute-force authentication attack detection using Splunk SIEM and Windows Security logs.

The project demonstrated:
- SOC monitoring workflows
- authentication attack detection
- dashboard engineering
- alert triage
- incident response procedures
- MITRE ATT&CK mapping
- security investigation documentation

The lab environment successfully replicated realistic SOC analyst investigation procedures within a controlled environment.