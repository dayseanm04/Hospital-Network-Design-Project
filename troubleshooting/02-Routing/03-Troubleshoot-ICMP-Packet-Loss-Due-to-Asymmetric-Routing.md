# 🚨 Issue: ICMP Packet Loss Due to Asymmetric Routing

## Reference Topology

<img width="708" height="618" alt="toplogy4" src="https://github.com/user-attachments/assets/5f671e8c-3e85-4ff5-871d-a27c0099da2c" />

---

## 📌 Problem Description

When I ping **HS-EDGE-R2** from internal hosts (PCs connected to the Access Switches) to I got **50% packet loss**.  

---

## 🌐 Affected Devices
- ED1 (Floor 1 PC)
- Access Switches (Floor 1, Floor 2, Floor 3)
- DSW1
- DSW2
- HS-CORE-FW2
- HS-EDGE-R2

---

## ❌ Symptoms Observed

Emergency DPT PC1 ping HS-EDGE-R2 

<img width="777" height="383" alt="ED1-ping" src="https://github.com/user-attachments/assets/bfee098b-c924-47f6-af14-3505e887730c" />

- ICMP ping showed **50% packet loss**
- Requests succeeded, but some replies timed out
- Observed different **forward and return paths** in simulation mode

---

## 🔍 Troubleshooting Steps Taken
- 1️⃣ Verified that all interfaces and links were **up/up**
- 2️⃣ Confirmed correct **IP addressing** across access, distribution, core, and edge layers
- 3️⃣ Used **simulation mode** to trace packet flow
- 4️⃣ Identified **asymmetric routing**:
  - Forward path used: ED-1 > ASW1 > DSw2 > HS-CORE-FW2 > HS-EDGE-R2
  - Return  path used: HS-EDGE-R2 > HS-CORE-FW2 > DSW2 > F3-ASW2 > DSW1 > F1-ASW1 > ED-1
- 5️⃣ Determined that OSPF was selecting **different-cost return paths**

---

## 🛠 Root Cause
The packet loss was caused by **asymmetric routing** in the OSPF domain.

OSPF selected different paths for the forward and return traffic, causing ICMP replies to return through a different access and distribution switch.  

This resulted in intermittent packet loss during the ping test.

---

## ✅ Resolution
Adjusted OSPF design to enforce more predictable routing behavior:


