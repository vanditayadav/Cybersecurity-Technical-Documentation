# Network Protocols and Services

## 1. File Transfer Protocols

| Protocol | Purpose | Default port |
|---|---|---|
| FTP | File transfer | TCP 20 (data), 21 (control) |
| TFTP | Simple file transfer | UDP 69 |

- **FTP:** Transfers files between a client and server. Standard FTP does not encrypt credentials or data.
- **TFTP:** A lightweight file transfer protocol with limited functionality and no built-in authentication or encryption.

## 2. Remote Access and Secure Communication

| Protocol | Purpose | Default port |
|---|---|---|
| SSH | Secure remote command-line access | TCP 22 |
| SCP | Secure file copying over SSH | TCP 22 |
| Telnet | Remote terminal access | TCP 23 |

- **SSH:** Provides encrypted remote access.
- **SCP:** Transfers files securely using SSH.
- **Telnet:** Provides remote terminal communication but does not encrypt the session.

**Security distinction:** Prefer SSH over Telnet for remote administration.

## 3. Email Protocols

| Protocol | Purpose | Default port |
|---|---|---|
| SMTP | Sending and relaying email | TCP 25 |
| POP3 | Retrieving email | TCP 110 |
| IMAP | Accessing and managing email on a server | TCP 143 |

- **SMTP:** Used to send email between clients and mail servers or between mail servers.
- **POP3:** Retrieves email, commonly by downloading messages to a client.
- **IMAP:** Synchronises and manages messages while they remain on the mail server.

Encrypted variants commonly use SMTP submission on TCP 587, POP3S on TCP 995 and IMAPS on TCP 993.

## 4. DNS — Domain Name System

| Port | Transport |
|---|---|
| 53 | UDP and TCP |

DNS resolves domain names into information such as IP addresses.

- UDP is commonly used for ordinary DNS queries.
- TCP is also used, including for zone transfers and responses requiring TCP.

DNS is an essential service for locating network resources.

## 5. DHCP — Dynamic Host Configuration Protocol

| Port | Transport |
|---|---|
| 67 | UDP server |
| 68 | UDP client |

DHCP automatically provides network configuration to clients.

Common information includes:
- IP address
- Subnet mask
- Default gateway
- DNS server

### DHCP Reservation

A DHCP reservation associates a particular client identifier, commonly its MAC address, with a specific IP address.

This allows the DHCP server to provide that client with a consistent address.

## 6. HTTP and HTTPS

| Protocol | Default port |
|---|---|
| HTTP | TCP 80 |
| HTTPS | TCP 443 |

- **HTTP:** Used for communication between web clients and servers.
- **HTTPS:** HTTP protected using TLS.

HTTPS provides encryption and server authentication when correctly configured.

## 7. NTP — Network Time Protocol

| Port | Transport |
|---|---|
| 123 | UDP |

NTP synchronises system clocks across networked devices.

Accurate time is important for:
- Log correlation.
- Event timelines.
- Security monitoring.
- Incident investigation.

## 8. SNMP — Simple Network Management Protocol

| Port | Transport |
|---|---|
| 161 | UDP requests and responses |
| 162 | UDP notifications/traps |

SNMP is used to monitor and manage network devices.

It can provide information about device status, interfaces and performance.

Versions:
- SNMPv1: Original version.
- SNMPv2c: Adds improvements but uses community strings without encryption.
- SNMPv3: Supports authentication and privacy features.

## 9. LDAP and LDAPS

| Protocol | Default port |
|---|---|
| LDAP | TCP/UDP 389, depending on operation |
| LDAPS | TCP 636 |

LDAP (Lightweight Directory Access Protocol) provides access to directory services.

It is commonly used for:
- Directory lookups.
- User and group information.
- Centralised identity management.

LDAPS protects LDAP communication using TLS.

## 10. SMB — Server Message Block

| Port | Transport |
|---|---|
| 445 | TCP |

SMB supports file and printer sharing over a network.

It is commonly used in Windows environments for accessing shared folders and network resources.

## 11. Syslog

Syslog is a standard protocol and message format used for logging system and network events.

Common uses:
- Centralised log collection.
- Network device monitoring.
- Troubleshooting.
- Security event analysis.

Commonly used ports:
- UDP 514: Traditional Syslog.
- TCP 514: Syslog over TCP in supported implementations.
- TCP 6514: Syslog over TLS.

## 12. Databases and SQL

A database stores and organises information so applications can retrieve and manage it.

**SQL (Structured Query Language)** is used to work with relational databases.

Examples include:
- Microsoft SQL Server
- MySQL
- PostgreSQL

Microsoft SQL Server commonly uses TCP port 1433 for its default instance.

---

## Quick Port Reference

| Port | Service |
|---:|---|
| 20, 21 | FTP |
| 22 | SSH / SCP |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 67, 68 | DHCP |
| 69 | TFTP |
| 80 | HTTP |
| 110 | POP3 |
| 123 | NTP |
| 143 | IMAP |
| 161, 162 | SNMP |
| 389 | LDAP |
| 443 | HTTPS |
| 445 | SMB |
| 514 | Syslog |
| 1433 | Microsoft SQL Server |

**Note:** These are conventional default ports, not proof that a particular service is running. Services can be configured to use different ports.

## Security and Investigation Relevance

Understanding these protocols helps when:
- Identifying services from network traffic.
- Reviewing firewall and connection logs.
- Investigating remote access.
- Analysing email and file-transfer activity.
- Understanding authentication and directory services.
- Correlating events using accurate timestamps.

A port number alone does not confirm the application or establish malicious activity.

## Learning Reference

- Original handwritten Phase 1 networking notes
- Professor Messer
- Jeremy's IT Lab
