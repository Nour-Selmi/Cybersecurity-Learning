# Subnetting

## Overview

Subnetting is the process of dividing a larger IP network into smaller logical networks called subnets.

It allows network administrators to:

- Organize networks efficiently
- Reduce network traffic
- Improve network performance
- Isolate different types of devices
- Improve security through network segmentation
- Use IP address space more efficiently

Subnetting is an important networking skill for cybersecurity because security controls such as firewalls, ACLs, IDS/IPS, and network segmentation often depend on IP ranges.

---

## Why Do We Need Subnetting?

Imagine a company has one large network:

```text
192.168.1.0/24
```

This network provides 254 usable host addresses.

If the company has different departments, putting everything in the same network may not be ideal.

For example:

Employees
Servers
IoT Devices
Guest Devices
Security Infrastructure

Instead, the network can be divided into smaller subnets:

Employees:   192.168.1.0/26
Servers:     192.168.1.64/26
IoT:         192.168.1.128/26
Guests:      192.168.1.192/26

Each subnet can then have its own security policies and access controls.

---

## IPv4 and Subnetting

IPv4 addresses contain 32 bits.

Example:

192.168.1.10

In binary:

11000000.10101000.00000001.00001010

A subnet mask determines which bits represent the network and which bits represent hosts.

For example:

IP Address:  192.168.1.10
Subnet Mask: 255.255.255.0
CIDR:        /24

The /24 means that the first 24 bits represent the network portion.

Network bits: 24
Host bits:     8
Total bits:   32

----
## CIDR Notation

CIDR stands for Classless Inter-Domain Routing.

CIDR notation represents an IP address followed by a prefix length.

Example:

192.168.1.0/24

The /24 indicates that 24 bits are used for the network portion.

Examples:

10.0.0.0/8
172.16.0.0/16
192.168.1.0/24
192.168.1.0/26

The smaller the prefix number, the larger the network.

For example:

/16 → larger network
/24 → smaller network
/26 → even smaller network
/30 → very small network

----
## Subnet Mask

The subnet mask can be written in two forms:

### CIDR notation
/24
### Dotted-decimal notation
255.255.255.0

Common examples:

CIDR	Subnet Mask
/8	255.0.0.0
/16	255.255.0.0
/24	255.255.255.0
/25	255.255.255.128
/26	255.255.255.192
/27	255.255.255.224
/28	255.255.255.240
/29	255.255.255.248
/30	255.255.255.252

---
## Network Bits and Host Bits

IPv4 contains 32 bits.

The CIDR prefix determines how many bits belong to the network.

For example:

192.168.1.0/24

Means:

Network bits = 24
Host bits    = 8

For:

192.168.1.0/26

We have:

Network bits = 26
Host bits    = 6

For:

192.168.1.0/28

We have:

Network bits = 28
Host bits    = 4

---
## Calculating the Number of Addresses

The number of addresses in a subnet can be calculated using:

2^h

Where h is the number of host bits.

### Example: /24

A /24 has:

32 - 24 = 8 host bits

Therefore:

2^8 = 256 addresses

Usually:

256 total addresses
- 1 network address
- 1 broadcast address
= 254 usable host addresses

---
## Common Subnet Sizes
CIDR	Host Bits	Total Addresses	Usable Hosts
/24	8	256	254
/25	7	128	126
/26	6	64	62
/27	5	32	30
/28	4	16	14
/29	3	8	6
/30	2	4	2

In traditional IPv4 subnetting, the network and broadcast addresses are not assigned to hosts.

---

## Network Address

The network address identifies the subnet itself.

For example:

192.168.1.0/24

The network address is:

192.168.1.0

It represents the entire network.

---

## Broadcast Address

The broadcast address is used to communicate with all hosts on a subnet.

For:

192.168.1.0/24

The broadcast address is:

192.168.1.255

Therefore:

Network:   192.168.1.0
Broadcast: 192.168.1.255

---
## Usable Host Range

The usable host range contains the addresses that can normally be assigned to devices.

For:

192.168.1.0/24

We have:

