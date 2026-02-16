# 🔗 Set Up Edge Routers to Core Firewall Connections

## 📌 Overview
This task establishes the **Layer 3 backbone connections** between:

- **HS-EDGE-R1 ↔ HS-CORE-FW1**
- **HS-EDGE-R2 ↔ HS-CORE-FW2**

Each connection uses a **static Layer 3 Port-Channel** with /30 addressing to provide redundancy.

### Reference Topology

<img width="567" height="244" alt="topology" src="https://github.com/user-attachments/assets/6bd8a4c8-f1fa-490d-8d3d-59955db3156e" />

---


# 🧱 HS-EDGE-R1 ↔ HS-CORE-FW1 Connection

## 🔌 Physical Interfaces

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| HS-EDGE-R1 | G1/1/3 | HS-CORE-FW1 | G1/1 |
| HS-EDGE-R1 | G1/1/4 | HS-CORE-FW1 | G1/2 |

---

# 🧱 HS-EDGE-R2 ↔ HS-CORE-FW2 Connection


## 🔌 Physical Interfaces

| Device     | Interface | Connected To | Interface |
| ---------- | --------- | ------------ | --------- |
| HS-EDGE-R2 | G1/1/3    | HS-CORE-FW2  | G1/1      |
| HS-EDGE-R2 | G1/1/4    | HS-CORE-FW2  | G1/2      |


## Click [**`here`**](/implementation-tasks/01-Redundancy/) to view the PortChannel configuration
