# Alert Triage Report

---

# Alert Name

Multiple Failed Login Detection

---

# Alert Severity

Medium

---

# Detection Logic

The alert was configured to detect repeated failed login attempts using Windows Security EventCode 4625.

Detection Query:

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
```

---

# Investigation Summary

The alert identified repeated failed authentication attempts against user accounts within the Windows VM environment.

Observed behavior included:
- repeated login failures
- targeted account activity
- suspicious authentication behavior

The activity simulated brute-force attack behavior commonly investigated by SOC analysts.

---

# SOC Analyst Actions

The following investigation activities were performed:

- reviewed authentication logs
- analyzed failed login events
- identified targeted accounts
- reviewed login activity trends
- monitored dashboard visualizations
- validated alert trigger conditions

---

# Risk Assessment

## Potential Risks

- brute-force attacks
- password spraying
- unauthorized authentication attempts
- account compromise attempts

---

# Analyst Assessment

The activity was classified as suspicious authentication behavior requiring monitoring and investigation.

No successful compromise was confirmed during the investigation.

---

# Recommendations

Recommended defensive actions include:

- enforce strong passwords
- enable account lockout policies
- monitor failed login activity
- investigate repeated authentication failures
- improve authentication monitoring

---

# Conclusion

This phase successfully simulated brute-force attack detection and SOC alert triage procedures using Splunk SIEM.

The investigation demonstrated:
- authentication monitoring
- alert engineering
- SOC investigation workflow
- dashboard analysis
- incident documentation