Network address:   192.168.1.0
First host:        192.168.1.1
Last host:         192.168.1.254
Broadcast:         192.168.1.255

Therefore:

Usable range:
192.168.1.1 – 192.168.1.254

---
## Subnetting Methods

There are two important approaches to understand:

Fixed-Length Subnet Masking (FLSM)
Variable-Length Subnet Masking (VLSM)

---
## FLSM

FLSM stands for Fixed-Length Subnet Masking.

All subnets use the same subnet mask.

For example:

192.168.1.0/24

can be divided into four /26 subnets:

192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26

Each subnet has:

64 total addresses
62 usable host addresses

FLSM is simple but may waste IP addresses when different departments require different numbers of hosts.

---
## VLSM

VLSM stands for Variable-Length Subnet Masking.

It allows different subnets to have different sizes.

For example, suppose a company needs:

Department A → 100 hosts
Department B → 50 hosts
Department C → 20 hosts
Department D → 10 hosts

Instead of giving every department the same subnet size, we can allocate:

Department A → /25
Department B → /26
Department C → /27
Department D → /28

This uses IP addresses more efficiently.

----
## How to Calculate a Subnet

When solving a subnetting problem, determine:

Network address
Broadcast address
First usable host
Last usable host
Number of usable hosts
Subnet mask
### Example 1: 192.168.1.0/24

Given:

Network: 192.168.1.0/24

Host bits:

32 - 24 = 8

Total addresses:

2^8 = 256

Usable hosts:

256 - 2 = 254

Therefore:

Network:     192.168.1.0
First host:  192.168.1.1
Last host:   192.168.1.254
Broadcast:   192.168.1.255
### Example 2: 192.168.1.0/26

Given:

192.168.1.0/26

Host bits:

32 - 26 = 6

Total addresses:

2^6 = 64

Usable hosts:

64 - 2 = 62

The subnet mask is:

255.255.255.192

The subnet ranges are:

192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26

For the first subnet:

Network:     192.168.1.0
First host:  192.168.1.1
Last host:   192.168.1.62
Broadcast:   192.168.1.63

For the second subnet:

Network:     192.168.1.64
First host:  192.168.1.65
Last host:   192.168.1.126
Broadcast:   192.168.1.127

For the third subnet:

Network:     192.168.1.128
First host:  192.168.1.129
Last host:   192.168.1.190
Broadcast:   192.168.1.191

For the fourth subnet:

Network:     192.168.1.192
First host:  192.168.1.193
Last host:   192.168.1.254
Broadcast:   192.168.1.255
### Example 3: 192.168.10.0/27

Given:

192.168.10.0/27

Host bits:

32 - 27 = 5

Total addresses:

2^5 = 32

Usable hosts:

32 - 2 = 30

Subnet mask:

255.255.255.224

The subnets are:

192.168.10.0/27
192.168.10.32/27
192.168.10.64/27
192.168.10.96/27
192.168.10.128/27
192.168.10.160/27
192.168.10.192/27
192.168.10.224/27

For the first subnet:

Network:     192.168.10.0
First host:  192.168.10.1
Last host:   192.168.10.30
Broadcast:   192.168.10.31

----
## The Block Size Method

A quick way to calculate subnets is to determine the block size.

The formula is:

Block Size = 256 - subnet mask value

For example:

/26

has the subnet mask:

255.255.255.192

Therefore:

256 - 192 = 64

The block size is:

64

So the subnet boundaries are:

0
64
128
192
### Example: 192.168.1.70/26

Given:

IP: 192.168.1.70
CIDR: /26

The subnet mask is:

255.255.255.192

Block size:

256 - 192 = 64

The subnet boundaries are:

0
64
128
192

70 falls between 64 and 127.

Therefore:

Network:     192.168.1.64
Broadcast:   192.168.1.127
First host:  192.168.1.65
Last host:   192.168.1.126

----
## Subnetting for Network Segmentation

Subnetting can be used to separate different parts of an organization.

Example:

Company Network
192.168.0.0/24

Could be divided into:

Users:
192.168.0.0/26

Servers:
192.168.0.64/26

IoT:
192.168.0.128/26

