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
