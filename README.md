# Enterprise-Network-Infrastructure-Lab-v1

## Overview
This project is a complete Enterprise Network simulation built in Cisco Packet Tracer.

The lab demonstrates VLAN segmentation, Inter-VLAN Routing using Layer 3 Switches, dynamic routing with EIGRP, DHCP services, ACL-based security, NAT, Internet simulation, and routing redundancy.

The network was designed to simulate a small-to-medium enterprise environment with multiple departments distributed across different Layer 3 switches.

---

# Network Topology
![Topology](topology.png)

## Core Components
- 3 Layer 3 Switches
- 2 Enterprise Routers
- 1 Internet Router
- Multiple VLANs and departmental networks
- DHCP Server
- Finance Server
- Database Server

---

# Technologies Used

- VLANs
- Inter-VLAN Routing
- Layer 3 Switching
- EIGRP Dynamic Routing
- ACL (Access Control Lists)
- DHCP
- NAT Overload (PAT)
- Routing Redundancy
- Cisco Packet Tracer

---

# VLAN Structure

## L3-SW1
| VLAN | Department | Network |
|---|---|---|
| VLAN 10 | HR | 192.168.10.0/24 |
| VLAN 20 | IT | 192.168.20.0/24 |
| VLAN 30 | Guest | 192.168.30.0/24 |
| VLAN 40 | Finance | 192.168.40.0/24 |
| VLAN 50 | Admin | 192.168.50.0/24 |

---

## L3-SW2
| VLAN | Department | Network |
|---|---|---|
| VLAN 10 | HR | 192.168.110.0/24 |
| VLAN 20 | IT | 192.168.120.0/24 |
| VLAN 30 | Guest | 192.168.130.0/24 |
| VLAN 40 | Finance | 192.168.140.0/24 |
| VLAN 50 | Admin | 192.168.150.0/24 |

---

## L3-SW3
| VLAN | Department | Network |
|---|---|---|
| VLAN 10 | HR | 192.168.210.0/24 |
| VLAN 20 | IT | 192.168.220.0/24 |
| VLAN 30 | Guest | 192.168.230.0/24 |
| VLAN 40 | Finance | 192.168.240.0/24 |
| VLAN 50 | Admin | 192.168.250.0/24 |

---

# Routing Design

## Router A Connections
| Connection | Network |
|---|---|
| RouterA ↔ L3-SW1 | 10.0.1.0/30 |
| RouterA ↔ L3-SW2 | 10.0.2.0/30 |
| RouterA ↔ L3-SW3 | 10.0.3.0/30 |
| RouterA ↔ Internet Router | 20.0.0.0/30 |

---

## Router B Connections
| Connection | Network |
|---|---|
| RouterB ↔ L3-SW1 | 10.0.11.0/30 |
| RouterB ↔ L3-SW2 | 10.0.12.0/30 |
| RouterB ↔ L3-SW3 | 10.0.13.0/30 |
| RouterB ↔ Internet Router | 30.0.0.0/30 |

---

# Dynamic Routing

EIGRP was configured across all routers and Layer 3 switches to provide:
- Dynamic route exchange
- Automatic failover
- Redundancy between Router A and Router B

---

# DHCP Services

A centralized DHCP Server was configured to dynamically assign IP addresses to hosts across all VLANs.

---

# Security Features

## ACL Implementation

Access Control Lists (ACLs) were configured to secure internal servers and control communication between VLANs.

### Implemented Policies
- Only authorized VLANs can access the Finance Server
- Database Server access is restricted to:
  - HR VLAN
  - IT VLAN on L3-SW2
  - IT VLAN on L3-SW1
- Unauthorized VLANs are denied access to protected servers

---

# NAT Configuration

NAT Overload (PAT) was implemented on Router A and Router B to provide simulated Internet access through the Internet Router.

---

# Internet Simulation

The Internet Router simulates external connectivity using:
- Loopback Interface: `8.8.8.8`

Hosts inside the enterprise network can successfully reach the simulated Internet using NAT.

---

# Redundancy

The network includes routing redundancy using:
- Dual edge routers
- EIGRP failover paths

If one router fails, traffic is automatically redirected through the backup router.

---

# Project Goals

- Build a scalable enterprise network
- Practice Layer 3 switching
- Implement dynamic routing
- Configure VLAN segmentation
- Apply network security using ACLs
- Implement NAT and Internet access
- Simulate routing redundancy

---

# Files Included

- Enterprise-Network-Lab.pkt
- README.md
- Topology Screenshot

---

# Conclusion

This project demonstrates a complete enterprise-style network infrastructure with routing, segmentation, redundancy, and security features.

It reflects practical CCNA-level networking and infrastructure design skills.
