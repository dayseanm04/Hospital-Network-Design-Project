# 📘 Device Inventory – Setup Overview

I will design the network using a Three-Tier Architecture to create a scalable and hierarchical network structure.
This architecture breaks the network into three layers: 

- Core: The high-speed backbone.
- Distribution: Aggregates data and enforces policies.
- Access: Connects end-user devices.

Note: I may be updated some of the devices as the project evolves (When its necessary).

---

# 🧠 1. Core Layer Devices (Tier 1)

### Core Routers

| Device Name | Model | Quantity | Role | Notes |
|-------------|--------|----------|------|-------|
| CORE-RTR1 | Cisco PT-Router | 1 | Main hospital router | Connects to ISP 1 |

---

# 🏛️ 2. Distribution Layer Devices (Tier 2)

These switches handle routing for VLANs, inter-VLAN connectivity and redundancy.

### Distribution Switches
| Device Name | Model | Quantity | Role | Notes |
|-------------|--------|----------|------|-------|
| DIST-SW1 | Cisco 3650-24PC | 1 | Primary distribution switch | Routing enabled |
| DIST-SW2 | Cisco 3650-24PC | 1 | Secondary distribution switch | Routing enabled |

---

# 🏢 3. Access Layer Devices (Tier 3)

These switches connect end devices (PCs, phones and printers) on each floor of the hospital.

### Access Switches
| Device Name | Model | Quantity | Floor / Purpose | Notes |
|-------------|--------|----------|------------------|-------|

