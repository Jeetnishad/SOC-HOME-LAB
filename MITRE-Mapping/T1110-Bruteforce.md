# MITRE ATT&CK Mapping – T1110: Brute Force

## Overview

This document maps the authentication failure activity generated during LAB-01 to the MITRE ATT&CK framework.

The objective of this lab was to validate Wazuh's ability to detect repeated failed Windows authentication attempts and correlate the observed activity with the appropriate ATT&CK technique.

---

# ATT&CK Technique Information

| Field | Value |
|-------|-------|
| Technique ID | T1110 |
| Technique Name | Brute Force |
| ATT&CK Tactic | Credential Access |
| Data Source | Windows Security Event Logs |
| Detection Platform | Wazuh SIEM 4.14.7 |
| Endpoint | Windows 10 Home |

---

# Technique Description

Brute Force (T1110) is a Credential Access technique in which an attacker repeatedly attempts to authenticate using invalid credentials until a valid password is discovered.

Repeated authentication failures generate Windows Security Event ID 4625, allowing security monitoring platforms such as Wazuh to detect suspicious authentication activity.

Although this lab used Windows local authentication instead of Remote Desktop Protocol (RDP), the resulting security events represent the same authentication failure behavior required to detect brute force activity.

---

# Attack Simulation

The Windows workstation was locked using the Windows + L shortcut.

Five consecutive failed authentication attempts were performed using an intentionally incorrect password.

Each failed authentication generated Windows Security Event ID 4625, which was collected by the Wazuh Agent and forwarded to the Wazuh Manager for analysis.

---

# Detection Workflow

1. Multiple failed login attempts were generated.
2. Windows Security Log recorded Event ID 4625.
3. Wazuh Agent collected the events.
4. Events were forwarded to the Wazuh Manager.
5. Wazuh evaluated Windows Security detection rules.
6. Rule ID 60122 generated authentication failure alerts.
7. The alerts were investigated using the Wazuh Dashboard.

---

# Wazuh Detection Details

| Field | Value |
|--------|-------|
| Rule ID | 60122 |
| Rule Description | Logon Failure – Unknown user or bad password |
| Rule Level | 5 |
| Windows Event ID | 4625 |
| Detection Result | Successful |

---

# Evidence Collected

The following evidence was collected during the investigation:

- Windows Security Event ID 4625
- Wazuh authentication failure alerts
- Rule ID 60122
- Rule details
- Failed authentication timeline
- Alert investigation screenshots

---

# Indicators of Compromise (IoCs)

The investigation identified the following indicators:

- Repeated failed authentication attempts
- Windows Security Event ID 4625
- Invalid password attempts
- Wazuh Rule ID 60122
- Authentication failure alerts

---

# Detection Logic

The detection is based on monitoring Windows Security authentication events.

When repeated failed login attempts occur, Windows generates Event ID 4625.

The Wazuh Agent forwards these events to the Wazuh Manager, where Windows Security detection rules identify authentication failures and generate alerts for investigation.

---

# Defensive Recommendations

To reduce the risk of brute force attacks, organizations should:

- Enforce strong password policies.
- Configure account lockout policies.
- Enable Multi-Factor Authentication (MFA) where applicable.
- Continuously monitor authentication failures.
- Investigate repeated failed login attempts.
- Validate SIEM detection rules through controlled testing.

---

# SOC Analyst Investigation Checklist

During authentication failure investigations, analysts should verify:

- Source of the authentication attempt
- Target account
- Number of failed login attempts
- Windows Event ID
- Wazuh Rule ID
- Alert severity
- Related authentication activity
- Evidence of successful compromise

---

# Conclusion

The authentication failure simulation successfully validated Wazuh's capability to detect Windows Security Event ID 4625 and generate authentication failure alerts.

The observed activity was correctly mapped to MITRE ATT&CK Technique T1110 (Brute Force), demonstrating how security monitoring solutions can detect and investigate authentication-based attacks within an authorized SOC Home Lab environment.
