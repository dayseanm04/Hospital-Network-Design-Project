# 04 Configure Trunk Links.md

## 🎯 Goal
Configure all **uplink interfaces** as **802.1Q trunk links** between:
- Access Switches (F1/F2/F3) ↔ Distribution Switches (DSW1/DSW2)
- DSW1 ↔ DSW2

## ✅ Standard Trunk Configuration Pattern (don’t repeat full commands)
Use this pattern for **each interface range** in the tables below:

1️⃣ Enter interface range config mode  
- `interface range [INTERFACE_RANGE]`

2️⃣ Configure as trunk  
- `switchport mode trunk`

---

## 🧱 Part A — Access Switch Uplinks (ASW → DSW)

### 🔌 Trunk Interfaces to Configure (on EVERY Access Switch)
All Access Switches use the same trunk uplink range: **G1/0/21 – G1/0/24**

| Device | Interface Range to Trunk |
|---|---|
| F1-ASW1 | `G1/0/21 - G1/0/24` |
| F1-ASW2 | `G1/0/21 - G1/0/24` |
| F2-ASW1 | `G1/0/21 - G1/0/24` |
| F2-ASW2 | `G1/0/21 - G1/0/24` |
| F3-ASW1 | `G1/0/21 - G1/0/24` |
| F3-ASW2 | `G1/0/21 - G1/0/24` |

### 📝 Uplink Mapping Notes (important)
| Access Switch Uplink Interfaces | Connected To |
|---|---|
| `G1/0/23 - G1/0/24` | DSW1 |
| `G1/0/21 - G1/0/22` | DSW2 |

