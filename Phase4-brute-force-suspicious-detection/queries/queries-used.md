# Queries Used — Phase 4

---

# Windows Authentication Monitoring

## Failed Login Events

```spl
index=main EventCode=4625
```

### Purpose
Detect failed Windows authentication attempts.

---

# Targeted Account Analysis

```spl
index=main EventCode=4625
| stats count by Account_Name
| sort -count
```

### Purpose
Identify accounts receiving repeated failed login attempts.

---

# Brute Force Detection Logic

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
```

### Purpose
Detect possible brute-force authentication activity.

---

# Authentication Timeline Monitoring

```spl
index=main EventCode=4625
| timechart count
```

### Purpose
Visualize failed login trends over time.

---

# Top Targeted Accounts

```spl
index=main EventCode=4625
| top Account_Name
```

### Purpose
Identify frequently targeted accounts.

---

# Dashboard Queries

## Failed Login Timeline

```spl
index=main EventCode=4625
| timechart count
```

---

## Account Targeting Statistics

```spl
index=main EventCode=4625
| stats count by Account_Name
| sort -count
```

---

# Alert Query

## Multiple Failed Login Detection

```spl
index=main EventCode=4625
| stats count by Account_Name
| where count > 3
```

### Alert Trigger
Trigger alert when suspicious repeated failed login attempts are detected.

---

# Investigation Outcome

The queries successfully detected:
- repeated failed logins
- suspicious authentication activity
- targeted accounts
- brute-force attack behavior

The investigation simulated realistic SOC monitoring and authentication attack detection workflows using Splunk SIEM.