# Week 02 - NetworkWalks Internship

## Overview

This directory contains the practical assignments, technical documentation, screenshots, and final report completed during Week 02 of my cybersecurity internship at **NetworkWalks**.

The primary focus of this week was learning and implementing website footprinting, reconnaissance, DNS enumeration, network scanning, host discovery, and network topology visualization.

All practical activities were documented with commands, observations, results, and supporting screenshots.

---

## Learning Objectives

- Understand website footprinting and reconnaissance.
- Gather publicly available domain registration information.
- Identify website technologies and server information.
- Perform DNS resolution and DNS enumeration.
- Inspect HTTP response headers.
- Identify Web Application Firewall technologies.
- Understand local network configuration and subnetting.
- Discover active hosts using Nmap and Zenmap.
- Identify IP addresses and MAC addresses.
- Generate and analyze network topology visualizations.
- Document cybersecurity findings professionally.

---

## Project Modules

### 1. PM1 – Footprinting with Multiple Kali Tools

\<badge color="success">Completed\</badge>

**Objective:** Perform website footprinting and reconnaissance using multiple tools available in Kali Linux.

**Tools Used:**

| Tool     | Purpose                            |
| -------- | ---------------------------------- |
| WHOIS    | Domain registration lookup         |
| WhatWeb  | Website technology fingerprinting  |
| Nslookup | DNS resolution                     |
| cURL     | HTTP response header inspection    |
| Wafw00f  | Web Application Firewall detection |
| DNSRecon | DNS enumeration                    |

**Key Findings:**

- Identified domain registrar and name servers.
- Detected Apache and WordPress technologies.
- Resolved the domain to its IPv4 address.
- Inspected HTTP response headers.
- Identified ModSecurity (SpiderLabs).
- Enumerated publicly available DNS records.

<<<<<<< HEAD
**Project Documentation:** [View PM1 README](./PM1%20-%20Footprinting%20with%20multiple%20Kali%20tools/README.md)
=======
**Project Documentation:** [View PM1 README](./PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/README.md)
>>>>>>> 9b6c03f (completed week 2.)

---

### 2. PM5 – Network Scanning with Zenmap

\<badge color="success">Completed\</badge>

**Objective:** Perform network discovery and identify active devices on a local Wi-Fi network using Zenmap.

**Tools Used:**

- Zenmap
- Nmap
- Windows Command Prompt
- ipconfig
<<<<<<< HEAD

=======
d
>>>>>>> 9b6c03f (completed week 2.)
**Key Findings:**

| Parameter                  | Result          |
| -------------------------- | --------------- |
| Local IPv4 Address         | 192.168.31.164  |
| Default Gateway            | 192.168.31.1    |
| Network Subnet             | 192.168.31.0/24 |
| Total IP Addresses Scanned | 256             |
| Live Hosts Discovered      | 7               |
| Scan Duration              | 3.85 seconds    |

**Practical Activities:**

- Installed and configured Zenmap.
- Identified local IP address and subnet.
- Performed Ping Scan using Nmap.
- Discovered seven live hosts.
- Inspected host IP and MAC address information.
- Examined gateway operating system information.
- Generated and exported network topology.

<<<<<<< HEAD
**Project Documentation:** [View PM5 README](./PM5%20-%20Network%20scanning%20with%20Zenmap/README.md)

**Network Topology:**

=======
**Project Documentation:** [View PM5 README](./PM5%20–%20Network%20scanning%20with%20Zenmap/README.md)
>>>>>>> 9b6c03f (completed week 2.)


---

## Final Report

The final report consolidates the practical activities performed during Week 02.

It includes:

- Introduction and project objectives.
- Tools and technologies used.
- Footprinting and reconnaissance activities.
- Network scanning and host discovery.
- Technical observations and findings.
- Risk analysis and potential security impact.
- Security recommendations.
- Practical screenshots and evidence.

**Final Documentation:** [View Week 02 Penetration Testing Report](./Final-Report/README.md)

---

## Repository Structure

```text
week-02/
│
├── Final-Report/
│   └── README.md
│
├── PM1 - Footprinting with multiple Kali tools/
│   ├── Screenshots/
│   └── README.md
│
├── PM5 - Network scanning with Zenmap/
│   ├── screenshots/
│   ├── topology/
│   │   └── network-topology.png
│   └── README.md
│
└── README.md
```

---

## Key Learnings

During Week 02, I gained hands-on experience in:

1. Website footprinting and reconnaissance.
2. Domain registration and DNS information gathering.
3. Website technology fingerprinting.
4. HTTP response header analysis.
5. Web Application Firewall identification.
6. DNS record enumeration.
7. Network configuration and subnet calculations.
8. Live host discovery using Nmap.
9. IP and MAC address identification.
10. Network topology visualization using Zenmap.
11. Technical documentation and evidence management.

---

## Disclaimer

All practical activities were performed for educational purposes as part of the NetworkWalks cybersecurity internship.

Website reconnaissance and network discovery were limited to the assigned target and my personal local network.

No exploitation or unauthorized access was performed.

---

**Internship Organization:** NetworkWalks
**Intern:** Lakshya Atulkar
**Batch:** B084
**Week:** 02
**Domain:** Cybersecurity & Ethical Hacking

**Status:** Week 02 Documentation Completed
