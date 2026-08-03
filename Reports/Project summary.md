# SOC Home Lab – Project Summary

## Project Overview

This SOC Home Lab project was built to simulate real-world Security Operations Center (SOC) activities using Wazuh SIEM, Windows 10, Kali Linux, Sysmon, and VirtualBox.

The primary objective of this project is to gain hands-on experience in security monitoring, attack detection, log analysis, incident investigation, and MITRE ATT&CK mapping within an isolated and authorized lab environment.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM Platform | Wazuh 4.14.7 |
| Attacker Machine | Kali Linux |
| Victim Machine | Windows 10 Home |
| Endpoint Monitoring | Wazuh Agent |
| Endpoint Telemetry | Sysmon |
| Virtualization | Oracle VirtualBox |
| Network Configuration | NAT Network |

---

# Completed Labs

## LAB 01 – Windows Brute Force Detection

**Status:** ✅ Completed

### Objective

Simulate multiple failed Windows authentication attempts and validate Wazuh's ability to detect authentication failures using Windows Security Event Logs.

### Detection Results

- Successfully generated multiple failed login attempts.
- Windows Security Event ID **4625** was recorded.
- Wazuh successfully detected the authentication failures.
- Rule ID **60122** triggered successfully.
- Rule Level **5** alert generated.
- Authentication events were successfully investigated.

### MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Credential Access | T1110 – Brute Force |

### Skills Demonstrated

- Windows Security Log Analysis
- Wazuh Alert Investigation
- Authentication Monitoring
- Event Correlation
- MITRE ATT&CK Mapping
- Incident Investigation

---

# Upcoming Labs

- ⏳ LAB 02 – PowerShell Detection
- ⏳ LAB 03 – Nmap Detection
- ⏳ LAB 04 – Reverse Shell Detection
- ⏳ LAB 05 – File Integrity Monitoring
- ⏳ LAB 06 – Suspicious Process Detection
- ⏳ LAB 07 – Persistence Detection
- ⏳ LAB 08 – Threat Hunting
- ⏳ LAB 09 – EICAR Test
- ⏳ LAB 10 – USB Monitoring

---

# Current Project Status

| Category | Status |
|----------|--------|
| Environment Setup | ✅ Completed |
| Wazuh Installation | ✅ Completed |
| Windows Agent Configuration | ✅ Completed |
| Sysmon Configuration | ✅ Completed |
| LAB 01 | ✅ Completed |
| Remaining Detection Labs | ⏳ In Progress |

---

# Conclusion

The first detection lab successfully demonstrated Wazuh's capability to monitor Windows authentication events, detect failed login attempts, and provide actionable security alerts for investigation. Future labs will expand the SOC Home Lab by covering PowerShell monitoring, network reconnaissance detection, reverse shell activity, file integrity monitoring, persistence techniques, threat hunting, malware simulation, and USB device monitoring.


# LAB-02 – PowerShell Detection

## Status

**Completed**

---

## Objective

The objective of this lab was to validate PowerShell execution monitoring using Sysmon and Wazuh. The exercise focused on generating PowerShell activity on a Windows 10 endpoint, verifying log collection, and investigating the resulting events through the Wazuh Dashboard.

---

## Environment

| Component | Details |
|----------|----------|
| SIEM | Wazuh 4.14.7 |
| Endpoint | Windows 10 |
| Attacker Machine | Kali Linux |
| Endpoint Monitoring | Sysmon |
| Agent | Wazuh Agent |
| Virtualization | VirtualBox |

---

## Activity Performed

The following PowerShell commands were executed on the Windows endpoint:

```powershell
Get-Process
```

```powershell
Get-ChildItem C:\Windows
```

These commands generated PowerShell process creation events that were captured by Sysmon and collected by Wazuh for analysis.

---

## Detection Workflow

PowerShell Execution

↓

Sysmon Process Creation Event (Event ID 1)

↓

Wazuh Agent

↓

Wazuh Manager

↓

Wazuh Dashboard

↓

SOC Investigation

---

## Evidence Collected

- Sysmon Process Creation Events
- Windows Event Logs
- Wazuh Dashboard Events
- PowerShell command execution
- Wazuh PowerShell-related rules
- Event Viewer screenshots
- Wazuh Dashboard screenshots

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | PowerShell | T1059.001 |

---

## Skills Demonstrated

- Windows Event Log Analysis
- Sysmon Monitoring
- Wazuh Log Analysis
- Endpoint Visibility
- PowerShell Monitoring
- MITRE ATT&CK Mapping
- Incident Investigation
- SOC Alert Analysis

---

## Learning Outcome

This lab provided practical experience in monitoring PowerShell activity using Sysmon and Wazuh. It demonstrated how endpoint telemetry can be collected, investigated, and documented following a standard SOC workflow. The activity was successfully mapped to MITRE ATT&CK Technique T1059.001, reinforcing knowledge of execution-related detections.

---

## Screenshots

- lab02-01-sysmon-process-create.png
- lab02-02-sysmon-event-details.png
- lab02-03-powershell-get-process.png
- lab02-04-powershell-get-childitem.png
- lab02-05-wazuh-sysmon-events.png
- lab02-06-wazuh-powershell-search.png
- lab02-07-wazuh-powershell-rule.png
- lab02-08-wazuh-powershell-rule-details.png

---

## Result

The PowerShell Detection Lab was successfully completed. PowerShell execution generated endpoint telemetry that was captured by Sysmon and forwarded to Wazuh for centralized monitoring and investigation. This lab demonstrates practical SOC Analyst skills in endpoint monitoring, event analysis, and MITRE ATT&CK mapping within an isolated home lab environment.
