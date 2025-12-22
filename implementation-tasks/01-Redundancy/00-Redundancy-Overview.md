# 🔁 Redundancy Overview

This document explains how **redundancy** is implemented across the
**access, distribution, and core layers** of the hospital network.

The goal of this design is to **eliminate single points of failure** and ensure
continuous connectivity for critical hospital services.

---

## 🏗️ Redundancy Design Summary

The hospital network follows a **hierarchical campus design** with redundancy
built into each layer:

- Redundant uplinks at the **Access layer**
- Dual Distribution Switches
- Redundant paths from Distribution to the **Core Router (HS-CORE-R1)**

This layered approach ensures the network can tolerate **link failures** and
**device failures** without service interruption.

---

## Reference Diagram

<img width="599" height="389" alt="implement-LACP" src="https://github.com/user-attachments/assets/25fe182f-1201-409c-b9c5-b48ee968a709" />


## 🔗 Access Layer Redundancy (ASW → DSW)

Each **Access Switch (ASW)** is connected to the Distribution layer using
**four uplinks**:

- **Two links to DSW1**
- **Two links to DSW2**

The links connected to the same Distribution Switch are bundled using
**LACP EtherChannel**.

### 📊 Access Uplink Design

| Component | Design Detail |
|---------|---------------|
| Uplinks per ASW | 4 total |
| Links to DSW1 | 2 |
| Links to DSW2 | 2 |
| Link bundling | LACP EtherChannel |
| Purpose | Redundancy + increased bandwidth |

**LACP EtherChannel** allows:
- Multiple physical links to act as one logical link
- Automatic failover if a physical link goes down

---

## 🔁 Distribution Layer Redundancy (DSW1 ↔ DSW2)

The network uses **two Distribution Switches (DSW1 and DSW2)**.

Because each Access Switch connects to **both** distribution switches:

- The Access layer never depends on a single Distribution Switch
- Traffic can dynamically use either DSW

### 📉 Distribution Failure Scenarios

| Scenario | Result |
|--------|--------|
| One ASW uplink fails | Traffic continues on remaining links |
| One EtherChannel member fails | EtherChannel remains operational |
| Entire DSW1 fails | ASWs continue via DSW2 |
| Entire DSW2 fails | ASWs continue via DSW1 |

---

## 🔁 Distribution-to-Distribution (DSW ↔ DSW) Redundancy

Redundancy is also implemented **between the Distribution Switches themselves**.

**DSW1 and DSW2 are interconnected using two physical links**.  
These links provide an additional redundant path at the distribution layer and
support east–west traffic between VLANs and access switches.

### 📊 Inter-Distribution Link Design

| Component | Design Detail |
|---------|---------------|
| Devices | DSW1 ↔ DSW2 |
| Physical links | 2 |
| Future configuration | Layer 3 EtherChannel |

I will implement Layer 3 ethechannel for the interconnection between  DSW1 and DSW2 to avoid Layer 2 loops, reduce STP complexity, and improve stability

### 📉 Distribution Failure Scenarios

| Scenario | Result |
|--------|--------|
| DSW1 interface connected to HS-CORE-R1 fails | Traffic will be sent to DSW2 via the layer 3 etherchannel |
| DSW2 interface connected to HS-CORE-R1 fails | Traffic will be sent to DSW1 via the layer 3 etherchannel |

### 🧠 Design reasons

- Provides **distribution-layer resiliency**
- Allows traffic to traverse the distribution layer even during failures
- LACP bundles the two links into a single logical Port-Channel for:
  - Increased bandwidth  
  - Faster recovery if one link fails  

---

## 🧠 Core Layer Redundancy (DSW → HS-CORE-R1)

Redundancy is also implemented at the **core layer**.

Both **DSW1 and DSW2** are independently connected to the
**Hospital Core Router (HS-CORE-R1)**.

This ensures that the core router remains reachable even if one
Distribution Switch becomes unavailable.

### 🔗 Core Connectivity Design

| Component | Design Detail |
|---------|---------------|
| Core device | HS-CORE-R1 |
| Distribution switches | DSW1 and DSW2 |
| Connectivity | Each DSW has a direct link to HS-CORE-R1 |
| Single point of failure | Eliminated at distribution-to-core path |

### 📉 Core Failure Scenarios

| Scenario | Network Impact |
|--------|----------------|
| One DSW-to-core link fails | Traffic continues over remaining path |
| DSW1 fails completely | Traffic routes through DSW2 to HS-CORE-R1 |
| DSW2 fails completely | Traffic routes through DSW1 to HS-CORE-R1 |

---

# ✅ End-to-End Redundancy Summary

- Access Switches use **four redundant uplinks**
- Uplinks are bundled with **LACP EtherChannel**
- Two Distribution Switches provide path diversity
- Both Distribution Switches connect to **HS-CORE-R1**
- Failure of a link or a single distribution switch **does not interrupt connectivity**
- Redundancy exists at:
  - **Access → Distribution**
  - **Distribution → Core**

This design provides a **resilient and fault-tolerant network** suitable for a hospital environment.
