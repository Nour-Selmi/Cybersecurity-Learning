#  TCP/IP Model

##  Overview

The TCP/IP model is a networking model used to describe how devices
communicate over a network.

Unlike the OSI model, which has seven layers, the TCP/IP model is
commonly represented using **four layers**.

---

##  The 4 Layers

| Layer | Name | Main Function | Examples |
|---|---|---|---|
| 4 | Application | Provides network services to applications | HTTP, HTTPS, DNS, FTP, SSH |
| 3 | Transport | Provides end-to-end communication | TCP, UDP |
| 2 | Internet | Handles addressing and routing | IP, ICMP |
| 1 | Network Access | Handles communication over the local network | Ethernet, Wi-Fi, ARP |

---

##  TCP/IP Communication

When a device sends data, the data moves down through the TCP/IP layers:

**Application → Transport → Internet → Network Access**

At the receiving device, the process is reversed:

**Network Access → Internet → Transport → Application**

---

##  TCP vs UDP

### TCP

TCP is connection-oriented and provides reliable data transmission.

It includes mechanisms such as:

- Connection establishment
- Sequencing
- Acknowledgments
- Retransmission
- Flow control

Examples of protocols that commonly use TCP:

- HTTP/HTTPS
- SSH
- FTP

### UDP

UDP is connectionless and does not provide the same reliability mechanisms
as TCP.

It is generally faster and has lower overhead.

Examples:

- DNS
- DHCP
- VoIP
- Streaming applications

---

##  Security Perspective

Understanding TCP/IP is essential for cybersecurity because many
security tools and attacks rely on network communication.

### Examples

**Nmap**

Can be used to discover open ports and identify services.

**Wireshark**

Can be used to capture and analyze network traffic.

**Firewalls**

Can filter network traffic based on parameters such as:

- Source IP
- Destination IP
- Port
- Protocol

---


## TCP/IP and OSI
The TCP/IP model and OSI model are not identical, but they can be
mapped approximately:

| TCP/IP Model | OSI Model|
|---|---|
| Application | Application | 
| Application| Presentation |
| Application | Session |
| Transport |Transport |
| Internet |Network |
| Network Access |Data Link |
| Network Access |Physical |

---
## Key Takeaways
- TCP/IP is a fundamental model for understanding network communication.
- TCP provides reliable, connection-oriented communication.
- UDP provides faster, connectionless communication.
- IP is responsible for logical addressing and routing.
- Understanding TCP/IP is essential for network security and penetration testing.
 ---
## What I Learned
-The four layers of the TCP/IP model.
-The difference between TCP and UDP.
-How IP and TCP work together.
-How networking concepts are connected to cybersecurity tools such as Nmap and Wireshark.



