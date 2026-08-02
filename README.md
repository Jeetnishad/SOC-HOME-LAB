# 🛡️ SOC Home Lab using Wazuh SIEM, Sysmon & Kali Linux

> A complete SOC (Security Operations Center) Home Lab built using Wazuh SIEM, Sysmon, Kali Linux, and Windows 10 to simulate attacks, monitor security events, perform threat hunting, and investigate incidents.

---

## 📌 Project Overview

This project demonstrates the implementation of a Security Operations Center (SOC) Home Lab using Wazuh SIEM. The lab is designed to collect Windows endpoint logs, detect suspicious activities, and analyze security events in a controlled virtual environment.

The project focuses on real-world SOC analyst tasks such as endpoint monitoring, log analysis, threat hunting, attack detection, and incident investigation.

---

## 🎯 Objectives

- Build a complete SOC Home Lab
- Deploy Wazuh SIEM
- Configure Windows Endpoint Monitoring
- Install and configure Sysmon
- Collect Windows Event Logs
- Perform Threat Hunting
- Detect suspicious activities
- Analyze security alerts
- Investigate incidents
- Map detections to MITRE ATT&CK

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Kali Linux |
| Victim Machine | Windows 10 |
| SIEM Platform | Wazuh 4.14.7 |
| Endpoint Monitoring | Sysmon |
| Virtualization | Oracle VirtualBox |

---

# 🏗️ Lab Architecture

```
                    +------------------------------+
                    |          Kali Linux          |
                    |------------------------------|
                    | Wazuh Manager                |
                    | Wazuh Dashboard              |
                    | Wazuh Indexer                |
                    | Nmap                         |
                    | Metasploit                   |
                    +--------------+---------------+
                                   |
                          Virtual Network
                                   |
                    +--------------+---------------+
                    |         Windows 10           |
                    |------------------------------|
                    | Wazuh Agent                  |
                    | Sysmon                       |
                    | Windows Event Logs           |
                    +------------------------------+
```

---

# 🛠️ Technologies Used

- Wazuh SIEM
- Sysmon
- Kali Linux
- Windows 10
- Oracle VirtualBox
- PowerShell
- Windows Event Logs
- MITRE ATT&CK Framework

---

# 📂 Repository Structure

```
SOC-Home-Lab/
│
├── Architecture
├── Installation
├── Configurations
├── Detection-Labs
├── Incident-Reports
├── MITRE-Mapping
├── Reports
├── Screenshots
├── Scripts
├── Images
│
├── README.md
├── LICENSE
└── .gitignore
```

---

# ✅ Completed

- Kali Linux Installation
- Windows 10 Virtual Machine Setup
- Virtual Network Configuration
- Wazuh Manager Installation
- Wazuh Dashboard Configuration
- Wazuh Indexer Configuration
- Windows Agent Registration
- Sysmon Installation
- Sysmon Configuration
- Endpoint Monitoring
- Log Collection Verification

---

# 🚧 Detection Labs (Coming Soon)

- Baseline Monitoring
- Nmap Scan Detection
- PowerShell Detection
- Brute Force Detection
- File Integrity Monitoring
- Persistence Detection
- Threat Hunting
- Incident Investigation

---

# 🧠 Skills Demonstrated

- Security Information and Event Management (SIEM)
- Endpoint Monitoring
- Windows Event Analysis
- Threat Hunting
- Log Analysis
- Incident Response
- SOC Operations
- MITRE ATT&CK Mapping
- Security Monitoring

---

# 📸 Screenshots

Project screenshots will be added after completing each detection lab.

---

# 🚀 Future Improvements

- Suricata Integration
- Sigma Rules
- YARA Rules
- VirusTotal Integration
- MISP Integration
- Active Response Automation

---

# 👨‍💻 Author

**Jeet Nishad**

Cybersecurity Enthusiast | SOC Analyst | Blue Team Learner

---

⭐ If you found this project useful, consider giving it a star.
