# Redundancy – Hospital Network Design

## Overview
The **Redundancy** folder documents how **high availability and fault tolerance** are implemented in the Hospital Network Design project.

Healthcare networks must remain operational at all times.  
This section focuses on eliminating **single points of failure** by using **EtherChannel (LACP)**, **layered redundancy**, and **parallel paths** across the **core, distribution, and access layers**.

All configurations follow **enterprise networking best practices** and are designed for **scalability, resiliency, and uptime**.

---

## Goals of Redundancy

- ✅ Ensure continuous network availability  
- ✅ Increase bandwidth using bundled links  
- ✅ Provide automatic failover if a link fails  
- ✅ Support mission-critical hospital services  
- ✅ Align with a **three-tier network architecture**

---

## Design Highlights

- **LACP (IEEE 802.3ad)** used for link aggregation
- Increased throughput by bundling multiple physical links
- Automatic failover if a link goes down
- Built to support hospital-critical systems (EMR, servers, etc)
- Fully integrated with the **core, distribution, and access layers**
