# Lab Environment

## Overview

This project was developed in a virtualized environment to simulate a real-world Security Operations Center (SOC). The lab consists of a Wazuh SIEM server deployed on Kali Linux and a monitored Windows 10 endpoint configured with the Wazuh Agent and Sysmon.

---

## Hardware Requirements

- Processor: Intel/AMD with Virtualization Support
- RAM: 8 GB or Higher
- Storage: 50 GB Free Disk Space

---

## Software Requirements

| Component | Version |
|-----------|----------|
| Oracle VirtualBox | Latest |
| Kali Linux | Latest |
| Windows 10 | 22H2 |
| Wazuh | 4.14.7 |
| Sysmon | Latest |

---

## Network Configuration

- Virtual Network: NAT Network
- Kali Linux: Wazuh Server
- Windows 10: Monitored Endpoint

---

## Lab Components

- Kali Linux
- Windows 10
- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Wazuh Agent
- Sysmon

---

## Purpose

The objective of this environment is to simulate enterprise SOC operations, monitor endpoint activity, detect threats, and investigate security incidents using Wazuh SIEM.
