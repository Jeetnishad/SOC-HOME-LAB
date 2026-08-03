# LAB 02 – PowerShell Activity Detection using Wazuh

## Objective

The objective of this lab is to simulate PowerShell activity within an authorized SOC Home Lab environment and validate Wazuh's ability to detect PowerShell execution through Windows event logs and Sysmon telemetry.

The lab demonstrates how PowerShell commands can be monitored, analyzed, and investigated using Wazuh SIEM.

---

# Lab Overview

PowerShell is one of the most widely used administrative tools in Windows environments. It is also frequently abused by attackers to execute malicious commands, download payloads, establish persistence, and perform post-exploitation activities.

In this lab, several PowerShell commands will be executed to generate Windows events. These events will be collected by the Wazuh Agent and analyzed through the Wazuh Dashboard.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM Platform | Wazuh 4.14.7 |
| Operating System | Windows 10 Home |
| Monitoring Agent | Wazuh Agent |
| Endpoint Telemetry | Sysmon |
| Virtualization | Oracle VirtualBox |
| Dashboard | Wazuh Dashboard |

---

# Attack Scenario

PowerShell commands are executed on the monitored Windows endpoint.

Windows records PowerShell execution events.

Sysmon captures process creation activity.

The Wazuh Agent forwards the logs to the Wazuh Manager, where detection rules analyze the events and generate alerts for investigation.

---

# Prerequisites

- Wazuh Manager operational
- Windows Agent connected
- Sysmon installed
- PowerShell available
- Windows Security logs forwarded to Wazuh

---

# Detection Workflow

1. Execute PowerShell commands.
2. Windows generates PowerShell-related events.
3. Sysmon records process creation.
4. Wazuh Agent collects the logs.
5. Wazuh analyzes the events.
6. Alerts are generated.
7. SOC analyst investigates the activity.

---

# Attack Simulation

This section will be updated after completing the practical lab.

---

# Evidence Collected

The following evidence will be collected:

- PowerShell execution
- Wazuh alerts
- Rule details
- Sysmon logs
- Event logs
- Investigation screenshots

---

# Wazuh Alert Analysis

This section will include:

- Rule ID
- Rule Level
- Rule Description
- Event ID
- Detection Status

> This section will be updated after the practical exercise.

---

# Log Analysis

PowerShell execution events generated during the lab will be analyzed to identify:

- Executed command
- Parent process
- Process ID
- User account
- Event source
- Detection timeline

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Execution | T1059.001 – PowerShell |

Detailed mapping is available in:

MITRE-Mapping/T1059.001-PowerShell.md

---

# Skills Demonstrated

- PowerShell Monitoring
- Wazuh Investigation
- Sysmon Log Analysis
- Process Investigation
- MITRE ATT&CK Mapping
- SOC Investigation

---

# Conclusion

This lab validates Wazuh's capability to monitor PowerShell activity using Windows event logs and Sysmon telemetry, enabling SOC analysts to investigate potentially malicious PowerShell execution.
