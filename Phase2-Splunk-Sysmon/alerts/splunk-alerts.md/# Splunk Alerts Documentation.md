# Splunk Alerts Documentation

## Alert Name
Multiple Failed Login Detection

---

## Purpose
Detects multiple failed login attempts that may indicate brute-force activity.

---

## SPL Query
index=main EventCode=4625
| stats count by Account_Name
| where count > 3

---

## Trigger Condition
Trigger alert when result count is greater than 0.

---

## Alert Type
Scheduled Alert

---

## Monitoring Goal
Identify suspicious authentication failures and possible attacker activity.

---

## Severity
Medium

---

## Recommended Analyst Action
- Investigate targeted account
- Check source system activity
- Review authentication logs
- Escalate if repeated attempts continue