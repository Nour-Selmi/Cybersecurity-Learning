#  TCP/IP Model

##  Overview

The TCP/IP (Transmission Control Protocol / Internet Protocol) model is a framework used to understand how devices communicate over a network.

It is the foundation of modern networking and the Internet.

Unlike the OSI model, which contains seven layers, the TCP/IP model is commonly represented using four layers.

---

##  The Four Layers of the TCP/IP Model

| Layer | Function | Examples |
|---------|------------|------------|
| Application | Provides services to applications | HTTP, HTTPS, DNS, FTP, SSH |
| Transport | Handles end-to-end communication | TCP, UDP |
| Internet | Handles addressing and routing | IP, ICMP |
| Network Access | Handles local network communication | Ethernet, Wi-Fi, ARP |

---

##  How Data Travels

When a user accesses a website:

```text
Application Layer
        ↓
Transport Layer
        ↓
Internet Layer
        ↓
Network Access Layer
```

At the receiving device, the process is reversed.

---

##  TCP vs UDP

### TCP (Transmission Control Protocol)

TCP is connection-oriented and reliable.

Features:

- Three-way handshake
- Sequencing
- Acknowledgments
- Retransmission
- Flow control

Examples:

- HTTP
- HTTPS
- SSH
- FTP

### UDP (User Datagram Protocol)

UDP is connectionless and faster.

Examples:

- DNS
- DHCP
- Streaming
- VoIP

---

##  Cybersecurity Perspective

Understanding TCP/IP is essential in cybersecurity because many attacks and security tools rely on network communication.

Examples:

### Nmap

Can identify:

- Open ports
- Running services
- Operating systems

Example:

```bash
nmap 192.168.1.10
```

### Wireshark

Can capture and analyze packets.

Example information:

- Source IP
- Destination IP
- Protocol
- Port numbers

### Firewalls

Firewalls can filter traffic based on:

- IP addresses
- Ports
- Protocols

---

##  Practical Example

When visiting:

https://example.com

The communication may look like:

```text
Browser
   ↓
HTTPS
   ↓
TCP
   ↓
IP
   ↓
Ethernet / Wi-Fi
```

Each layer has a specific responsibility.

---

##  Relationship with the OSI Model

| OSI Model | TCP/IP Model |
|------------|-------------|
| Application | Application |
| Presentation | Application |
| Session | Application |
| Transport | Transport |
| Network | Internet |
| Data Link | Network Access |
| Physical | Network Access |

---

##  Key Takeaways

- TCP/IP contains four layers.
- TCP provides reliable communication.
- UDP provides faster communication.
- IP is responsible for addressing and routing.
- Understanding TCP/IP is important for networking and cybersecurity.

---

##  What I Learned

- The four layers of the TCP/IP model.
- The difference between TCP and UDP.
- How devices communicate over networks.
- Why TCP/IP knowledge is important in cybersecurity.
---
##  Related Topics

- [OSI Model](osi-model.md)
