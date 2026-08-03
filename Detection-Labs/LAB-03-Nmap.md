
# LAB 03 - Nmap Detection

## Objective

The objective of this lab is to simulate a reconnaissance attack using Nmap from the Kali Linux attacker machine against the Windows 10 victim machine and analyze the generated telemetry using Sysmon and Wazuh.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Wazuh 4.14.7 |
| Attacker | Kali Linux |
| Victim | Windows 10 |
| Monitoring | Sysmon + Wazuh Agent |
| Network | VirtualBox NAT Network |

---

## Attack Scenario

An attacker performs reconnaissance to discover open ports and services running on the target Windows system using Nmap.

This activity is commonly performed before attempting exploitation.

---

## Lab Topology

Attacker (Kali Linux)

IP Address:

10.0.2.4

↓

Victim (Windows 10)

IP Address:

10.0.2.5

↓

Sysmon

↓

Wazuh Manager

↓

Wazuh Dashboard

---

## Verification Steps

### Step 1 - Verify Nmap Installation

Command

```bash
nmap --version
```

Screenshot

```
LAB03-01-Nmap-Version.png
```

---

### Step 2 - Verify Kali IP Address

Command

```bash
ip a
```

Screenshot

```
LAB03-02-Kali-IP.png
```

---

### Step 3 - Verify Windows IP Address

Command

```cmd
ipconfig
```

Screenshot

```
LAB03-03-Windows-IP.png
```

---

### Step 4 - Verify Connectivity

Command

```bash
ping 10.0.2.5
```

Screenshot

```
LAB03-04-Ping-Success.png
```

---

## Attack Execution

### Basic Port Scan

Command

```bash
sudo nmap 10.0.2.5
```

Purpose

Identifies open TCP ports on the target.

Screenshot

```
LAB03-05-Basic-Scan.png
```

---

### Full Service Detection Scan

Command

```bash
sudo nmap -A 10.0.2.5
```

Purpose

Performs:

- OS Detection
- Version Detection
- Script Scanning
- Traceroute

Screenshot

```
LAB03-08-Full-Port-Scan.png
```

---

## Detection

The Windows endpoint generated Sysmon Network Connection (Event ID 3) logs after the scan.

These logs were successfully forwarded to Wazuh for analysis.

Screenshot

```
LAB03-07-Sysmon-Verification.png
```

---

## Wazuh Analysis

Observed Activity

- Network Connection Events
- Source IP: 10.0.2.4
- Destination IP: 10.0.2.5
- Reconnaissance Activity

Although a dedicated custom Nmap alert was not triggered, the reconnaissance activity was successfully recorded by Sysmon and ingested by Wazuh.

---

## MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| Network Service Discovery | T1046 |

---

## Outcome

Successful

The Nmap reconnaissance activity generated Windows Sysmon telemetry that was collected by Wazuh, allowing investigation of the network connections created during the scan.

---

## Skills Demonstrated

- Nmap
- Network Reconnaissance
- Sysmon
- Wazuh
- Log Analysis
- MITRE ATT&CK Mapping
- Detection Engineering
