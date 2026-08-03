# SOC Home Lab – Project Summary

## Project Overview

This SOC Home Lab project was developed to simulate real-world Security Operations Center (SOC) operations using Wazuh SIEM, Windows 10, Kali Linux, Sysmon, and Oracle VirtualBox. The project focuses on gaining practical experience in security monitoring, attack detection, log analysis, incident investigation, and MITRE ATT&CK mapping within an isolated and authorized lab environment.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM Platform | Wazuh 4.14.7 |
| Attacker Machine | Kali Linux |
| Victim Machine | Windows 10 |
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

- Generated multiple failed login attempts.
- Windows Security Event ID **4625** was recorded.
- Wazuh successfully detected failed authentication attempts.
- Authentication events were analyzed through the Wazuh Dashboard.
- Security logs were investigated and documented.

### MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Credential Access | T1110 – Brute Force |

### Skills Demonstrated

- Windows Security Log Analysis
- Authentication Monitoring
- Wazuh Alert Investigation
- Event Correlation
- Incident Investigation
- MITRE ATT&CK Mapping

### Learning Outcome

This lab demonstrated how repeated authentication failures can be monitored and investigated using Windows Security Logs and Wazuh, providing practical experience with credential attack detection and SOC investigation workflows.

---

## LAB 02 – PowerShell Detection

**Status:** ✅ Completed

### Objective

Validate PowerShell execution monitoring using Sysmon and Wazuh by generating PowerShell activity on a Windows endpoint and analyzing the resulting events.

### Detection Results

- Executed PowerShell commands on the Windows endpoint.
- Sysmon generated Process Creation (Event ID 1).
- Wazuh successfully collected and displayed PowerShell activity.
- PowerShell-related events were investigated through the Wazuh Dashboard.
- Endpoint telemetry was documented for analysis.

### MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Execution | T1059.001 – PowerShell |

### Skills Demonstrated

- PowerShell Monitoring
- Sysmon Process Analysis
- Wazuh Log Investigation
- Endpoint Visibility
- Event Analysis
- MITRE ATT&CK Mapping

### Learning Outcome

This lab demonstrated how PowerShell execution generates endpoint telemetry that can be monitored through Sysmon and analyzed in Wazuh, reinforcing practical SOC monitoring and investigation skills.

---

## LAB 03 – Nmap Reconnaissance Detection

**Status:** ✅ Completed

### Objective

Simulate a network reconnaissance attack using Nmap from Kali Linux against a Windows 10 endpoint and analyze the generated telemetry using Sysmon and Wazuh.

### Detection Results

- Verified communication between Kali Linux and Windows 10.
- Successfully executed Basic and Advanced Nmap scans.
- Sysmon generated Network Connection (Event ID 3).
- Wazuh successfully collected Windows endpoint telemetry.
- Reconnaissance activity was analyzed using Wazuh and Sysmon logs.

### MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Discovery | T1046 – Network Service Discovery |

### Skills Demonstrated

- Network Reconnaissance
- Nmap Scanning
- Sysmon Network Monitoring
- Wazuh Log Analysis
- Network Event Investigation
- MITRE ATT&CK Mapping

### Learning Outcome

This lab demonstrated how reconnaissance activities generate endpoint network telemetry that can be collected by Sysmon and investigated through Wazuh. It also highlighted the importance of monitoring reconnaissance techniques during the early stages of the cyber attack lifecycle.

---

# Upcoming Labs

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
| LAB 02 | ✅ Completed |
| LAB 03 | ✅ Completed |
| Remaining Detection Labs | ⏳ In Progress |

---

# Overall Project Progress

The SOC Home Lab has successfully established a functional monitoring environment using Wazuh, Sysmon, Windows 10, and Kali Linux. The completed labs demonstrate practical experience in authentication monitoring, PowerShell execution analysis, and network reconnaissance detection. Each exercise follows a structured SOC workflow that includes attack simulation, log collection, event analysis, MITRE ATT&CK mapping, and incident documentation. The remaining labs will further expand the project by covering reverse shells, file integrity monitoring, persistence techniques, threat hunting, malware simulation, and USB device monitoring, creating a comprehensive SOC Analyst portfolio.
