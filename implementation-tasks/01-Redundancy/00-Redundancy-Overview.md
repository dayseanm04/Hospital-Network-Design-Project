# 🔁 01 – Redundancy Overview

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

