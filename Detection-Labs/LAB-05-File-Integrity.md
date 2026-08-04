
# LAB 05 – File Integrity Monitoring (FIM)

## Objective

The objective of this lab is to configure and validate Wazuh File Integrity Monitoring (FIM) on a Windows endpoint. The lab demonstrates how Wazuh detects file creation, file modification, and file deletion events within a monitored directory. This simulates a real-world scenario where a SOC Analyst monitors unauthorized changes to critical files and investigates generated security alerts.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM Platform | Wazuh |
| Wazuh Manager | Kali Linux |
| Endpoint | Windows 10 |
| Monitoring Module | Syscheck (File Integrity Monitoring) |
| Test Directory | C:\FIM |
| Test File | Important-Data.txt |

---

# Attack Scenario

An attacker gains access to a Windows endpoint and performs unauthorized file operations inside a monitored directory.

The attacker performs the following actions:

1. Creates a new file.
2. Modifies the contents of the file.
3. Deletes the file to remove evidence.

The SOC Analyst must identify each activity using Wazuh File Integrity Monitoring alerts.

---

# Prerequisites

- Wazuh Manager installed
- Windows Agent connected
- Sysmon configured
- Windows endpoint sending logs
- Syscheck enabled
- Real-time monitoring enabled for C:\FIM

---

# Configuration

A dedicated monitoring directory was added inside the Windows Agent configuration.

```xml
<directories realtime="yes">C:\FIM</directories>
```

Configuration File:

```
C:\Program Files (x86)\ossec-agent\ossec.conf
```

After updating the configuration, the Wazuh Agent service was restarted.

---

# Attack Simulation

## Step 1 — Create Monitoring Folder

Created the following directory on the Windows endpoint.

```
C:\FIM
```

Screenshot

```
LAB-05-01-FIM-Folder-Created.png
```

---

## Step 2 — Configure File Integrity Monitoring

Updated Windows Agent configuration.

Added:

```xml
<directories realtime="yes">C:\FIM</directories>
```

Restarted Wazuh Agent successfully.

Screenshot

```
LAB-05-02-ossec.conf-FIM-Configuration.png
```

```
LAB-05-03-Wazuh-Agent-Restart.png
```

---

## Step 3 — File Creation

Created:

```
C:\FIM\Important-Data.txt
```

Content:

```
This is the original file.
```

Screenshot

```
LAB-05-04-Test-File-Created.png
```

---

## Detection Result

Wazuh detected:

- File added to the system

Rule Information

| Field | Value |
|--------|------|
| Rule ID | 554 |
| Rule Level | 5 |
| Category | Syscheck |
| Description | File added to the system |

Screenshots

```
LAB-05-05-Wazuh-FIM-Alert.png
```

```
LAB-05-06-Wazuh-FIM-Alert-Details.png
```

---

## Step 4 — File Modification

Modified:

```
C:\FIM\Important-Data.txt
```

Added:

```
Unauthorized modification detected.
```

Screenshot

```
LAB-05-07-File-Modified.png
```

---

## Detection Result

Wazuh generated a checksum change alert.

Alert Information

| Field | Value |
|--------|------|
| Rule ID | 550 |
| Rule Level | 7 |
| Description | Integrity checksum changed |

Screenshots

```
LAB-05-08-Wazuh-FIM-Modified-Alert.png
```

```
LAB-05-09-Wazuh-FIM-Modified-Details.png
```

---

## Step 5 — File Deletion

Deleted:

```
C:\FIM\Important-Data.txt
```

Screenshot

```
LAB-05-10-File-Deleted.png
```

---

## Detection Result

Wazuh successfully detected the deletion of the monitored file.

Screenshots

```
LAB-05-11-Wazuh-FIM-Deleted-Alert.png
```

```
LAB-05-12-Wazuh-FIM-Deleted-Details.png
```

---

# Detection Workflow

```
Attacker

↓

Creates File

↓

Modifies File

↓

Deletes File

↓

Windows Agent

↓

Syscheck (FIM)

↓

Wazuh Manager

↓

Security Alert Generated

↓

SOC Analyst Investigation
```

---

# Wazuh Analysis

During this lab, Wazuh File Integrity Monitoring successfully detected:

- New file creation
- File integrity checksum modification
- File deletion

The generated alerts provided sufficient information for investigation, including:

- Agent Name
- Rule ID
- Rule Level
- File Path
- Timestamp
- Event Description

These events demonstrate how Wazuh can monitor unauthorized file system activity on monitored endpoints.

---

# Skills Demonstrated

- File Integrity Monitoring
- Windows Endpoint Monitoring
- Wazuh Syscheck Configuration
- Security Event Investigation
- Alert Validation
- File Change Detection
- Blue Team Monitoring
- SOC Incident Investigation

---

# Learning Outcome

After completing this lab, the following concepts were demonstrated:

- Configuring File Integrity Monitoring
- Monitoring sensitive directories
- Detecting file creation events
- Detecting unauthorized file modifications
- Detecting file deletion events
- Investigating Wazuh alerts
- Understanding file integrity monitoring workflows used by Security Operations Centers

---

# Result

The File Integrity Monitoring lab was successfully completed.

Wazuh detected all simulated file system activities, including file creation, modification, and deletion, validating the effectiveness of Syscheck for endpoint integrity monitoring.
