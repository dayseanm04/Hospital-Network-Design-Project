# Hospital Network Design Project

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

---

## 🧠 Design 

- Three-tier architecture (core, distribution, access)
- Department-based VLAN segmentation
- Structured and scalable IP addressing
- Redundant links using EtherChannel
- Network security enforcement

---

## 🔐 Security Focus
Security is applied **across the entire network**, including:
- Device access protection
- Traffic control using ACLs
- Secure management access
- Segmentation between departments

I will add additional security features as the project evolves.

---

## 🧪 Testing & Validation

Testing is organized into dedicated categories to verify that the hospital network operates correctly, securely, and reliably.

The testing phase validates **redundancy, failover behavior, security controls, and end-to-end connectivity** across the entire network. 
