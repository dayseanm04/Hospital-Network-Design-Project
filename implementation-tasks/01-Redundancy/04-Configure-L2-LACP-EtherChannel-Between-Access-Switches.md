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

<img width="854" height="391" alt="F1-ASW1-et-su" src="https://github.com/user-attachments/assets/9915b30f-9329-4d9f-9c0b-dd0e2924c566" />

#### ♦️ show etherchannel summary on F1-ASW2

<img width="808" height="384" alt="F1-ASW2-et-su" src="https://github.com/user-attachments/assets/129f5d66-7761-4d60-99ae-e0cbdfa03d0a" />

#### ♦️ show etherchannel summary on F2-ASW1

<img width="812" height="385" alt="F2-ASW1-et-su" src="https://github.com/user-attachments/assets/1ed76951-742b-43c9-9fef-de0886c8b796" />

#### ♦️ show etherchannel summary on F2-ASW2

<img width="804" height="390" alt="F2-ASW2-et-su" src="https://github.com/user-attachments/assets/b6fa67c4-ca29-4ecd-9547-45333543004a" />

#### ♦️ show etherchannel summary on F3-ASW1

<img width="799" height="389" alt="F3-ASW1-et-su" src="https://github.com/user-attachments/assets/d9e0fa88-be3f-4ea3-b904-7b9944f2a274" />

#### ♦️ show etherchannel summary on F3-ASW2

<img width="813" height="386" alt="F3-ASW2-et-su" src="https://github.com/user-attachments/assets/93255837-801d-4a21-a03c-2e9589ea73d3" />
