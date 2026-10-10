## Overview

This project demonstrates the use of Suricata in Intrusion Prevention System (IPS) mode to block selected network traffic in a controlled cybersecurity home lab.

The experiment uses Kali Linux as the testing machine, Ubuntu as the Suricata IPS gateway, and Windows Server 2022 as the target. Custom drop rules are used to test whether matching TCP connection attempts are blocked.

## Objectives

- Configure Suricata to process traffic through Linux NFQUEUE.
- Create and validate custom IPS drop rules.
- Block selected TCP connection attempts from Kali Linux to Windows Server.
- Verify blocking actions through Suricata's EVE JSON logs.
- Compare Nmap scan results before and after applying blocking rules.

## Lab Configuration

| Component | Role |
|---|---|
| Kali Linux | Generates controlled connection attempts |
| Ubuntu | Runs Suricata in IPS mode |
| Windows Server 2022 | Target system |
| Nmap | Tests TCP port accessibility |
| EVE JSON | Records Suricata alert and blocking events |

## Blocking Results

A custom Suricata drop rule using signature ID `1000004` successfully blocked TCP connection attempts from Kali Linux (`192.168.195.130`) to Windows Server 2022 (`192.168.195.134`) on destination port `445`.

Suricata recorded events with the action `blocked`, and Nmap subsequently reported the SMB port as `filtered`.

A broader TCP blocking rule was also prepared to test additional destination ports. Its results should be documented after confirming that the updated rule was loaded and that the corresponding test traffic was blocked.

## Key Learning Outcomes

- Understanding the difference between IDS alerting and IPS prevention.
- Configuring and validating Suricata drop rules.
- Using NFQUEUE to process forwarded network traffic.
- Verifying blocking behavior with EVE JSON and Nmap.
- Evaluating the impact of traffic-blocking rules in a controlled lab.
