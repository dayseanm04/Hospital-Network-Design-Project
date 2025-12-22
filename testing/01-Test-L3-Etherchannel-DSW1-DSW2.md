# ✅ Test – L3 EtherChannel Connectivity (DSW1 ↔ DSW2)

This test validates **Layer 3 (routed) EtherChannel connectivity** between **DSW1 and DSW2**.
This test is to verify that:

- LACP formed the Port-Channel correctly
- The Port-Channel is operating as a **Layer 3 routed link**
- End-to-end connectivity works across the EtherChannel

> 📌 Note: This test does **not** require dynamic routing to be configured.

---

## Reference Test Area

<img width="634" height="206" alt="L3-Etherchannel-Test-AREA" src="https://github.com/user-attachments/assets/e70b160c-fd81-410c-a2b9-da81fc8ba2a5" />


## 🎯 Test Objective

| Objective | What I am Confirming |
|----------|-------------------------|
| EtherChannel is up | LACP bundle formed and is not suspended |
| L3 Port-Channel is routed | Port-Channel has an IP and acts as a routed interface |
| Basic connectivity works | DSW1 and DSW2 can reach each other across Po (Layer 3) |

---

## 🧩 Devices Under Test

| Device | Role |
|--------|------|
| DSW1 | Distribution Switch 1 |
| DSW2 | Distribution Switch 2 |

---

## 🧪 Connectivity Tests (Ping)

### ✅ Ping Test Plan

| Test # | Source | Destination | Purpose |
|-------:|--------|------------|---------|
| 1 | DSW1 (Port-Channel IP) | DSW2 (Port-Channel IP) | Validate L3 EtherChannel connectivity |
| 2 | DSW2 (Port-Channel IP) | DSW1 (Port-Channel IP) | Confirm reverse direction |

### 📝 Ping Results 

### Ping Test 1 (DSW1 → DSW2):

<img width="716" height="125" alt="DSW2-L3-port-channel-connectivity-test" src="https://github.com/user-attachments/assets/983b0765-7573-450d-9621-cbb52cfb4dd6" />


### Ping Test 1 (DSW2 → DSW1):

<img width="699" height="120" alt="DSW1-L3-port-channel-connectivity-test" src="https://github.com/user-attachments/assets/de7c894f-1dde-4107-9393-937c37ddd10c" />












