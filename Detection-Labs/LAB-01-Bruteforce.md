# LAB 01 – Windows Brute Force Detection using Wazuh

## Objective

The objective of this lab is to simulate multiple failed Windows authentication attempts in an authorized SOC Home Lab environment and verify Wazuh's ability to detect authentication failures through Windows Security Event Logs.

The lab demonstrates how a Security Information and Event Management (SIEM) platform detects failed logon attempts, generates alerts, and provides security analysts with the information required to investigate authentication-related incidents.

---

# Lab Overview

Brute force attacks are one of the most common techniques used by attackers to gain unauthorized access to Windows systems by repeatedly attempting invalid credentials.

Since the target system in this lab is running Windows 10 Home Edition, Remote Desktop (RDP) based brute force simulation was not applicable because Windows Home does not provide an RDP server.

Instead, multiple failed Windows logon attempts were intentionally generated from the Windows lock screen to create Windows Security Event ID 4625 events. These events were collected by the Wazuh Agent, forwarded to the Wazuh Manager, and successfully detected by Wazuh.

---

# Lab Environment

| Component | Details |
|----------|---------|
| SIEM Platform | Wazuh 4.14.7 |
| Attacker System | Windows Local Authentication Simulation |
| Monitored Endpoint | Windows 10 Home |
| Log Collection | Wazuh Agent |
| Endpoint Monitoring | Sysmon |
| Virtualization | Oracle VirtualBox |
| Operating System | Kali Linux & Windows 10 Home |

---

# Attack Scenario

An attacker repeatedly attempts to authenticate using invalid credentials.

Every failed authentication generates Windows Security Event ID 4625.

The Wazuh Agent forwards these events to the Wazuh Manager, where predefined Windows Security detection rules identify suspicious authentication failures and generate alerts for investigation.

---

# Prerequisites

The following components were configured before performing the lab:

- Kali Linux installed
- Windows 10 Home installed
- Wazuh 4.14.7 installed
- Windows Agent connected
- Sysmon installed and configured
- Windows Security Events successfully forwarded to Wazuh
- Wazuh Dashboard operational

---

# Attack Simulation

The Windows workstation was locked using **Windows + L**.

Five consecutive authentication attempts were performed using an intentionally incorrect password.

Each failed authentication generated Windows Security Event ID 4625, which was forwarded to Wazuh for analysis.

---

# Detection Workflow

1. Windows generated failed authentication events.
2. Windows Security Log recorded Event ID 4625.
3. Wazuh Agent collected the events.
4. Events were forwarded to the Wazuh Manager.
5. Windows Security detection rules were evaluated.
6. Wazuh generated authentication failure alerts.
7. The alerts were investigated using the Wazuh Dashboard.

---

# Evidence Collected

The following evidence was collected during the investigation:

- Failed Windows logon attempts
- Windows Security Event ID 4625
- Wazuh authentication failure alerts
- Rule details
- Security event timeline

Screenshots collected:

- Failed Login Screen
- Wazuh Alert List
- Wazuh Rule Details

---

# Wazuh Alert Analysis

| Field | Value |
|--------|-------|
| Rule ID | 60122 |
| Rule Level | 5 |
| Rule Description | Logon Failure – Unknown user or bad password |
| Log Source | Windows Security Events |
| Detection Status | Successful |

The generated alerts confirmed that Wazuh successfully detected repeated failed authentication attempts performed during the simulation.

---

# Log Analysis

Windows Security Event ID **4625** was generated for every failed authentication attempt.

The collected logs confirmed:

- Failed authentication activity
- Invalid password usage
- Successful log forwarding
- Wazuh alert generation
- Proper Windows Security monitoring

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Credential Access | T1110 – Brute Force |

Detailed mapping is available in:

```

MITRE-Mapping/T1110-Bruteforce.md

```

---

# Skills Demonstrated

- Windows Security Log Analysis
- Authentication Monitoring
- Wazuh Alert Investigation
- Windows Event Investigation
- Security Event Correlation
- MITRE ATT&CK Mapping
- SOC Incident Analysis

---

# Conclusion

The brute force authentication simulation successfully demonstrated Wazuh's capability to detect failed Windows authentication attempts using Windows Security Event ID 4625.

Although Remote Desktop brute force simulation was not applicable because the endpoint was running Windows 10 Home Edition, the generated authentication failures produced the same Windows security events required for detection.

The lab validated that Wazuh correctly collected Windows Security Logs, generated authentication alerts, and provided sufficient forensic evidence for SOC investigation and incident reporting.
