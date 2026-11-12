# PENETRATION TESTING REPORT

### Footprinting & Network Scanning Phases

**W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**

| Field | Detail |
|---|---|
| **Pentester Name** | Lakshya Atulkar |
| **Program/Batch** | B084 – NetworkWalks |
| **Date** | 12 November 2026 |
| **Modules Completed** | W2-PM1 (Multiple Kali Tools), W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. networkwalks.com  2. Personal Local Wi-Fi Network |
| **Testing Environment** | Kali Linux (VirtualBox), Windows 10/11 |
| **Phases Covered** | Phase 1: Reconnaissance & Footprinting; Phase 2: Scanning & Network Discovery |
| **Project Status** | Phase 1 and Phase 2 Completed |

---

# 1. Liability Disclaimer

All activities documented in this report were performed for educational and cybersecurity training purposes as part of the NetworkWalks internship program.

Testing was restricted to the assigned target and my personally owned local network. Activities were limited to information gathering, reconnaissance, DNS enumeration, and authorized network discovery.

No exploitation, brute-force attacks, privilege escalation, denial-of-service attacks, or unauthorized access attempts were performed.

The information collected is intended for educational documentation and security awareness. Any further testing must be performed only with appropriate authorization.

---

# 2. Introduction

This report documents the practical activities completed during Week 02 of my Cybersecurity and Ethical Hacking internship at NetworkWalks.

The primary objective was to understand the initial phases of penetration testing, particularly reconnaissance, footprinting, scanning, and network discovery.

Two project modules were completed:

**W2-PM1 – Footprinting with Multiple Kali Tools**

This module involved gathering publicly available information about the `networkwalks.com` domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, cURL, Wafw00f, and DNSRecon.

**W2-PM5 – Network Scanning with Zenmap**

This module involved identifying my local network configuration, discovering active hosts, examining IP and MAC addresses, reviewing available host information, and generating a network topology using Zenmap.

The footprinting activities were conducted using Kali Linux running in VirtualBox, while network scanning was performed using Zenmap on Windows.

Each practical activity was documented with its command, observations, results, and screenshots.

---

# 3. Tools Used

The following tools and technologies were used throughout the practical activities.

| Tool | Purpose |
|---|---|
| Kali Linux | Linux-based cybersecurity testing environment |
| WHOIS | Retrieve publicly available domain registration information |
| WhatWeb | Identify website technologies and web server information |
| Nslookup | Resolve domain names into IP addresses |
| cURL | Inspect HTTP response headers |
| Wafw00f | Identify Web Application Firewall technologies |
| DNSRecon | Enumerate DNS records |
| Zenmap | Graphical interface for Nmap network scanning |
| Nmap | Network discovery and scanning |
| Windows CMD | Identify local network configuration |
| VirtualBox | Run Kali Linux in a virtualized environment |

---

# 4. Activities Performed

## 4.1 Phase 1 – Footprinting and Reconnaissance (W2-PM1)

The first phase focused on gathering publicly accessible information about the target domain `networkwalks.com`.

Six different Kali Linux tools were used to collect information about domain registration, web technologies, DNS resolution, HTTP headers, WAF protection, and DNS infrastructure.

### 4.1.1 WHOIS – Domain Registration Lookup

**Command:**

```bash
whois networkwalks.com
```

**Observations:**

- Registrar: GoDaddy.com, LLC
- Domain Creation Date: 06 November 2019
- Registry Expiry Date: 06 November 2027
- Name Server 1: NS6135.HOSTGATOR.COM
- Name Server 2: NS6136.HOSTGATOR.COM
- DNSSEC: Unsigned

**Result:**

WHOIS successfully retrieved publicly available domain registration information, registrar details, registration dates, and name server information.

**Security Relevance:**

Domain registration information can help security professionals understand the domain's registration history and associated infrastructure.

**Evidence:**

![WHOIS Results](../PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/Screenshots/01-whois%20networkwalks.png)

### 4.1.2 WhatWeb – Website Technology Fingerprinting

**Command:**

```bash
whatweb networkwalks.com
```

**Observations:**

- Web Server: Apache
- CMS: WordPress 7.1.4 (as reported by WhatWeb)
- Bootstrap: 7.1.4 (as reported by WhatWeb)
- jQuery: 3.7.1
- WordPress Download Manager: 3.3.76
- Website IP Address: 192.232.216.135
- HTTP Status: 200 OK

**Result:**

WhatWeb successfully identified technologies and information exposed by the target website.

**Security Relevance:**

Technology fingerprinting can help security professionals identify software components that may require further security review and maintenance.

**Evidence:**