Guest:
192.168.0.192/26

This separation allows network administrators to apply different security policies.

For example:

Users → Servers     ALLOW
Users → IoT         DENY
Guest → Servers     DENY
IoT → Internet      ALLOW
IoT → Users         DENY

Subnetting itself does not provide security. Security comes from controls such as firewalls, ACLs, routing policies, and VLANs applied to the networks.

---
## Subnetting and Cybersecurity

Subnetting is highly relevant to cybersecurity.

### 1. Network Scanning

During an authorized security assessment, subnet ranges can be scanned to identify active hosts.

Example:

nmap 192.168.1.0/24

A smaller subnet can also be scanned:

nmap 192.168.1.64/26

Understanding CIDR helps determine exactly which IP addresses are included in a scan.

### 2. Firewall Rules

Firewall rules often use CIDR notation.

Example:

Allow 192.168.10.0/24 → Web Server
Deny  192.168.20.0/24 → Database Server

Understanding subnetting is therefore important when configuring or analyzing firewall rules.

### 3. Network Segmentation

Subnetting can help separate:

Users
Servers
IoT
Guests
Security Systems

This can limit unnecessary communication between systems.

### 4. Attack Surface Analysis

During network reconnaissance, identifying subnet ranges helps security professionals understand:

How large the network is
Which IP ranges are in use
Which hosts belong to different networks
Which systems may be exposed
How the network is segmented
### 5. IDS/IPS Monitoring

IDS/IPS systems can use IP ranges when analyzing network traffic.

For example:

Internal Network:
192.168.10.0/24

Server Network:
192.168.20.0/24

Traffic between these networks can be monitored for suspicious activity.

----
## Practical Linux Commands
### Display IP Addresses
ip addr
### Display Routing Table
ip route
### Test Connectivity
ping 192.168.1.1
### Scan a Subnet with Nmap
nmap 192.168.1.0/24
### Scan a Smaller Subnet
nmap 192.168.1.64/26

----
## Subnetting Cheat Sheet
CIDR	Subnet Mask	Total Addresses	Usable Hosts	Block Size
/24	255.255.255.0	256	254	256
/25	255.255.255.128	128	126	128
/26	255.255.255.192	64	62	64
/27	255.255.255.224	32	30	32
/28	255.255.255.240	16	14	16
/29	255.255.255.248	8	6	8
/30	255.255.255.252	4	2	4

----
## Subnetting Practice
### Exercise 1

Given:

192.168.1.0/26

Find:

Network address
Broadcast address
First usable host
Last usable host
Number of usable hosts
### Exercise 2

Given:

192.168.10.75/27

Find:

Network address
Broadcast address
First usable host
Last usable host
Number of usable hosts
### Exercise 3

Given:

10.10.20.130/28

Find:

Network address
Broadcast address
First usable host
Last usable host
Number of usable hosts
### Exercise 4

A company has the network:

192.168.100.0/24

It needs four separate networks for:

Users
Servers
IoT
Guests

Create four equal-sized subnets.

For each subnet, identify:

Network address
Broadcast address
Usable host range
Number of usable hosts

---
## Key Takeaways
Subnetting divides a network into smaller networks.
IPv4 addresses contain 32 bits.
CIDR notation determines the number of network bits.
The remaining bits are used for hosts.
The number of addresses is calculated using 2^host_bits.
Network and broadcast addresses are normally not assigned to hosts.
FLSM uses the same subnet size for all subnets.
VLSM allows different subnet sizes.
Subnetting is important for network organization and security.
CIDR notation is widely used in Nmap, firewalls, routing, ACLs, and network security.

---
## What I Learned
How subnetting divides an IPv4 network into smaller networks.
How to calculate network and host portions.
How to calculate the number of addresses and usable hosts.
How to identify network and broadcast addresses.
How to use CIDR notation.
How to calculate subnet ranges using the block size method.
The difference between FLSM and VLSM.
How subnetting is used in network segmentation and cybersecurity.

---
## Related Topics
OSI Model
TCP/IP Model
IPv4
VLANs
Routing
ARP
Firewalls
Network Security
