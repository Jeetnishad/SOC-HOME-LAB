# LAB-02 – PowerShell Detection

## Objective

The objective of this lab is to validate PowerShell execution monitoring using Sysmon and Wazuh. The lab demonstrates how PowerShell activity is captured on a Windows 10 endpoint, forwarded to the Wazuh Manager, and analyzed through the Wazuh Dashboard. The activity is then mapped to the MITRE ATT&CK framework for proper documentation and incident analysis.

---

# Lab Environment

| Component | Details |
|----------|----------|
| SIEM | Wazuh 4.14.7 |
| Attacker Machine | Kali Linux |
| Target Machine | Windows 10 |
| Endpoint Monitoring | Sysmon |
| Endpoint Agent | Wazuh Agent |
| Virtualization | VirtualBox |
| Network Mode | NAT |

---

# Lab Topology

```
+-------------+          NAT Network          +----------------+
| Kali Linux  | ---------------------------> | Windows 10 VM  |
|             |                              | Wazuh Agent    |
+-------------+                              | Sysmon         |
                                             +-------+--------+
                                                     |
                                                     |
                                              +------v------+
                                              | Wazuh Server|
                                              +-------------+
```

---

# Detection Goal

Validate that PowerShell execution generates endpoint telemetry which is successfully collected by Sysmon and forwarded to Wazuh for security monitoring and investigation.

---

# Prerequisites

- Wazuh Manager installed and running
- Windows 10 endpoint connected to Wazuh
- Wazuh Agent installed and active
- Sysmon installed and configured
- Wazuh Dashboard accessible
- Windows logs successfully forwarded

---

# Commands Executed

## Command 1

```powershell
Get-Process
```

**Purpose**

Displays all running processes on the Windows system. This command was executed to generate a PowerShell process creation event while keeping the activity completely safe.

---

## Command 2

```powershell
Get-ChildItem C:\Windows
```

**Purpose**

Lists the contents of the Windows directory. This command generates additional PowerShell activity that can be monitored through Sysmon and Wazuh.

---

# Wazuh Detection

After executing the PowerShell commands, endpoint telemetry was successfully collected.

The following observations were made:

- PowerShell execution generated Sysmon Process Creation events.
- Wazuh Agent forwarded the events to the Wazuh Manager.
- Events were searchable through the Wazuh Dashboard.
- PowerShell-related Wazuh rules were successfully verified.

---

# Log Analysis

## Data Source

- Microsoft Sysmon
- Windows Event Logs
- Wazuh Agent
- Wazuh Dashboard

---

## Event Analysis

The executed PowerShell commands generated process creation events which contained valuable forensic information.

The following information was available during analysis:

- Process Name
- Process Path
- Command Line
- Parent Process
- User Account
- Timestamp
- Computer Name

These logs provide analysts with visibility into PowerShell execution occurring on the monitored endpoint.

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | PowerShell | T1059.001 |

PowerShell is commonly abused by attackers for execution, reconnaissance, persistence, and post-exploitation activities. Monitoring PowerShell execution improves endpoint visibility and enables analysts to identify suspicious behavior.

---

# Screenshots

| Screenshot | Description |
|------------|-------------|
| lab02-01-sysmon-process-create.png | Sysmon Process Creation Event |
| lab02-02-sysmon-event-details.png | Event Details |
| lab02-03-powershell-get-process.png | Get-Process Execution |
| lab02-04-powershell-get-childitem.png | Get-ChildItem Execution |
| lab02-05-wazuh-sysmon-events.png | Sysmon Events in Wazuh |
| lab02-06-wazuh-powershell-search.png | PowerShell Search Results |
| lab02-07-wazuh-powershell-rule.png | PowerShell Detection Rule |
| lab02-08-wazuh-powershell-rule-details.png | Rule Details |

---

# Detection Summary

| Validation | Status |
|------------|--------|
| PowerShell Executed | ✅ Completed |
| Sysmon Process Creation Logged | ✅ Completed |
| Wazuh Agent Received Logs | ✅ Completed |
| Wazuh Dashboard Investigation | ✅ Completed |
| MITRE ATT&CK Mapping | ✅ Completed |
| Documentation Completed | ✅ Completed |

---

# Learning Outcome

This lab demonstrates how PowerShell activity can be monitored using Sysmon and Wazuh. The generated process creation events provide visibility into endpoint activity and allow SOC analysts to investigate PowerShell execution using centralized logging. Mapping the activity to MITRE ATT&CK Technique T1059.001 strengthens incident documentation and improves threat analysis skills.

---

# Conclusion

The PowerShell Detection Lab was successfully completed within the SOC Home Lab environment. PowerShell commands executed on the Windows endpoint generated Sysmon Process Creation events which were collected by the Wazuh Agent and made available for investigation in the Wazuh Dashboard.

This lab validates endpoint visibility, log collection, PowerShell monitoring, and MITRE ATT&CK mapping, demonstrating a practical SOC Analyst workflow for detecting and investigating PowerShell activity.

---

# References

- MITRE ATT&CK – T1059.001 (PowerShell)
- Wazuh Documentation
- Microsoft Sysmon Documentation
- Microsoft PowerShell Documentation
