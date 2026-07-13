# Wireshark Network Packet Analysis Report

## Assessment Information

| Item | Details |
|------|---------|
| Assessment Type | Network Packet Capture & Protocol Analysis |
| Packet Analyzer | Wireshark 4.x |
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable2 |
| Target IP | 192.168.0.14 |
| Network | VMware Bridged Network |
| Virtualization | VMware Workstation |
| Date | 13 July 2026 |

---

# Objective

The objective of this assessment was to capture and analyze network traffic generated between the Kali Linux attacker machine and the Metasploitable2 target. The analysis focused on understanding protocol behavior, packet structures, network communication, and identifying insecure protocols commonly found in penetration testing laboratories.

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System (Attacker) | Kali Linux |
| Operating System (Target) | Metasploitable2 |
| Packet Capture Tool | Wireshark |
| Virtualization | VMware Workstation |
| Network Mode | Bridged Network |

---

# Protocol Analysis

The following protocols were analyzed during the assessment.

---

# Address Resolution Protocol (ARP)

## Purpose

ARP resolves an IPv4 address into a MAC address before communication begins.

## Display Filter

```text
arp
```

## Observation

- Observed ARP Request packets.
- Observed ARP Reply packets.
- Verified successful MAC address resolution.
- Source and destination MAC addresses were successfully identified.

---

# Internet Control Message Protocol (ICMP)

## Purpose

ICMP is used for connectivity testing and network diagnostics.

## Display Filter

```text
icmp
```

## Traffic Generated

```bash
ping 192.168.0.14
```

## Observation

- ICMP Echo Request captured.
- ICMP Echo Reply captured.
- TTL values observed.
- Response time successfully measured.

---

# Transmission Control Protocol (TCP)

## Purpose

TCP provides reliable, connection-oriented communication.

## Display Filter

```text
tcp
```

## Observation

Captured complete TCP communication including:

- TCP Three-Way Handshake
- Sequence Numbers
- Acknowledgement Numbers
- Window Size
- TCP Flags
- Connection Termination

### TCP Handshake

1. SYN
2. SYN-ACK
3. ACK

---

# Domain Name System (DNS)

## Purpose

DNS translates domain names into IP addresses.

## Display Filter

```text
dns
```

## Traffic Generated

```bash
ping testfire.net
```

## Observation

Captured DNS Query and DNS Response.

Example:

```
Query:
testfire.net

Response:
65.61.137.117
```

Observed Records

- A Record
- AAAA Record
- Response Code
- Transaction ID
- TTL

---

# Hypertext Transfer Protocol (HTTP)

## Purpose

HTTP is used for web communication.

## Display Filter

```text
http
```

## Traffic Generated

Visited

```
http://192.168.0.14
```

and

```
http://192.168.0.14/dvwa
```

## Observation

Captured

- HTTP GET Request
- HTTP POST Request
- HTTP 200 OK
- HTTP 302 Redirect
- HTTP 404 Not Found
- HTTP Headers

Observed HTTP Headers

- Host
- User-Agent
- Accept
- Referer
- Cookie
- Content-Type
- Content-Length

Captured HTTP login request to DVWA demonstrating transmission of credentials over unencrypted HTTP.

---

# File Transfer Protocol (FTP)

## Purpose

FTP provides file transfer between client and server.

## Display Filter

```text
ftp
```

## Traffic Generated

```bash
ftp 192.168.0.14
```

## Observation

Captured

- FTP Banner
- USER command
- PASS command
- Login Authentication
- Directory Listing
- FTP Commands
- Server Responses

Verified that FTP credentials are transmitted in plaintext.

---

# Telnet Protocol

## Purpose

Telnet provides remote command-line access over TCP.

## Display Filter

```text
telnet
```

## Traffic Generated

```bash
telnet 192.168.0.14
```

## Observation

Captured

- Telnet Login Banner
- Username
- Password
- Shell Prompt
- Interactive Commands
- Server Responses

Verified that Telnet transmits user credentials and terminal data without encryption.

---

# Server Message Block (SMB)

## Purpose

SMB provides shared file and printer access over a network.

## Display Filter

```text
smb || smb2
```

## Traffic Generated

```bash
smbclient -L //192.168.0.14 -N

smbclient //192.168.0.14/tmp -N
```

## Observation

Captured

- SMB Session Setup
- Anonymous Authentication
- Tree Connect Request
- Share Enumeration
- Directory Listing
- SMB Responses

Enumerated Shares

- print$
- tmp
- opt
- IPC$
- ADMIN$

Successfully accessed the public **tmp** share and listed its contents.

---

# Wireshark Display Filters Used

| Filter | Purpose |
|---------|---------|
| arp | ARP packets |
| icmp | Ping traffic |
| tcp | TCP packets |
| dns | DNS queries and responses |
| ftp | FTP communication |
| http | HTTP traffic |
| telnet | Telnet communication |
| smb | SMB packets |
| smb2 | SMB Version 2 traffic |
| ip.addr==192.168.0.14 | Target packets |
| tcp.port==21 | FTP |
| tcp.port==23 | Telnet |
| tcp.port==80 | HTTP |
| tcp.port==445 | SMB |

---

# Results Summary

Successfully analyzed the following protocols:

| Protocol | Status |
|----------|--------|
| ARP | Completed |
| ICMP | Completed |
| TCP | Completed |
| DNS | Completed |
| HTTP | Completed |
| FTP | Completed |
| Telnet | Completed |
| SMB | Completed |

---

# Security Findings

The assessment identified several insecure communication methods commonly present in intentionally vulnerable laboratory environments.

Findings include:

- FTP transmits usernames and passwords in plaintext.
- Telnet transmits login credentials without encryption.
- HTTP exposes sensitive web requests in cleartext.
- Anonymous SMB shares allow unauthenticated access.
- DNS queries reveal requested domain names.
- Network traffic can be monitored by any attacker with packet capture capabilities on the same network segment.

---

# Security Recommendations

- Replace FTP with SFTP or FTPS.
- Replace Telnet with SSH.
- Use HTTPS instead of HTTP.
- Disable anonymous SMB access.
- Encrypt sensitive communications.
- Monitor network traffic for suspicious activity.
- Apply strong authentication mechanisms.
- Restrict unnecessary network services.
- Implement network segmentation.
- Regularly monitor packet captures for anomalous behavior.

---

# Conclusion

This assessment successfully demonstrated the practical use of Wireshark for packet capture and protocol analysis in a controlled penetration testing laboratory. Multiple protocols including ARP, ICMP, TCP, DNS, HTTP, FTP, Telnet, and SMB were analyzed to understand how devices communicate across a network. The captured traffic highlighted the risks associated with legacy protocols that transmit sensitive information in plaintext and reinforced the importance of secure communication protocols in modern network environments.

---
