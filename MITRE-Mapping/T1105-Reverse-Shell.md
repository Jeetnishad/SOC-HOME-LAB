# T1105 – Reverse Shell

## MITRE ATT&CK Technique

| Field | Details |
|--------|---------|
| Technique ID | T1105 |
| Technique Name | Ingress Tool Transfer |
| Tactic | Command and Control |

---

# Overview

MITRE ATT&CK Technique **T1105 – Ingress Tool Transfer** describes adversary behavior where tools or payloads are transferred or communication channels are established between a compromised system and an attacker-controlled host. Reverse shells are a common example of this technique because they provide attackers with remote interactive access to an infected endpoint.

---

# Lab Objective

The objective of this lab was to simulate a reverse shell attack from a Windows 10 endpoint to a Kali Linux attacker machine using Netcat (Ncat) and investigate the generated telemetry using Sysmon and Wazuh SIEM.

---

# Lab Environment

| Component | Details |
|----------|----------|
| Attacker | Kali Linux |
| Victim | Windows 10 |
| SIEM | Wazuh 4.14.7 |
| Endpoint Monitoring | Sysmon + Wazuh Agent |
| Tool Used | Netcat (Ncat) |
| Virtualization | Oracle VirtualBox |

---

# Attack Procedure

1. Verified network connectivity between Kali Linux and Windows 10.
2. Started a Netcat listener on Kali Linux using TCP port 4444.
3. Executed an Ncat reverse shell command from the Windows endpoint.
4. Established a reverse shell connection to the Kali Linux machine.
5. Executed Windows commands (`whoami`, `hostname`, and `ipconfig`) through the remote shell.
6. Investigated the generated telemetry using the Wazuh Dashboard.

---

# Detection Workflow

```
Windows 10

↓

Netcat Reverse Shell

↓

Sysmon Event ID 1 (Process Creation)

↓

Wazuh Agent

↓

Wazuh Manager

↓

Threat Hunting

↓

SOC Investigation
```

---

# Detection Evidence

The following evidence was collected during the investigation:

- Reverse shell connection established successfully.
- Sysmon generated Process Creation (Event ID 1).
- Wazuh collected endpoint telemetry.
- Threat Hunting displayed abnormal command execution.
- Wazuh Rule **92052** identified abnormal command prompt execution.

---

# Indicators of Compromise (IOCs)

- Execution of `ncat.exe`
- Command Prompt (`cmd.exe`) launched by an abnormal process
- Outbound connection from Windows to Kali Linux
- Interactive remote shell session
- Suspicious process creation events

---

# MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Command and Control | Ingress Tool Transfer | T1105 |

---

# Security Impact

A successful reverse shell allows an attacker to remotely execute commands on a compromised endpoint. If such activity occurs in a production environment, it may indicate post-exploitation or unauthorized remote access and should be treated as a high-priority security incident.

---

# Detection Notes

During this lab, Sysmon successfully captured the reverse shell process creation activity, and Wazuh collected the corresponding telemetry for investigation. The generated alerts provided visibility into abnormal command execution associated with the reverse shell.

---

# Conclusion

This lab successfully demonstrated MITRE ATT&CK Technique **T1105 – Ingress Tool Transfer** by establishing a reverse shell between a Windows endpoint and a Kali Linux attacker machine. The activity generated endpoint telemetry that was captured by Sysmon and investigated through Wazuh SIEM, demonstrating practical SOC Analyst skills in detection, investigation, and MITRE ATT&CK mapping.
