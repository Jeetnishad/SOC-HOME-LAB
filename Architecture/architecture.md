# SOC Home Lab Architecture

## Overview

This project demonstrates a Security Operations Center (SOC) Home Lab built using Wazuh SIEM, Kali Linux, Windows 10, and Sysmon.

The objective of this lab is to simulate real-world cyber attacks, collect logs, detect malicious activities, investigate alerts, and perform incident response.

## Components

- Kali Linux (Attacker)
- Windows 10 (Victim)
- Wazuh Agent
- Sysmon
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

## Data Flow

1. Attacker launches an attack from Kali Linux.
2. Windows 10 generates security events.
3. Sysmon captures detailed telemetry.
4. Wazuh Agent forwards logs.
5. Wazuh Manager analyzes events.
6. Wazuh Dashboard displays alerts.
7. Analyst investigates the incident.
