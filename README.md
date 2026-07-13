# Wireshark Packet Analysis Lab

## 📖 Overview

This repository demonstrates the use of **Wireshark** for capturing, filtering, and analyzing network traffic in a controlled virtual lab environment.

The project focuses on understanding common network protocols, examining packet structures, and learning how packet analysis supports network troubleshooting and cybersecurity investigations.

---

# 🎯 Objective

The objectives of this lab are:

- Capture live network traffic
- Analyze common network protocols
- Understand packet flow
- Inspect TCP communication
- Analyze HTTP and FTP traffic
- Observe DNS resolution
- Apply Wireshark display filters
- Document observations

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

# 🛠 Tools Used

- Kali Linux
- Wireshark
- VMware Workstation
- Metasploitable2

---

# 📚 Methodology

The assessment followed these steps:

1. Start packet capture.
2. Generate network traffic.
3. Apply protocol filters.
4. Inspect packets.
5. Analyze protocol behavior.
6. Document observations.
7. Capture screenshots.
8. Summarize findings.

---

# 🔍 Protocols Analyzed

- ARP
- ICMP
- TCP
- DNS
- FTP
- HTTP

---

# 🔎 Wireshark Filters Used

| Filter | Purpose |
|---------|---------|
| arp | Display ARP packets |
| icmp | Display ICMP packets |
| tcp | Display TCP traffic |
| ftp | Display FTP packets |
| dns | Display DNS traffic |
| http | Display HTTP packets |
| ip.addr==192.168.0.10 | Filter packets for target |
| tcp.port==21 | FTP traffic |

---

# 📊 Results

The packet captures successfully demonstrated:

- ARP request and reply
- ICMP Echo Request and Reply
- TCP Three-Way Handshake
- FTP authentication
- DNS query and response
- HTTP GET request
- Packet filtering techniques
  
## 📄 Detailed Report

For the complete assessment, findings, and results, see **[REPORT.md](REPORT.md)**.

---

# 🛡 Recommendations

- Replace FTP with SFTP.
- Use HTTPS instead of HTTP.
- Monitor suspicious network traffic.
- Secure sensitive services.
- Encrypt network communication.

---

# 📖 Learning Outcomes

After completing this lab, I learned:

- Packet capture techniques
- Protocol analysis
- Display filters
- TCP/IP communication
- DNS resolution
- HTTP communication
- FTP authentication
- Network troubleshooting

---

## 👨‍💻 Author

**Gautam S B**

Aspiring Cybersecurity Engineer | VAPT Enthusiast

GitHub: https://github.com/GautamSB
