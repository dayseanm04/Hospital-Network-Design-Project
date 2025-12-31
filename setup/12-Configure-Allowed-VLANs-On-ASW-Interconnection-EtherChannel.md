# 🔐 Configure Allowed VLANs on L2 LACP EtherChannel (ASW Interconnections)

**Goal:** Configure allowed VLAN on access-switches interconnections

## Refernce Netork Diagram

<img width="551" height="147" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/530bc025-1921-4b91-89a4-ce4868f8dffb" />

---

## 🔗 Interconnection Summary (What connects to what)

| Pair | Link Type | Port-Channel | Allowed VLANs |
|---|---|---:|---|
| **F1-ASW1 ↔ F1-ASW2** | L2 Trunk EtherChannel | **Po3** | **101** |
| **F2-ASW1 ↔ F2-ASW2** | L2 Trunk EtherChannel | **Po3** | **200, 210** |
| **F3-ASW1 ↔ F3-ASW2** | L2 Trunk EtherChannel | **Po3** | **300, 310, 330**  |

✅ Do the same config on **both switches in the pair** (example: F1-ASW1 *and* F1-ASW2).

---

## 🛠️ Step-by-Step Configuration

### 1️⃣ Configure Po3 allowed VLANs on Floor 1 switches (F1-ASW1 + F1-ASW2)

#### ♦️ On **F1-ASW1** and **F1-ASW2**:

```bash
interface po3
switchport trunk allowed vlan 101
```


### 🟩 verify

#### show interfaces trunk on F1-ASW1

<img width="708" height="231" alt="F1-1-trunk" src="https://github.com/user-attachments/assets/78951b9c-7475-4135-8fd7-858a64abe9bc" />

