# Splunk Queries Used

## Failed Login Detection
index=main EventCode=4625

Description:
Detects failed login attempts from Windows Security logs.

---

## Failed Login Trend Analysis
index=main EventCode=4625
| timechart count

Description:
Visualizes failed login attempts over time.

---

## Targeted Account Analysis
index=main EventCode=4625
| stats count by Account_Name

Description:
Displays accounts receiving failed login attempts.

---

## Multiple Failed Login Alert
index=main EventCode=4625
| stats count by Account_Name
| where count > 3

Description:
Used for detecting possible brute-force login attempts.