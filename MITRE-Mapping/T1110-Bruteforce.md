# MITRE ATT&CK Mapping – Brute Force (T1110)

## Overview

This document maps the brute force authentication simulation performed in LAB-01 to the MITRE ATT&CK framework. The objective is to demonstrate how repeated failed authentication attempts can be detected, investigated, and associated with a known adversary technique.

---

# Technique Information

| Field | Value |
|-------|-------|
| Technique ID | T1110 |
| Technique Name | Brute Force |
| Tactic | Credential Access |
| Data Source | Windows Security Event Logs |
| Detection Platform | Wazuh SIEM |
| Endpoint | Windows 10 |

---

# Technique Description

Brute Force (T1110) is a Credential Access technique in which an attacker repeatedly attempts different passwords or authentication credentials until valid credentials are discovered.

Attackers commonly target local Windows accounts, Remote Desktop Protocol (RDP), SSH, VPN gateways, web applications, and other authentication services.

Repeated authentication failures often generate Windows Security Events that can be monitored by SIEM platforms such as Wazuh.

---

# Detection Strategy

The detection strategy for this lab is based on monitoring Windows Security Event Logs collected by the Wazuh Agent.

The overall detection workflow is:

1. Multiple failed authentication attempts are generated.
2. Windows records Security Events.
3. Wazuh Agent collects the logs.
4. Logs are forwarded to the Wazuh Manager.
5. Detection rules identify suspicious authentication activity.
6. Wazuh generates security alerts for investigation.

---

# Evidence Collected

The following evidence will be collected during the practical lab:

- Windows Security Events
- Failed authentication logs
- Wazuh security alerts
- Alert details
- Event timestamps
- Source IP address
- Target username
- Rule ID
- Alert level

> **This section will be updated after completing the attack simulation.**

---

# Detection Logic

The detection relies on:

- Monitoring repeated failed authentication events
- Identifying abnormal authentication behavior
- Correlating multiple failed login attempts
- Generating alerts for suspicious authentication activity

---

# Wazuh Detection

The following information will be documented after the practical lab:

| Item | Value |
|------|-------|
| Rule ID | To be updated |
| Alert Level | To be updated |
| Rule Description | To be updated |
| Event ID | To be updated |
| Agent Name | To be updated |

---

# Indicators of Compromise (IoCs)

The investigation will identify:

- Source IP Address
- Target Username
- Windows Event ID(s)
- Failed Login Attempts
- Wazuh Rule ID
- Alert Severity
- Authentication Failure Pattern

---

# ATT&CK Mapping Summary

| ATT&CK Tactic | ATT&CK Technique |
|--------------|------------------|
| Credential Access | T1110 – Brute Force |

---

# Defensive Recommendations

The following security controls help reduce the risk of brute force attacks:

- Enforce strong password policies.
- Configure account lockout policies.
- Enable multi-factor authentication (MFA) where possible.
- Monitor failed authentication attempts.
- Generate alerts for repeated login failures.
- Regularly review authentication logs.
- Continuously validate detection rules through controlled security testing.

---

# SOC Analyst Notes

During an investigation, the SOC analyst should verify:

- Number of failed login attempts
- Source IP address
- Target account
- Event timestamps
- Wazuh alert details
- Correlation with other authentication events
- Whether the activity represents a legitimate user mistake or a malicious attack

---

# Conclusion

The brute force simulation demonstrates how Wazuh can detect repeated failed authentication attempts using Windows Security Event Logs. Mapping this activity to MITRE ATT&CK Technique T1110 helps standardize detection, investigation, and reporting while improving threat visibility within the SOC environment.
