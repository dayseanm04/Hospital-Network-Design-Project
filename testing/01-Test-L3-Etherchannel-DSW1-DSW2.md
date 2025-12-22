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


