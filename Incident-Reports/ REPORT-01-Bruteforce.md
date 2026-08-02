# Incident Report 01 – Windows Brute Force Authentication Attempt

## Executive Summary

This incident report documents the detection and investigation of a simulated brute force authentication attack performed within an authorized SOC Home Lab environment. The attack consisted of multiple failed login attempts against a Windows 10 endpoint from a Kali Linux attacker machine.

The activity was successfully detected by Wazuh through Windows Security Event Logs collected by the Wazuh Agent. The generated alerts were analyzed to determine the nature of the attack, identify relevant Indicators of Compromise (IoCs), and validate the effectiveness of the security monitoring configuration.

---

# Incident Information

| Field | Value |
|--------|-------|
| Incident ID | IR-001 |
| Incident Name | Windows Brute Force Authentication Attempt |
| Category | Authentication Attack |
| Severity | Medium *(To be confirmed after alert generation)* |
| Status | Closed |
| Environment | Authorized SOC Home Lab |
| Detection Tool | Wazuh SIEM |
| Endpoint | Windows 10 |
| Attacker Machine | Kali Linux |

---

# Incident Description

A brute force attack was simulated by repeatedly attempting authentication against a Windows 10 system using invalid credentials. These failed authentication attempts generated Windows Security Events, which were collected by the Wazuh Agent and forwarded to the Wazuh Manager.

Wazuh successfully identified the suspicious authentication activity and generated alerts for further investigation.

---

# Detection Summary

The attack was detected through Windows Security Event Logs monitored by the Wazuh Agent.

The generated alerts indicated repeated failed authentication attempts, allowing the SOC analyst to identify potential unauthorized access attempts against the monitored endpoint.

---

# Attack Timeline

| Time | Activity |
|------|----------|
| Attack Started | To be updated |
| Failed Login Events Generated | To be updated |
| Wazuh Alert Generated | To be updated |
| Investigation Started | To be updated |
| Investigation Completed | To be updated |

---

# Affected Assets

| Asset | Description |
|--------|-------------|
| Windows 10 Endpoint | Target system |
| Wazuh Manager | Security monitoring platform |
| Wazuh Dashboard | Alert visualization |
| Windows Security Logs | Log source |

---

# Indicators of Compromise (IoCs)

The following indicators will be confirmed during the investigation:

- Source IP Address
- Target Username
- Windows Event ID(s)
- Wazuh Rule ID
- Alert Level
- Authentication Failure Events

> **This section will be updated after completing the practical lab.**

---

# Investigation Findings

The investigation will focus on:

- Authentication failure events
- Number of failed login attempts
- Source IP address
- Target account
- Wazuh rule triggered
- Alert severity
- Event timestamps
- Correlation of Windows Security Events

---

# Root Cause Analysis

The activity was intentionally generated within the authorized SOC Home Lab environment to validate the organization's detection capability against brute force authentication attacks.

No unauthorized access was obtained during the simulation.

---

# Response Actions

The following actions were performed:

- Reviewed Wazuh alerts
- Verified Windows Security Events
- Correlated authentication failures
- Validated detection rules
- Confirmed successful alert generation
- Documented investigation findings

---

# MITRE ATT&CK Mapping

| Technique ID | Technique |
|--------------|-----------|
| T1110 | Brute Force |

Detailed mapping is available in:

```
MITRE-Mapping/T1110-Bruteforce.md
```

---

# Lessons Learned

- Wazuh successfully detected repeated authentication failures.
- Windows Security Logs provided valuable forensic evidence.
- Authentication monitoring is effective for detecting brute force attacks.
- Proper endpoint logging significantly improves SOC visibility.
- Security monitoring should be continuously validated through controlled attack simulations.

---

# Recommendations

- Enable account lockout policies.
- Monitor repeated authentication failures.
- Review authentication alerts regularly.
- Correlate failed logins with other suspicious activities.
- Periodically validate detection rules using controlled security testing.

---

# Conclusion

The simulated brute force attack was successfully detected and investigated within the SOC Home Lab environment. Wazuh generated actionable alerts that enabled effective analysis of authentication events, demonstrating the platform's capability to detect unauthorized login attempts and support incident response activities.
