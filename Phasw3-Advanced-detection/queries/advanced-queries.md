# Advanced Threat Hunting Queries

---

# PowerShell Activity Detection

```spl
index=main powershell
```

Purpose:
Detect PowerShell execution activity.

---

# Suspicious Process Detection

```spl
index=main process
```

Purpose:
Identify suspicious process creation events.

---

# Temporary Directory Activity

```spl
index=main temp
```

Purpose:
Detect execution activity originating from temporary directories.

---

# Combined IOC Hunt

```spl
index=main powershell OR cmd.exe OR temp
```

Purpose:
Perform broad IOC hunting across suspicious activity indicators.

---

# Visualization Query

```spl
index=main temp | timechart count
```

Purpose:
Visualize suspicious activity trends over time.

---

# MITRE ATT&CK Detection Query

```spl
index=main powershell | stats count by source
```

Purpose:
Support MITRE ATT&CK mapping and investigation workflows.