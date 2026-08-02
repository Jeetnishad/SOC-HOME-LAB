# LAB 01 – Windows Brute Force Detection using Wazuh

## Objective

The objective of this lab is to simulate a Windows brute force authentication attack in a controlled home lab environment and validate Wazuh's ability to detect multiple failed login attempts. This lab demonstrates how security monitoring solutions can identify authentication-based attacks, generate alerts, and provide valuable forensic evidence for incident investigation.

---

# Lab Overview

Brute force attacks are one of the most common techniques used by attackers to gain unauthorized access to systems by repeatedly attempting different passwords against a valid user account.

In this lab, multiple failed Windows login attempts will be generated from the Kali Linux attacker machine against the Windows 10 victim machine. The generated authentication events will be collected by the Wazuh Agent, forwarded to the Wazuh Manager, and analyzed through the Wazuh Dashboard.

The collected logs will later be investigated to understand how Wazuh detects authentication attacks and how these events map to the MITRE ATT&CK framework.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| SIEM Platform | Wazuh 4.14.7 |
| Attacker Machine | Kali Linux |
| Victim Machine | Windows 10 |
| Virtualization | Oracle VirtualBox |
| Network Mode | NAT |
| Endpoint Monitoring | Wazuh Agent |
| System Monitoring | Sysmon |

---

# Attack Scenario

An attacker attempts to gain unauthorized access to a Windows system by repeatedly submitting invalid credentials.

The repeated authentication failures generate Windows Security Events, which are collected by the Wazuh Agent and forwarded to the Wazuh Manager for analysis.

The generated alerts allow a SOC analyst to identify suspicious authentication activity and begin an incident investigation.

---

# Prerequisites

Before performing this lab, the following requirements must be completed:

- Kali Linux installed
- Windows 10 installed
- Wazuh Server operational
- Wazuh Dashboard accessible
- Windows Agent connected
- Sysmon installed and configured
- Windows Security logs successfully forwarded to Wazuh

---

# Detection Workflow

1. Attacker performs multiple failed authentication attempts.
2. Windows generates Security Event Logs.
3. Wazuh Agent collects the logs.
4. Logs are forwarded to the Wazuh Manager.
5. Wazuh applies detection rules.
6. Security alerts are generated.
7. SOC analyst investigates the alerts.

---

# Commands Executed

The commands used during this lab will be documented after the practical exercise.

> **To be updated after completing the attack simulation.**

---

# Evidence Collected

The following evidence will be collected during the practical lab:

- Failed login attempts
- Windows Security Event Logs
- Wazuh Alert
- Alert Details
- Event Log Analysis
- Dashboard Screenshots

---

# Wazuh Alert Analysis

This section will include:

- Rule ID
- Alert Level
- Rule Description
- Timestamp
- Agent Name
- Source IP Address
- Event Details

> **To be updated after alert generation.**

---

# Log Analysis

This section will contain the analysis of Windows Security Event Logs related to the brute force activity.

The investigation will focus on identifying:

- Authentication failures
- Username targeted
- Source IP address
- Event IDs
- Log source
- Detection timeline

> **To be updated after log collection.**

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1110 | Brute Force |

A detailed MITRE mapping is documented separately under:

```

MITRE-Mapping/T1110-Bruteforce.md

```

---

# Expected Outcome

At the end of this lab, Wazuh should successfully detect repeated failed authentication attempts and generate security alerts that can be investigated by a SOC analyst.

---

# Skills Demonstrated

- Windows Log Analysis
- Wazuh Alert Investigation
- Authentication Monitoring
- Security Event Analysis
- MITRE ATT&CK Mapping
- SOC Incident Investigation

---

# Conclusion

This lab demonstrates how Wazuh can detect brute force authentication attempts against Windows systems by monitoring Security Event Logs and generating actionable alerts. The collected evidence provides SOC analysts with the information required to investigate unauthorized authentication attempts and respond appropriately.

The incident report and MITRE ATT&CK mapping for this activity are documented separately within this repository.
