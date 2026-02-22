# Set Up Core Firewall to Distribution Connections

## Overview
This task establishes the **Layer 3 backbone connections** between:

- **HS-CORE-FW1 ↔ DSW1**
- **HS-CORE-FW2 ↔ DSW2**

Each connection uses a **static Layer 3 Port-Channel (Po20)** with /30 addressing to provide redundancy and high-speed routing between the core and distribution layers.

### Reference Topology

<img width="775" height="399" alt="topology" src="https://github.com/user-attachments/assets/5e6a837f-9f18-4623-8039-2d2279c558ca" />

---

# HS-CORE-FW1 ↔ DSW1 Connection

## Physical Interfaces

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| HS-CORE-FW1 | G1/3 | DSW1 | G1/1/1 |
| HS-CORE-FW1 | G1/4 | DSW1 | G1/1/4 |

## Subnet 

| Link               | Subnet        |  HS-CORE-FW1 IP  |  DSW1 IP   |
| ------------------ | ------------- | ---------------- | ----------------- |
| HS-CORE-FW1 ↔ DSW1 | 10.255.0.0/30 |    10.255.0.1    |     10.255.0.2    |

---

# HS-CORE-FW2 ↔ DSW2 Connection

## Physical Interfaces

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| HS-CORE-FW2 | G1/3 | DSW2 | G1/1/1 |
| HS-CORE-FW2 | G1/4 | DSW2 | G1/1/4 |

## Subnet 

| Link               | Subnet        |  HS-CORE-FW2 IP  |  DSW2 IP   |
| ------------------ | ------------- | ---------------- | ----------------- |
| HS-CORE-FW2 ↔ DSW2 | 10.255.0.4/30 |    10.255.0.5    |     10.255.0.6    |

## Click [`here`](/implementation-tasks/01-Redundancy/) to view the PortChannel configurations
