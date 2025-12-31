# 🔗 Configure L2 LACP EtherChannel for Access Switch Interconnections (ASW ↔ ASW)

**Goal:** Configure **Layer 2 LACP EtherChannels** between each access switches on every floor:
- **F1-ASW1 ↔ F1-ASW2**
- **F2-ASW1 ↔ F2-ASW2**
- **F3-ASW1 ↔ F3-ASW2** 

## Refernce Netork Diagram

<img width="551" height="147" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/530bc025-1921-4b91-89a4-ce4868f8dffb" />

---


## 🔌 Interface Connection Table (Cabling Map)
| Floor | Switch A | Port | Switch B | Port |
|---|---|---|---|---|
| Floor 1 | F1-ASW1 | G1/1/1 | F1-ASW2 | G1/1/1 |
| Floor 1 | F1-ASW1 | G1/1/2 | F1-ASW2 | G1/1/2 |
| Floor 2 | F2-ASW1 | G1/1/1 | F2-ASW2 | G1/1/1 |
| Floor 2 | F2-ASW1 | G1/1/2 | F2-ASW2 | G1/1/2 |
| Floor 3 | F3-ASW1 | G1/1/1 | F3-ASW2 | G1/1/1 |
| Floor 3 | F3-ASW1 | G1/1/2 | F3-ASW2 | G1/1/2 |

---

## 🧠 EtherChannel Design (Standard for All Floors)
- **Port-Channel ID:** `Po3`
- **Member Links:** `G1/1/1-2`
- **Mode:** **LACP active**
- **Type:** **Layer 2 trunk**

---


### 1️⃣ Configure the member interfaces (both switches in the pair)

#### ♦️ Do this on **both** switches (example: F1-ASW1 and F1-ASW2):

```bash
interface range g1/1/1 - 2
switchport mode trunk
channel-group 3 mode active
```

✅ Repeat the same exact steps for:
- F2-ASW1 + F2-ASW2
- F3-ASW1 + F3-ASW2

---

### 2️⃣ Add descriptions on Port-Channel 3 (helps with troubleshooting)

#### ♦️ Go to `interface po3` on each switch and set a description:

| Switch | Port-Channel | Description |
|---|---|---|
| F1-ASW1 | Po3 | `To-F1-ASW2` |
| F1-ASW2 | Po3 | `To-F1-ASW1` |
| F2-ASW1 | Po3 | `To-F2-ASW2` |
| F2-ASW2 | Po3 | `To-F2-ASW1` |
| F3-ASW1 | Po3 | `To-F3-ASW2` |
| F3-ASW2 | Po3 | `To-F3-ASW1` |

---

## ✅ Verification

#### ♦️ show etherchannel summary on F1-ASW1













