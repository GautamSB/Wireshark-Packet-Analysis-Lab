# Wireshark Packet Analysis Lab

## 📖 Overview

This repository demonstrates the use of **Wireshark** to capture, filter, and analyze network traffic in a controlled virtual lab environment.

The assessment focuses on understanding how common network protocols operate, examining packet structures, inspecting client-server communication, and identifying security risks associated with unencrypted protocols.

---

# 🎯 Objective

The objectives of this assessment were to:

- Capture live network traffic
- Analyze common network protocols
- Understand packet flow and communication
- Examine the TCP Three-Way Handshake
- Analyze DNS query and response
- Inspect HTTP requests and responses
- Capture FTP authentication traffic
- Analyze Telnet communication
- Enumerate SMB shares and sessions
- Apply Wireshark display filters
- Document observations and security findings

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable2 |
| Packet Analyzer | Wireshark |
| Virtualization | VMware Workstation |
| Network Type | Bridged Network |

---

# 🛠️ Tools Used

- Kali Linux
- Wireshark
- VMware Workstation
- Metasploitable2
- FTP Client
- Telnet
- SMBClient

---

# 📚 Methodology

The assessment followed these steps:

1. Configure the lab environment.
2. Start packet capture on the active network interface.
3. Generate protocol-specific network traffic.
4. Apply Wireshark display filters.
5. Inspect protocol headers and packet details.
6. Analyze client-server communication.
7. Capture screenshots of significant findings.
8. Document observations and security implications.

---

# 🔍 Protocols Analyzed

- ARP
- ICMP
- TCP
- DNS
- HTTP
- FTP
- Telnet
- SMB

---

# 🔎 Wireshark Display Filters Used

| Filter | Purpose |
|---------|---------|
| `arp` | Display ARP packets |
| `icmp` | Display ICMP packets |
| `tcp` | Display TCP traffic |
| `dns` | Display DNS queries and responses |
| `http` | Display HTTP traffic |
| `ftp` | Display FTP communication |
| `telnet` | Display Telnet sessions |
| `smb` | Display SMB packets |
| `smb2` | Display SMBv2 packets |
| `ip.addr == 192.168.0.14` | Filter target traffic |
| `tcp.port == 21` | FTP traffic |
| `tcp.port == 23` | Telnet traffic |
| `tcp.port == 80` | HTTP traffic |
| `tcp.port == 445` | SMB traffic |

---

# 📊 Results

The packet captures successfully demonstrated:

- ARP Request and Reply
- ICMP Echo Request and Echo Reply
- TCP Three-Way Handshake
- DNS Query and Response
- HTTP GET and POST Requests
- FTP Authentication
- Telnet Login Session
- SMB Share Enumeration
- SMB Anonymous Share Access
- Packet filtering and protocol analysis

---

# 📄 Detailed Report

A detailed assessment report containing methodology, packet analysis, observations, security findings, and recommendations is available in **[REPORT.md](REPORT.md)**.

---

# 📖 Learning Outcomes

After completing this assessment, I gained practical experience in:

- Packet capture using Wireshark
- Applying display filters
- TCP/IP communication analysis
- TCP Three-Way Handshake
- DNS resolution analysis
- HTTP request and response inspection
- FTP authentication analysis
- Telnet session analysis
- SMB share enumeration
- Packet header analysis
- Network troubleshooting
- Identifying insecure network protocols

---

## 👨‍💻 Author

**Gautam S B**

Aspiring Cybersecurity Engineer | VAPT Enthusiast

**GitHub:** https://github.com/GautamSB
