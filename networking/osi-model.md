#  OSI Model

##  Overview

The OSI (Open Systems Interconnection) model is a conceptual framework
used to understand how network communication works.

It divides network communication into **7 layers**, with each layer
having a specific role.

---

##  The 7 Layers

| Layer | Name | Main Function | Examples |
|---|---|---|---|
| 7 | Application | Provides network services to applications | HTTP, HTTPS, DNS, FTP |
| 6 | Presentation | Data formatting, encryption, compression | SSL/TLS, JPEG, JSON |
| 5 | Session | Establishes and manages communication sessions | RPC, NetBIOS |
| 4 | Transport | End-to-end communication and reliability | TCP, UDP |
| 3 | Network | Logical addressing and routing | IP, ICMP, Routers |
| 2 | Data Link | Frames, MAC addressing, local delivery | Ethernet, ARP, Switches |
| 1 | Physical | Transmits raw bits over the physical medium | Cables, Fiber, Radio |

---

##  Data Flow

When data is sent over a network, it moves from:

**Application → Presentation → Session → Transport → Network → Data Link → Physical**

At the receiving side, the process is reversed:

**Physical → Data Link → Network → Transport → Session → Presentation → Application**

---

##  Security Perspective

Understanding the OSI model is important in cybersecurity because
different attacks and security controls can operate at different layers.

### Layer 7 — Application

Examples:

- Cross-Site Scripting (XSS)
- SQL Injection
- Broken Access Control
- API vulnerabilities

Common security tools:

- Burp Suite
- OWASP ZAP

### Layer 4 — Transport

Security concepts include:

- TCP connections
- Port scanning
- TLS over TCP

Example tool:

- Nmap

### Layer 3 — Network

Security concepts include:

- IP addressing
- Routing
- Packet filtering
- Network reconnaissance

Examples:

- Firewalls
- IDS/IPS

### Layer 2 — Data Link

Security concepts include:

- MAC addresses
- ARP
- VLANs
- ARP spoofing

---

##  Practical Example

When I access:

`https://example.com`

the communication can be understood through the OSI model:

1. **Application:** HTTP/HTTPS is used to request the webpage.
2. **Transport:** TCP provides reliable communication.
3. **Network:** IP handles addressing and routing.
4. **Data Link:** Ethernet or Wi-Fi handles local network communication.
5. **Physical:** Data is transmitted as electrical, optical, or radio signals.

---

##  Key Takeaways

- The OSI model contains **7 layers**.
- Each layer has a specific responsibility.
- The model helps understand how network communication works.
- It is useful for troubleshooting and cybersecurity.
- Many security attacks and defensive mechanisms can be mapped to
  different OSI layers.

---

##  What I Learned

- How the seven OSI layers interact.
- The difference between TCP and IP responsibilities.
- How protocols are associated with different layers.
- Why understanding networking fundamentals is important for cybersecurity.
