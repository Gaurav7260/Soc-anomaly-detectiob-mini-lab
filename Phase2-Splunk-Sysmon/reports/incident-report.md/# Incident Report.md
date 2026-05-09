# Incident Report

## Incident Title
Multiple Failed Login Attempts Detected

---

## Incident Summary
Suspicious failed login activity was detected in Windows Security logs using Splunk SIEM.

---

## Environment
- Host System: Mac
- SIEM Platform: Splunk Enterprise
- Target Machine: Windows VM
- Attacker Simulation Source: Manual failed login attempts

---

## Detection Method
Windows Security Event Logs were ingested into Splunk and analyzed using SPL queries.

---

## Relevant Event Code
EventCode 4625

Description:
Failed login attempt detected.

---

## SPL Query Used
index=main EventCode=4625
| stats count by Account_Name

---

## Investigation Findings
- Multiple failed login attempts were observed.
- User accounts receiving authentication failures were identified.
- Failed authentication events were successfully visualized using Splunk dashboards.
- Alert logic was configured for repeated failed login attempts.

---

## Security Impact
Repeated failed login attempts may indicate:
- Brute-force activity
- Password guessing attacks
- Unauthorized authentication attempts

---

## Recommended Response Actions
- Monitor repeated authentication failures
- Review targeted accounts
- Investigate source systems
- Implement account lockout policies if necessary

---

## Outcome
Successfully detected and monitored failed login activity using Splunk SIEM.