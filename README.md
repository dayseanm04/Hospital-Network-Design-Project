# Hospital Network Design Project

## Reference Toplogy

<img width="1034" height="629" alt="toplogy" src="https://github.com/user-attachments/assets/5ee324f3-8d54-45f6-9cbf-4264a7588f7d" />
<img width="975" height="298" alt="2" src="https://github.com/user-attachments/assets/3a2ee9ea-95d3-44bc-a49d-231fb042781d" />


## Project Overview

This project is a large-scale enterprise hospital network designed and implemented using Cisco Packet Tracer to simulate a real-world production environment supporting approximately **500 users**.

The network follows a **Three-Tier Hierarchical Architecture (Access, Distribution, Core)** and is engineered with a strong focus on:

- Redundancy and High Availability  
- Network Segmentation using VLANs and VLSM  
- Dynamic Routing with OSPF  
- Enterprise Service Deployment (DHCP, NTP, DNS, SYSLOG)  
- Secure Device Management  
- Structured Testing and Troubleshooting  

---

## Project Goals

- Design a scalable hospital network architecture  
- Segment departments using VLANs and structured IP addressing  
- Implement redundancy for high availability  
- Secure the entire network using layered security controls  
- Verify functionality through structured testing  
- Document all decisions and configurations  

---

## Network Architecture

### Access Layer

- Two access switches per floor (e.g., `F1-ASW1`, `F1-ASW2`).
- End-user devices (PCs, printers) connect at this layer
- Layer 2 EtherChannels between same-floor switches
- Layer 3 EtherChannels to Distribution switches
- 10+ VLANs configured for departmental segmentation
- HSRP configured for redundant default gateways
- Port Security enabled on access ports

Note there are multuple users per floor, I used 2 Access switches per floor for demostratation.

---

### Distribution Layer

- Two distribution switches (`DSW1`, `DSW2`)
- Layer 3 EtherChannel between distribution switches
- Redundant Layer 3 EtherChannels to Core Firewalls
- OSPF configured for dynamic routing

---

### Core Layer

- Two core firewalls (`HS-CORE-FW1`, `HS-CORE-FW2`)
- Redundant Layer 3 EtherChannels to Edge Routers
- High-availability backbone design

---

### Edge Layer

- Two edge routers (`HS-EDGE-R1`, `HS-EDGE-R2`)
- Layer 3 EtherChannel between edge routers
- PAT (NAT Overload) configured using standard Named ACLs
- Simulated Internet connectivity

---

## Internal Services Deployed

A dedicated internal services segment hosts:

- DHCP Server
- NTP Server
- DNS Server
- Syslog Server

### Service Implementation Details

- Static IP addressing for servers and IT Department
- DHCP pools configured per VLAN
- HSRP integrated with DHCP default gateway design
- Centralized logging to Syslog server
- NTP synchronization across all network devices

---

## Security Implementations

- SSH-only remote device management
- Local authentication configured
- Standard ACL restricting management access to IT Department devices
- VLAN-based network segmentation
- Port Security on access switches
- Loopback interfaces configured for routing stability and management

---

## Redundancy & High Availability Design

- Layer 2 and Layer 3 EtherChannels throughout the network
- HSRP for gateway redundancy
- Dual Distribution switches
- Dual Core Firewalls
- Dual Edge Routers
- Dynamic routing using OSPF

The design minimizes single points of failure and reflects enterprise-grade network engineering practices.

---

## Testing & Troubleshooting

Comprehensive validation and troubleshooting performed, including:

- Endpoint-to-Gateway connectivity testing
- Inter-VLAN routing verification
- Internet reachability testing
- Service validation (DHCP, NTP, DNS, SYSLOG)
- OSPF adjacency troubleshooting (EXSTART state, area mismatch)
- Packet loss and routing issue troubleshooting and resolution

---


## 📂 Project Structure

| Folder / File | Purpose |
|--------------|---------|
| 📁 **[`design/`](./design)** | Network planning, requirements, VLAN design, and IP addressing |
| 📁 **[`docs/`](./docs)** | Reference documents used throughout the project |
| 📁 **[`setup/`](./setup)** | Initial device and network setup tasks |
| 📁 **[`implementation-tasks/`](./implementation-tasks)** | Core network implementation tasks |
| 📁 **[`Network-Security/`](./Network-Security)** | Hospital Network security tasks |
| 📁 **[`testing/`](./testing)** | Connectivity, security, and validation tests |
| 📁 **[`troubleshooting/`](./troubleshooting)** | Issue identification and resolution documentation |
| 📁 **[`change-log/`](./change-log)** | Tracks configuration changes and updates |
| 📁 **[`packet-tracer-files/`](./packet-tracer-files)** | Cisco Packet Tracer project files |
| 📁 **[`skip/`](./skip)** | Skipped steps |
| 📄 **[`Project-Overview.md`](./Project-Overview.md)** | High-level explanation of the project |
