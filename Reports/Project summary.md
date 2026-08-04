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



## LAB 04 – Reverse Shell Detection

**Status:** ✅ Completed

### Objective

Simulate a reverse shell attack using Netcat (Ncat) from a Windows 10 endpoint to a Kali Linux attacker machine and investigate the generated endpoint telemetry using Sysmon and Wazuh SIEM.

### Detection Results

- Verified communication between the Windows endpoint and Kali Linux attacker.
- Successfully started a Netcat listener on Kali Linux.
- Established a reverse shell from Windows to Kali Linux.
- Executed remote commands (`whoami`, `hostname`, and `ipconfig`) through the reverse shell.
- Sysmon generated Process Creation (Event ID 1) telemetry.
- Wazuh successfully collected endpoint logs and generated alerts for abnormal command prompt execution.
- Reverse shell activity was investigated using the Wazuh Threat Hunting module.

### MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Execution | T1059.003 – Windows Command Shell |
| Command and Control | T1105 – Ingress Tool Transfer |

### Skills Demonstrated

- Reverse Shell Simulation
- Netcat (Ncat)
- Windows Process Monitoring
- Sysmon Event Analysis
- Wazuh Threat Hunting
- Alert Investigation
- Endpoint Detection
- MITRE ATT&CK Mapping
- SOC Incident Investigation

### Learning Outcome

This lab demonstrated how reverse shell activity generates endpoint telemetry that can be captured by Sysmon and investigated through Wazuh SIEM. The exercise provided hands-on experience in detecting suspicious process execution, analyzing security events, and mapping attacker behavior to the MITRE ATT&CK framework. It also strengthened practical SOC Analyst skills in incident investigation, endpoint visibility, and threat detection within a controlled home lab environment.

The SOC Home Lab has successfully established a functional monitoring environment using Wazuh, Sysmon, Windows 10, and Kali Linux. The completed labs demonstrate practical experience in authentication monitoring, PowerShell execution analysis, and network reconnaissance detection. Each exercise follows a structured SOC workflow that includes attack simulation, log collection, event analysis, MITRE ATT&CK mapping, and incident documentation. The remaining labs will further expand the project by covering reverse shells, file integrity monitoring, persistence techniques, threat hunting, malware simulation, and USB device monitoring, creating a comprehensive SOC Analyst portfolio.

# Project Summary

## LAB 05 – File Integrity Monitoring (FIM)

### Objective

The objective of this lab was to configure and validate Wazuh File Integrity Monitoring (FIM) on a Windows endpoint. The lab focused on detecting file creation, file modification, and file deletion events within a monitored directory to simulate real-world endpoint monitoring performed by Security Operations Center (SOC) analysts.

---

## Environment

| Component | Details |
|-----------|---------|
| SIEM Platform | Wazuh |
| Wazuh Manager | Kali Linux |
| Endpoint | Windows 10 |
| Monitoring Module | Syscheck (File Integrity Monitoring) |
| Test Directory | C:\FIM |

---

## Activities Performed

- Created a dedicated monitoring directory (`C:\FIM`).
- Configured Wazuh Agent for real-time File Integrity Monitoring.
- Restarted the Wazuh Agent to apply the configuration.
- Created a test file (`Important-Data.txt`).
- Modified the file to simulate unauthorized changes.
- Deleted the monitored file.
- Verified all alerts in the Wazuh Dashboard.

---

## Detection Results

| Activity | Detection Status |
|----------|------------------|
| File Creation | ✅ Detected |
| File Modification | ✅ Detected |
| File Deletion | ✅ Detected |

---

## Wazuh Alerts Observed

| Rule ID | Description | Level |
|---------|-------------|------:|
| 554 | File added to the system | 5 |
| 550 | Integrity checksum changed | 7 |
| File Deletion | File removed from monitored directory | Generated |

---

## Skills Demonstrated

- File Integrity Monitoring (FIM)
- Wazuh Syscheck Configuration
- Windows Endpoint Monitoring
- Security Event Analysis
- Alert Investigation
- Blue Team Detection
- SOC Incident Documentation
- MITRE ATT&CK Mapping

---

## Learning Outcome

This lab demonstrated how Wazuh File Integrity Monitoring detects unauthorized file system activity in real time. By monitoring a dedicated directory, the platform successfully identified file creation, modification, and deletion events, providing the visibility required for effective incident detection and investigation.

