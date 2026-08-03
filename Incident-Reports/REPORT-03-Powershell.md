# Incident Report 02 – PowerShell Activity Detection

## Executive Summary

This incident report documents the detection and investigation of PowerShell activity performed within an authorized SOC Home Lab environment.

The objective of this exercise was to validate Wazuh's capability to monitor PowerShell execution, collect endpoint telemetry through Sysmon, and generate security alerts for analyst investigation.

The activity was performed in a controlled lab environment, and no unauthorized actions were executed.

---

# Incident Information

| Field | Value |
|--------|-------|
| Incident ID | IR-002 |
| Incident Name | PowerShell Activity Detection |
| Category | Command and Script Interpreter |
| Severity | To be updated |
| Status | Closed |
| Environment | Authorized SOC Home Lab |
| Detection Tool | Wazuh SIEM 4.14.7 |
| Endpoint | Windows 10 Home |
| Log Source | Sysmon / Windows Event Logs |

---

# Incident Description

PowerShell commands were intentionally executed on the monitored Windows endpoint to generate endpoint telemetry for detection testing.

The generated events were collected by Sysmon and forwarded to the Wazuh Manager through the Wazuh Agent.

Wazuh analyzed the events and generated alerts that enabled the activity to be investigated.

---

# Detection Summary

PowerShell execution activity was detected through Windows event logs and Sysmon process creation events.

The generated alerts confirmed that PowerShell execution was successfully monitored within the SOC Home Lab environment.

---

# Timeline of Events

| Time | Activity |
|------|----------|
| PowerShell Executed | To be updated |
| Event Generated | To be updated |
| Wazuh Alert Generated | To be updated |
| Investigation Started | To be updated |
| Investigation Completed | To be updated |

---

# Affected Assets

| Asset | Description |
|--------|-------------|
| Windows 10 Home | Monitored Endpoint |
| Wazuh Agent | Log Collection |
| Sysmon | Endpoint Telemetry |
| Wazuh Manager | Alert Generation |
| Wazuh Dashboard | Alert Investigation |

---

# Indicators of Compromise (IoCs)

The following information will be collected during the investigation:

- PowerShell process execution
- Process ID
- Parent Process
- Command Line
- Wazuh Rule ID
- Alert Level

> This section will be updated after completing the practical lab.

---

# Investigation Findings

The investigation will verify:

- PowerShell execution
- Parent process
- Command line arguments
- Wazuh rule triggered
- Alert severity
- Event source
- Process creation details

---

# Root Cause Analysis

The PowerShell activity was intentionally executed as part of a controlled SOC Home Lab exercise to validate detection capabilities.

No malicious activity occurred outside the authorized testing environment.

---

# Response Actions

The following actions were performed:

- Reviewed Wazuh alerts
- Verified Sysmon logs
- Investigated process creation
- Correlated PowerShell events
- Documented investigation findings

---

# MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Execution | T1059.001 – PowerShell |

Detailed mapping is available in:

MITRE-Mapping/T1059.001-PowerShell.md

---

# Lessons Learned

- PowerShell activity can be effectively monitored using Sysmon.
- Wazuh provides visibility into PowerShell execution.
- Endpoint telemetry improves SOC investigations.
- PowerShell monitoring should be enabled in production environments.

---

# Recommendations

- Enable PowerShell logging.
- Monitor suspicious PowerShell commands.
- Investigate encoded or obfuscated PowerShell activity.
- Continuously validate SIEM detection rules.
- Correlate PowerShell events with other endpoint activity.

---

# Conclusion

The PowerShell detection exercise successfully demonstrated Wazuh's ability to monitor PowerShell execution and provide meaningful telemetry for security investigations.

The collected evidence will be used to complete the MITRE ATT&CK mapping and document the overall investigation.
