# 🔁 Configure Backbone L3 Port-Channels for Redundancy

## 📌 Overview
This task, I will implements**Layer 3 static Port-Channels** across the hospital backbone to provide:

- High availability
- Increased bandwidth
- Redundant routing paths

The backbone includes:
- Edge Routers
- Core Firewalls
- Distribution Switches

---

## 🧱 Backbone Interconnections

The following Layer 3 Port-Channels form the redundant backbone:

| Connection | Port-Channel | Subnet |
|------------|-------------|--------|
| HS-EDGE-R1 ↔ HS-CORE-FW1 | Po1 | 10.200.0.0/30 |
| HS-EDGE-R2 ↔ HS-CORE-FW2 | Po1 | 10.200.0.4/30 |
| HS-CORE-FW1 ↔ DSW1 | Po20 | 10.255.0.0/30 |
| HS-CORE-FW2 ↔ DSW2 | Po20 | 10.255.0.4/30 |
| HS-EDGE-R1 ↔ HS-EDGE-R2 | Po10 | 10.150.0.0/30 |

---


# 🧱 1️⃣ Edge ↔ Core Redundant Links

## 🔷 HS-EDGE-R1 ↔ HS-CORE-FW1

#### On HS-EDGE-R1 in global config mode:

```bash
interface range g1/1/3-4
 no switchport
 channel-group 1 mode on
```

#### On HS-CORE-FW1 in global config mode:

```bash
interface g1/1
 channel-group 1 mode on
interface g1/2
 channel-group 1 mode on
```

## 🔷 HS-EDGE-R2 ↔ HS-CORE-FW2
