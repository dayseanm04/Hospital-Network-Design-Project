# 🌐 08 – Update DHCP Pools with Centralized DNS Server

## 📌 Overview

In this task, I will updates all DHCP pools on the **DHCP-SRV** to use a centralized DNS server:
DNS Server: 200.10.0.2

## Topology For Reference

<img width="984" height="438" alt="toplogy" src="https://github.com/user-attachments/assets/3c2ecd67-1e2e-40b0-a8f9-5d50c7032b97" />


## 🏥 Scope of Update

All department DHCP pools must be updated to use:
DNS Server: 200.10.0.2

---

## 🖥️ Configuration Steps (Packet Tracer – GUI)

### Step 1 – Access the DHCP Server

1. Click on **DHCP-SRV**
2. Navigate to:
   Services → DHCP

---

### 🔹 Step 2 – Update Each DHCP Pool

For **each existing DHCP pool**, configure:
DNS Server: 200.10.0.2
Then click **Save**.
Repeat this for all department pools.

---

