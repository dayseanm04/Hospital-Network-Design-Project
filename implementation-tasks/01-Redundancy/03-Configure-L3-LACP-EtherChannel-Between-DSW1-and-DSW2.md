# 🔗 03 – Configure L3 LACP EtherChannel between DSW1 ↔ DSW2

In this task I will configure a **Layer 3 (routed) LACP EtherChannel**
between **DSW1** and **DSW2**.

## Rererence Diagram

<img width="620" height="233" alt="implement-l3-LACP" src="https://github.com/user-attachments/assets/05665561-547b-40e2-982b-bc594b839fb5" />

### ✅ Why L3 EtherChannel here?
- Keeps the inter-distribution link **routed** (no VLANs carried)
- Reduces STP complexity since its a routed port
- Provides **redundancy + bandwidth** using LACP

---

## 🧠 Design Summary

| Item | Value |
|------|------|
| Devices | DSW1 ↔ DSW2 |
| EtherChannel Type | Layer 3 (Routed) |
| LACP Mode | active |
| Port-Channel | Po10 |
| Physical Interfaces | G1/1/2–G1/1/3 (both switches) |
| IP Network | 10.255.1.0/30 |
| DSW1 IP | 10.255.1.1/30 |
| DSW2 IP | 10.255.1.2/30 |

---

## ✅ Step-by-Step 

### 1️⃣ Enable Routing on the Distribution Switches
On each distribution switch, enable Layer 3 routing:
- Enter global configuration mode
- Enable routing on the switch (`ip routing`)

> 📌 Only required if routing is not already enabled.

---

### 2️⃣ Convert the Physical Links to Routed Ports
On **DSW1 and DSW2**:
- Enter interface range configuration for the uplinks used for EtherChannel
- Convert interfaces to Layer 3 with `no switchport`

| Switch | Interface Range | Purpose |
|--------|------------------|---------|
| DSW1 | Gi1/1/2 – Gi1/1/3 | Links to DSW2 |
| DSW2 | Gi1/1/2 – Gi1/1/3 | Links to DSW1 |

---



