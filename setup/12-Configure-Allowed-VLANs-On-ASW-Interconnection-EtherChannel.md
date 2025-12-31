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

