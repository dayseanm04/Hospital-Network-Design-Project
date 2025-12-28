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

| Device Name | Model | Role | Notes |
|-------------|--------|------|-------|
| HS-CORE-R1 | Cisco PT-Router | Main hospital router | Connects to HS-CORE-FW 1 |

### Core Firewall
| Device Name | Model | Role | Notes |
|-------------|--------|------|-------|
| HS-CORE-FW1 | Cisco ASA 5506 | Security/perimeter firewall | Sits between ISP router and the HS-CORE-R1 |

---

# 🏛️ 2. Distribution Layer Devices (Tier 2)

These switches handle routing for VLANs, inter-VLAN connectivity and redundancy.

### Distribution Switches
| Device Name | Model | Role | Notes |
|-------------|--------|------|-------|
| DSW1 | Cisco 3650-24PC | Primary distribution switch | Routing enabled |
| DSW2 | Cisco 3650-24PC | Secondary distribution switch | Routing enabled |

---

# 🏢 3. Access Layer Devices (Tier 3)

These switches connect end devices (PCs, phones and printers) on each floor of the hospital.

### Access Switches

| Device Name | Model | Floor / Purpose | Notes |
|-------------|--------|------------------|-------|
| F1-ASW1 | Cisco 3560-24PC | Floor 1 | Routing enabled |
| F1-ASW2 | Cisco 3560-24PC | Floor 1 | Routing enabled |
| F2-ASW1 | Cisco 3560-24PC | Floor 2 | Routing enabled |
| F2-ASW2 | Cisco 3560-24PC | Floor 2 | Routing enabled |
| F3-AWS1 | Cisco 3560-24PC | Floor 3 | Routing enabled |
| F3-AWS2 | Cisco 3560-24PC | Floor 3 | Routing enabled |
| Service-ASW | Cisco 3560-24PC | Floor 2 | Routing enabled |
