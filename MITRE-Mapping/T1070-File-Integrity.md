
# MITRE ATT&CK Mapping – File Integrity Monitoring

---

# Technique Information

| Field | Value |
|--------|-------|
| Repository File | T1070-File-Integrity.md |
| Lab | LAB 05 – File Integrity Monitoring |
| ATT&CK Tactic | Defense Evasion |
| ATT&CK Technique | T1070 – Indicator Removal on Host *(Repository Mapping)* |
| Detection Platform | Wazuh |
| Endpoint | Windows 10 |

---

# Overview

File Integrity Monitoring (FIM) is a defensive security capability that detects unauthorized changes to monitored files and directories.

In this lab, Wazuh Syscheck was configured to monitor a dedicated directory (`C:\FIM`) in real time. Any file creation, modification, or deletion generated alerts, allowing the SOC analyst to investigate suspicious file system activity.

Although File Integrity Monitoring itself is not a MITRE ATT&CK technique, it is commonly used to detect activities associated with techniques such as Indicator Removal on Host, where attackers modify or delete files to hide evidence of malicious actions.

---

# Lab Scenario

A monitored directory was configured on the Windows endpoint.

The following activities were simulated:

- Creating a new file
- Modifying an existing file
- Deleting the monitored file

Each action generated Wazuh File Integrity Monitoring alerts.

---

# Attack Simulation

## Step 1 – File Creation

Created:

```
C:\FIM\Important-Data.txt
```

Generated Alert

```
File added to the system
```

Rule ID

```
554
```

---

## Step 2 – File Modification

Modified the file contents.

Generated Alert

```
Integrity checksum changed
```

Rule ID

```
550
```

---

## Step 3 – File Deletion

Deleted the monitored file.

Generated Alert

```
File deleted / File removed
```

---

# Detection Logic

Wazuh Syscheck continuously monitored the configured directory.

Whenever a file operation occurred:

```
Windows Endpoint

↓

Wazuh Agent

↓

Syscheck

↓

Event Generated

↓

Wazuh Manager

↓

Alert Created

↓

SOC Investigation
```

---

# Wazuh Detection

The following activities were successfully detected:

| Activity | Detection |
|-----------|-----------|
| File Creation | Detected |
| File Modification | Detected |
| File Deletion | Detected |

---

# Indicators Observed

| Indicator | Value |
|-----------|-------|
| Endpoint | DESKTOP-M8DPQQK |
| Directory | C:\FIM |
| File | Important-Data.txt |
| Detection Module | Syscheck |

---

# MITRE ATT&CK Mapping

| ATT&CK Tactic | Technique | Description |
|--------------|-----------|-------------|
| Defense Evasion | T1070 | Indicator Removal on Host |

Repository Note:

This project uses **T1070-File-Integrity.md** to maintain consistency with the repository structure.

---

# Detection Opportunities

SOC analysts should investigate when they observe:

- Unexpected file creation
- Unauthorized file modification
- Integrity checksum changes
- Unexpected file deletion
- Repeated changes to sensitive files
- Changes outside approved maintenance windows

---

# Defensive Recommendations

- Enable File Integrity Monitoring on critical directories.
- Use real-time monitoring for sensitive locations.
- Investigate checksum change alerts immediately.
- Correlate File Integrity Monitoring alerts with Sysmon Process Creation events.
- Maintain baseline file integrity for important systems.
- Review deleted critical files during incident investigations.

---

# Skills Demonstrated

- File Integrity Monitoring
- Wazuh Syscheck Configuration
- Endpoint Monitoring
- Alert Investigation
- Blue Team Detection
- MITRE ATT&CK Mapping
- Security Event Analysis

---

# Learning Outcome

This lab demonstrates how File Integrity Monitoring improves endpoint visibility by detecting unauthorized file system activity.

The exercise highlights how Wazuh assists SOC analysts in identifying suspicious file operations that may indicate attacker behavior or attempts to remove evidence from a compromised host.

---

# Conclusion

The File Integrity Monitoring lab successfully demonstrated Wazuh's ability to detect file creation, file modification, and file deletion events in real time.

These detections provide valuable visibility into endpoint activity and support effective incident investigation within a Security Operations Center (SOC).
