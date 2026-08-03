# Incident Report 02 – PowerShell Execution Detection

## Incident Summary

A PowerShell execution event was detected on the Windows 10 endpoint monitored by Wazuh. The activity was captured through Sysmon and forwarded to the Wazuh Manager for analysis. This lab validates the organization's ability to detect PowerShell execution and investigate endpoint telemetry.

---

# Incident Information

| Field | Value |
|--------|-------|
| Incident ID | IR-002 |
| Incident Name | PowerShell Execution Detection |
| Severity | Medium *(To be verified after alert generation)* |
| Status | Closed (Lab Simulation) |
| Detection Source | Wazuh + Sysmon |
| Endpoint | Windows 10 |
| Analyst | Jeet Nishad |
| Date | *(To be updated after lab)* |

---

# Detection Timeline

| Time | Activity |
|------|----------|
| T0 | PowerShell command executed |
| T1 | Sysmon generated process creation event |
| T2 | Wazuh Agent forwarded the log |
| T3 | Wazuh generated alert |
| T4 | SOC analyst investigated the event |

*(Actual timestamps will be updated after completing the lab.)*

---

# Investigation

## Initial Observation

PowerShell execution was detected on the monitored endpoint. Wazuh generated an alert based on process creation logs collected from Sysmon.

---

## Indicators Observed

The following information will be collected after the lab:

- Process Name
- Parent Process
- Command Line
- Process ID (PID)
- User Account
- Computer Name
- Event ID
- Rule ID

---

## Evidence Collected

The following evidence will be added after performing the lab:

- PowerShell command executed
- Wazuh alert details
- Sysmon event
- Windows Event Log
- Dashboard screenshots

---

# Root Cause Analysis

This activity was intentionally generated inside an isolated SOC Home Lab to validate PowerShell detection capabilities. No unauthorized access or malicious compromise occurred.

---

# Impact Assessment

- No production systems affected
- No data loss
- No persistence established
- No privilege escalation performed
- Controlled lab environment

---

# Containment

No containment actions were required because this was an authorized security validation exercise.

---

# Eradication

Not applicable.

---

# Recovery

Not applicable.

---

# Lessons Learned

- Confirm Sysmon captures PowerShell process creation events.
- Validate Wazuh rule coverage for PowerShell execution.
- Improve analyst familiarity with PowerShell telemetry.
- Verify command-line logging for investigations.

---

# MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| PowerShell | T1059.001 |

---

# Incident Status

**Closed**

Reason:

This was a planned detection validation conducted within the SOC Home Lab.

---

# Appendix

The following items will be attached after completing the lab:

- Screenshot of PowerShell execution
- Wazuh alert screenshot
- Event details screenshot
- Relevant Sysmon event
- MITRE mapping
