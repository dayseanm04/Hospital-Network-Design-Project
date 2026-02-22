# Packet Tracer Files – Hospital Network Design

## Overview
This folder contains **Cisco Packet Tracer (.pkt) files** that represent different **stages of the Hospital Network Design project**.

---

## Stage 1 – Network Setup

### 📁 `Hospital-Network-Stage1-Setup.pkt`

This file represents the **initial network setup** which includes:

- **Layer 2 & Layer 3 EtherChannels** for link aggregation  
- **Redundancy** between core, distribution, and access layers  
- **Basic OSPF routing** for internal network connectivity  
- **Basic device security**, such as secure access and management setup  
- **VLAN segmentation** and **IP addressing** completed in earlier setup tasks  

This stage focuses on creating a **stable, redundant, and routable foundation** for the hospital network.

## Stage 2 – Services & ISP Integration

### 📁 `Hospital-Network-Stage2-changes.pkt`

This stage builds on the foundational network setup from Stage 1 by introducing **core network services** and **ISP connectivity**.

### 🔧 Key Additions
- Configured **DHCP, SYSLOG, and NTP** for the hospital LAN  
- I Setup **ISP1 and ISP2** and configured Layer 3 **Port-Channels** and IP addressing 
- Deployed an additional **core firewall** for improved redundancy
- Added **internet servers** (DNS, Web, NTP) connected to INET-SW which is connected to ISP1
- Configured **NAT** to allow the internet services to be reachbbly by the hospital lan

Stage 2 focuses on integrating **ISPs and internet services** while preparing the network for internet connectivity.