![WhatWeb Results](../PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/Screenshots/02-whatweb%20networkwalks.png)

### 4.1.3 Nslookup – DNS Resolution

**Command:**

```bash
nslookup networkwalks.com
```

**Observations:**

- DNS Server: 8.8.8.8
- DNS Port: 53
- Domain: networkwalks.com
- Resolved IPv4 Address: 192.232.216.135
- Response: Non-authoritative answer

**Result:**

The domain name was successfully resolved to its corresponding IPv4 address using Google's public DNS resolver.

**Security Relevance:**

DNS resolution helps identify the IP address associated with a domain and provides a starting point for understanding its network infrastructure.

**Evidence:**

![Nslookup Results](../PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/Screenshots/03-nslookup%20networkwalks.png)

### 4.1.4 cURL – HTTP Response Header Inspection

**Command:**

```bash
curl -I https://networkwalks.com
```

**Observations:**

- HTTP Status: 200 OK
- Server: Apache
- Content-Type: text/html; charset=UTF-8
- Referrer-Policy: no-referrer-when-downgrade
- WordPress REST API reference: /wp-json/
- Cookie attributes: Secure and HttpOnly

**Result:**

The cURL command successfully retrieved the HTTP response headers and provided information about the server, response status, cookie attributes, and website configuration.

**Security Relevance:**

HTTP response headers provide useful information about server configuration and security-related browser policies.

**Evidence:**

![cURL Results](../PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/Screenshots/04-curl%20networkwalks.png)

### 4.1.5 Wafw00f – Web Application Firewall Detection

**Command:**

```bash
wafw00f networkwalks.com
```

**Observations:**

- WAF Detection: Successful
- Identified WAF: ModSecurity (SpiderLabs)
- Number of Requests: 2

**Result:**

Wafw00f successfully identified ModSecurity (SpiderLabs) as the Web Application Firewall associated with the target website.

**Security Relevance:**

A Web Application Firewall helps monitor and filter HTTP traffic according to configured security rules.

Identifying the WAF provides information about the website's security infrastructure.

**Evidence:**

![Wafw00f Results](../PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/Screenshots/05-wafw00f%20networkwalks.png)

### 4.1.6 DNSRecon – DNS Enumeration

**Command:**

```bash
dnsrecon -d networkwalks.com -t std
```

**Observations:**

- SOA Record: ns6135.hostgator.com
- Name Servers: ns6135.hostgator.com and ns6136.hostgator.com
- A Record: 192.232.216.135
- MX Record: mail.networkwalks.com
- TXT Records: SPF and Google site verification
- SRV Records: Autodiscover-related services
- Total Records Found: 8
- DNSSEC Query: No answer returned

**Result:**

DNSRecon successfully enumerated publicly available DNS records and identified information about the domain's DNS infrastructure.

**Security Relevance:**

DNS enumeration helps security professionals understand domain infrastructure, mail-related records, and publicly exposed service information.

**Evidence:**

![DNSRecon Results](../PM1%20–%20Footprinting%20with%20multiple%20Kali%20tools/Screenshots/06-dnsrecon%20networkwalks.png)

---

## 4.2 Phase 2 – Network Scanning and Discovery (W2-PM5)

The second phase focused on identifying devices connected to my personal Wi-Fi network using Zenmap.

The objective was to discover live hosts, identify their network addresses, examine host information, and visualize the discovered network.

### 4.2.1 Zenmap Installation

Zenmap was downloaded from the official Nmap website:

https://nmap.org/download.html

The official Windows installer was executed, and Zenmap was successfully installed and launched.

**Result:**

The Zenmap graphical interface was successfully opened and configured for network scanning.

**Evidence:**

![Zenmap Installation](../PM5%20–%20Network%20scanning%20with%20Zenmap/screenshots/01-zenmap-installation.png)

### 4.2.2 Local IP Address and Network Configuration

**Command:**

```cmd
ipconfig
```

**Active Network Interface:** Wireless LAN adapter Wi-Fi

**Observed Network Configuration:**

| Parameter | Value |
|---|---|
| IPv4 Address | 192.168.31.164 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.31.1 |
| DNS Suffix | lan |

**Subnet Calculation:**

The subnet mask `255.255.255.0` corresponds to a `/24` network prefix.

Therefore, the identified network subnet was:

```text
192.168.31.0/24
```

**Network Details:**

- Network Address: 192.168.31.0
- Host IP Address: 192.168.31.164
- Default Gateway: 192.168.31.1
- Broadcast Address: 192.168.31.255
- Usable Host Range: 192.168.31.1 – 192.168.31.254

**Result:**

Successfully identified the active Wi-Fi network configuration and calculated the subnet for network discovery.

