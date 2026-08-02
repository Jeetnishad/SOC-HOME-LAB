# Incident Report 01 – Windows Authentication Failure Detection

## Executive Summary

This incident report documents the detection and investigation of multiple failed Windows authentication attempts generated within an authorized SOC Home Lab environment.

The activity was intentionally performed to validate Wazuh's ability to detect Windows authentication failures using Windows Security Event Logs. Wazuh successfully identified the failed logon attempts, generated security alerts, and provided sufficient forensic evidence for investigation.

No unauthorized access was achieved during this simulation.

---

# Incident Information

| Field | Value |
|--------|-------|
| Incident ID | IR-001 |
| Incident Name | Windows Authentication Failure Detection |
| Category | Authentication Failure |
| Severity | Medium |
| Status | Closed |
| Environment | Authorized SOC Home Lab |
| Detection Tool | Wazuh SIEM 4.14.7 |
| Endpoint | Windows 10 Home |
| Log Source | Windows Security Logs |

---

# Incident Description

Multiple failed authentication attempts were intentionally generated on the Windows endpoint using invalid credentials from the Windows lock screen.

Each failed login generated Windows Security Event ID 4625. These events were collected by the Wazuh Agent and forwarded to the Wazuh Manager.

Wazuh successfully detected the failed authentication attempts and generated alerts indicating repeated logon failures.

---

# Detection Summary

The authentication failures were successfully detected by Wazuh using predefined Windows Security detection rules.

Generated Alert Information:

| Field | Value |
|--------|-------|
| Rule ID | 60122 |
| Rule Description | Logon Failure – Unknown user or bad password |
| Rule Level | 5 |
| Detection Status | Successful |

---

# Timeline of Events

| Time | Activity |
|------|----------|
| User Account Locked | Windows Lock Screen |
| Multiple Failed Login Attempts | Generated |
| Windows Event ID 4625 Created | Yes |
| Wazuh Agent Collected Events | Yes |
| Wazuh Alert Generated | Yes |
| Investigation Completed | Successful |

---

# Affected Assets

| Asset | Description |
|--------|-------------|
| Windows 10 Home | Monitored Endpoint |
| Wazuh Agent | Log Collection |
| Wazuh Manager | Alert Generation |
| Wazuh Dashboard | Alert Investigation |

---

# Indicators of Compromise (IoCs)

The investigation identified the following indicators:

- Windows Security Event ID: **4625**
- Authentication Failure
- Invalid Password Attempts
- Wazuh Rule ID: **60122**
- Rule Level: **5**
- Authentication Failure Alerts

---

# Investigation Findings

The investigation confirmed:

- Multiple failed authentication attempts were generated.
- Windows Security Logs successfully recorded Event ID 4625.
- Wazuh Agent forwarded the logs to the Wazuh Manager.
- Wazuh detection rules successfully generated authentication failure alerts.
- The alerts accurately represented the simulated attack.

---

# Root Cause Analysis

The authentication failures were intentionally generated as part of a controlled SOC Home Lab exercise to validate detection capabilities.

No malicious activity occurred outside the authorized testing environment.

---

# Response Actions

The following actions were performed during the investigation:

- Reviewed generated Wazuh alerts.
- Verified Windows Security Event Logs.
- Confirmed Event ID 4625.
- Validated Rule ID 60122.
- Correlated authentication failures.
- Documented investigation findings.

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

# Lessons Learned

- Wazuh successfully detected failed authentication attempts.
- Windows Security Event Logs provided reliable forensic evidence.
- Authentication monitoring is effective for detecting brute force activity.
- Security monitoring should be validated regularly through controlled attack simulations.

---

# Recommendations

- Implement strong password policies.
- Configure account lockout policies.
- Continuously monitor authentication failures.
- Review failed login alerts regularly.
- Perform periodic validation of SIEM detection rules.

---

# Conclusion

The Windows authentication failure simulation successfully demonstrated Wazuh's ability to detect failed login attempts using Windows Security Event ID 4625.

The generated alerts, rule information, and Windows Security Logs provided sufficient evidence for a SOC analyst to investigate authentication-related security events and document the incident following standard incident response procedures.

The lab successfully validated the authentication monitoring capabilities of the Wazuh SIEM platform within the authorized SOC Home Lab environment.
