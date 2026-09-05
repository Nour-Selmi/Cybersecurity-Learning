#  IPv4

##  Overview

IPv4 (Internet Protocol version 4) is a network-layer protocol used to identify devices and route packets across networks.

An IPv4 address is a 32-bit number divided into four 8-bit sections called octets.

Example:

192.168.1.10

Each octet can have a value from 0 to 255.

---

##  IPv4 Address Structure

An IPv4 address contains:

- Network portion
- Host portion

For example:

192.168.1.10/24

With a `/24` prefix:

- Network: 192.168.1.0
- Host: 10
- Broadcast: 192.168.1.255
- Usable hosts: 192.168.1.1 – 192.168.1.254

---

##  IPv4 Address Classes

Historically, IPv4 addresses were divided into five classes:

| Class | Range | Typical Use |
|-------|-------|-------------|
| A | 1.0.0.0 – 126.255.255.255 | Large networks |
| B | 128.0.0.0 – 191.255.255.255 | Medium networks |
| C | 192.0.0.0 – 223.255.255.255 | Small networks |
| D | 224.0.0.0 – 239.255.255.255 | Multicast |
| E | 240.0.0.0 – 255.255.255.255 | Experimental |

> Modern networks use CIDR instead of relying on traditional address classes.

---

##  Private IPv4 Addresses

Private addresses are used inside local networks and are not directly routable on the public Internet.

The main private ranges are:

- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

Examples:

```text
10.0.0.5
172.16.10.20
192.168.1.10

These addresses are commonly used for:

Home networks
Enterprise networks
Servers
IoT devices
Internal network infrastructure
```
---
## Public IPv4 Addresses

Public IPv4 addresses are globally routable addresses used to communicate across the Internet.

Example:

8.8.8.8

Public IP addresses are generally assigned by Internet Service Providers or organizations responsible for Internet address allocation.

---

## Static vs Dynamic IP
Static IP

A static IP address remains assigned to a device.

Common uses:

Servers
Network devices
Firewalls
Security infrastructure
Dynamic IP

A dynamic IP address can change over time.

It is commonly assigned using DHCP.

 Special IPv4 Addresses
Loopback
127.0.0.1

Used by a device to communicate with itself.

Example:

ping 127.0.0.1
Default Route
0.0.0.0/0

Represents the default route used when no more specific route exists.

Limited Broadcast
255.255.255.255

Used to broadcast traffic to devices on the local network.

---

## Subnet Mask

A subnet mask determines which part of an IPv4 address represents the network and which part represents the host.

Example:

IP Address:  192.168.1.10
Subnet Mask: 255.255.255.0
CIDR:        /24

This means:

Network: 192.168.1.0
Host:     10

---
## CIDR Notation

CIDR (Classless Inter-Domain Routing) represents the network prefix using /number.

Examples:

192.168.1.0/24
10.0.0.0/8
172.16.0.0/16

The number indicates how many bits belong to the network portion.

For example:

/24 = 24 network bits
     = 8 host bits

A /24 network provides:

2^8 = 256 total addresses

Usually:

254 usable host addresses

because one address is used for the network and one for broadcast.

---

## IPv4 and Cybersecurity

Understanding IPv4 is essential for cybersecurity.

1. Network Scanning

Tools such as Nmap use IP addresses to discover hosts and services.

Example:

nmap 192.168.1.0/24

This scans the hosts in the network.

2. Firewall Rules

Firewalls use IP addresses to control network traffic.

Example:

Allow: 192.168.1.0/24 → Web Server
Deny:  10.0.0.0/8 → Database Server
3. Network Segmentation

Different IP networks can be used to separate systems.

Example:

Users Network: 192.168.10.0/24
Server Network: 192.168.20.0/24
IoT Network: 192.168.30.0/24

This can reduce the impact of a compromised device.

4. Reconnaissance

During authorized security assessments, identifying IP addresses helps determine:

Network ranges
Active hosts
Exposed services
Network architecture
 Practical Commands
Check your IP address on Linux
ip addr
Display routing information
ip route
Test connectivity
ping 192.168.1.1
Scan a network with Nmap
nmap 192.168.1.0/24
 Example

Consider:

IP:      192.168.10.25
CIDR:    /24

The network is:

192.168.10.0/24

The broadcast address is:

192.168.10.255

Usable host range:

192.168.10.1 – 192.168.10.254

---
## What I Learned
-IPv4 uses 32-bit addresses. </br>
-An IPv4 address contains four octets.</br>
-Private and public IP addresses have different purposes.</br>
-Subnet masks separate network and host portions.</br>
-CIDR notation represents network prefixes.</br>
-IP addressing is important for scanning, routing, firewall rules, and network segmentation.</br>