**Evidence:**

![IP Configuration](../PM5%20–%20Network%20scanning%20with%20Zenmap/screenshots/02-ipconfig.png)

### 4.2.3 Ping Scan – Live Host Discovery

**Target Network:**

```text
192.168.31.0/24
```

**Zenmap Profile:** Ping Scan

**Command:**

```bash
nmap -sn 192.168.31.0/24
```

**Command Explanation:**

- `nmap`: Starts the Nmap scanning engine.
- `-sn`: Performs host discovery without port scanning.
- `192.168.31.0/24`: Specifies the target network.

**Observations:**

| Parameter | Result |
|---|---|
| Target Network | 192.168.31.0/24 |
| Total IP Addresses Scanned | 256 |
| Live Hosts Discovered | 7 |
| Scan Duration | 3.85 seconds |
| Scan Status | Completed |

The scan output reported:

```text
Nmap done: 256 IP addresses (7 hosts up)
```

**Result:**

Successfully discovered seven live hosts on the local Wi-Fi network using the Ping Scan profile.

**Evidence:**

![Ping Scan Results](../PM5%20–%20Network%20scanning%20with%20Zenmap/screenshots/03-ping-scan.png)

### 4.2.4 Identification of Live Hosts

The Ping Scan results identified seven active hosts on the local network.

**Discovered Hosts:**

| Hostname / Device | IPv4 Address |
|---|---|
| jiofiber.local.html | 192.168.31.1 |
| DESKTOP-2RBSLB0.lan | 192.168.31.78 |
| vivo-1938.lan | 192.168.31.127 |
| Meow.lan | 192.168.31.174 |
| Unnamed Host | 192.168.31.203 |
| realme-C2.lan | 192.168.31.248 |
| DESKTOP-69HJI12.lan | 192.168.31.164 |

**Result:**

Seven live hosts were identified and their available hostname and IP address information was recorded.

### 4.2.5 Host Details and MAC Address Identification

The Host Details tab in Zenmap was used to inspect information about an individual discovered device.

The selected device was the local Wi-Fi gateway.

**Observed Information:**

| Parameter | Value |
|---|---|
| Hostname | jiofiber.local.html |
| IPv4 Address | 192.168.31.1 |
| MAC Address | 04:68:74:CE:AD:BA |
| Host Status | Up |
| Operating System | OpenWrt 21.02 |
| Kernel | Linux 5.4 |

**Additional Observations:**

The earlier Intense Scan output for the gateway reported:

- Open Ports: 6
- Filtered Ports: 0
- Closed Ports: 994
- Total Scanned Ports: 1000

The initial scan also displayed open ports 80, 443, and 8080.

These observations are from the earlier Intense Scan, not the Ping Scan.

**Result:**

Successfully inspected host information, identified the gateway's MAC address, and observed operating system information reported by Zenmap.

**Evidence:**

![Host Details](../PM5%20–%20Network%20scanning%20with%20Zenmap/screenshots/04-host-details.png)

### 4.2.6 Network Topology Generation

The Topology tab in Zenmap was used to visualize the discovered network devices.

**Steps Performed:**

1. Opened the completed scan results in Zenmap.
2. Navigated to the Topology tab.
3. Observed the discovered network nodes.
4. Examined the visual representation of the network.
5. Used the Save Graphic option.
6. Exported the network topology as a PNG image.

**Observed Network Devices:**

- Gateway: 192.168.31.1
- Windows laptop: 192.168.31.164
- Additional discovered devices: 192.168.31.78, 192.168.31.127, 192.168.31.174, 192.168.31.203, and 192.168.31.248.

**Result:**

Successfully generated and exported a network topology visualization showing the discovered network devices.

**Topology Screenshot:**

![Zenmap Topology Screenshot](../PM5%20–%20Network%20scanning%20with%20Zenmap/screenshots/05-network-topology.png)

**Exported Topology Graphic:**

![Exported Network Topology](../PM5%20–%20Network%20scanning%20with%20Zenmap/topology/network-topology.png)

---

# 5. Risk Analysis / Impact

Based on the information collected during the footprinting and network scanning activities, the following potential security observations were identified.

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|---|---|---|---|---|
| 1 | Website technology information exposed | WhatWeb identified Apache, WordPress and related technologies | May assist technology fingerprinting and software security reviews | Low |
| 2 | Public IP address identifiable | DNS resolution returned 192.232.216.135 | Provides information about the website's hosting infrastructure | Informational |
| 3 | HTTP configuration information exposed | cURL returned server headers and WordPress REST API reference | May assist further information gathering | Low |
| 4 | WAF technology identifiable | Wafw00f identified ModSecurity (SpiderLabs) | Reveals information about the website's security infrastructure | Informational |
| 5 | DNS infrastructure information exposed | DNSRecon identified NS, MX, TXT and SRV records | Helps build a profile of domain infrastructure | Informational |
| 6 | Multiple live devices identified | Zenmap discovered seven live hosts | Unknown devices may require identification and inventory verification | Low |
| 7 | Gateway services identified | Earlier Intense Scan reported open ports on the gateway | Unnecessary or exposed services may increase attack surface if not properly secured | Requires further review |

**Risk Level Key:**

- Critical: Confirmed severe security issue.
- High: Significant security concern.
- Medium: Potential security concern requiring investigation.
- Low: Limited potential impact.
- Informational: Observation without a confirmed security weakness.

The above findings are based on reconnaissance and network discovery observations. No exploitable vulnerability was confirmed during these activities.

The identification of software technologies, public DNS records, WAF products, or open ports does not automatically indicate that a system is vulnerable.

Further authorized testing would be required to validate any security weaknesses.

---

# 6. Recommendations

Based on the observations collected during the practical exercises, the following recommendations are suggested:

1. **Regular Software Updates:** Keep CMS platforms, plugins, web servers, and other software components updated.
2. **Review Technology Exposure:** Periodically review publicly exposed technology and version information.
3. **HTTP Security Configuration:** Review HTTP response headers and ensure that appropriate security policies are configured.
4. **DNS Security:** Regularly review DNS records and remove obsolete or unnecessary records.
5. **WAF Monitoring:** Maintain appropriate ModSecurity rules and monitor suspicious web traffic.
6. **Network Inventory:** Maintain an updated inventory of all authorized devices connected to the network.
7. **Unknown Device Investigation:** Investigate unexpected devices discovered during network scans.
8. **Gateway Security:** Review exposed router services and disable unnecessary services where appropriate.
9. **Network Segmentation:** Separate guest devices and untrusted devices from important internal systems.
10. **Regular Security Assessments:** Conduct periodic authorized network discovery and security assessments.

---

# 7. Conclusion

During Week 02 of my Cybersecurity and Ethical Hacking internship at NetworkWalks, I completed two practical modules covering footprinting, reconnaissance, network scanning, and host discovery.

In W2-PM1, I used six Kali Linux tools to collect publicly available information about the `networkwalks.com` domain.

I gained practical experience with WHOIS, WhatWeb, Nslookup, cURL, Wafw00f, and DNSRecon. These tools helped me understand domain registration information, website technology fingerprinting, DNS resolution, HTTP response headers, WAF identification, and DNS enumeration.

In W2-PM5, I installed and used Zenmap to perform network discovery on my personal Wi-Fi network.

I identified my local IP configuration, calculated the network subnet, discovered seven live hosts, inspected available IP and MAC address information, and generated a network topology visualization.

These activities helped me understand how cybersecurity professionals gather information about systems and networks before conducting more advanced security assessments.

The practical exercises also improved my understanding of network infrastructure, DNS, HTTP, host discovery, and the importance of documenting technical observations with evidence.

Overall, Week 02 provided valuable hands-on experience with the initial phases of penetration testing and cybersecurity reconnaissance.

---

# 8. Evidences Collected

The following screenshots were captured during the practical activities and organized within their respective project folders.

## W2-PM1 – Footprinting with Multiple Kali Tools

| No. | Evidence | Description |
|---|---|---|
| 01 | 01-whois networkwalks.png | Domain registration lookup |
| 02 | 02-whatweb networkwalks.png | Website technology fingerprinting |
| 03 | 03-nslookup networkwalks.png | DNS resolution |
| 04 | 04-curl networkwalks.png | HTTP response header inspection |
| 05 | 05-wafw00f networkwalks.png | WAF identification |
| 06 | 06-dnsrecon networkwalks.png | DNS enumeration |

## W2-PM5 – Network Scanning with Zenmap

| No. | Evidence | Description |
|---|---|---|
| 01 | 01-zenmap-installation.png | Zenmap installation and interface |
| 02 | 02-ipconfig.png | Local network configuration |
| 03 | 03-ping-scan.png | Live host discovery |
| 04 | 04-host-details.png | Host and MAC address information |
| 05 | 05-network-topology.png | Network topology visualization |

**Additional Evidence:** The exported network topology is available at `PM5 - Network scanning with Zenmap/topology/network-topology.png`.

---

**Internship Organization:** NetworkWalks  
**Intern:** Lakshya Atulkar  
**Program/Batch:** B084  
**Report:** Week 02 – Penetration Testing Report  
**Date:** 12 November 2026

**End of Report**