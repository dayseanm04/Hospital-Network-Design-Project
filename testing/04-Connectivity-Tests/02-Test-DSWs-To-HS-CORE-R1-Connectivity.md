# ✅ Test – DSWs to HS-CORE-R1 IP Connectivity

This test validates **Layer 3 IP connectivity** between the
**Distribution Switches (DSW1, DSW2)** and the
**Hospital Core Router (HS-CORE-R1)** using **point-to-point /30 networks**.

This test is performed **before any dynamic routing protocols** are configured.

---

## 🧩 Devices Under Test

| Device | Role |
|------|------|
| DSW1 | Distribution Switch 1 |
| DSW2 | Distribution Switch 2 |
| HS-CORE-R1 | Hospital Core Router1 |

---

## 🌐 IP Addressing Reference (From Configuration)

### 🔗 Point-to-Point Links

| Link | Device | Interface | IP Address | Subnet Mask |
|-----|--------|-----------|------------|-------------|
| Core ↔ DSW1 | HS-CORE-R1 | Gi2/0 | 10.255.0.1 | 255.255.255.252 |
| Core ↔ DSW1 | DSW1 | Gi1/1/1 | 10.255.0.2 | 255.255.255.252 |
| Core ↔ DSW2 | HS-CORE-R1 | Gi3/0 | 10.255.0.5 | 255.255.255.252 |
| Core ↔ DSW2 | DSW2 | Gi1/1/1 | 10.255.0.6 | 255.255.255.252 |

## 🎯 Test Objectives

| Objective | Description |
|---------|-------------|
| Verify IP reachability | DSWs can ping HS-CORE-R1 |
| Verify bidirectional connectivity | HS-CORE-R1 can ping both DSWs |

---

## 🧪 Connectivity Tests (Ping)

### 📌 Ping Test Plan

| Test # | Source | Destination |
|------:|--------|-------------|
| 1 | DSW1 | 10.255.0.1 (HS-CORE-R1) |
| 2 | DSW2 | 10.255.0.5 (HS-CORE-R1) |
| 3 | HS-CORE-R1 | 10.255.0.2 (DSW1) |
| 4 | HS-CORE-R1 | 10.255.0.6 (DSW2) |

### 📝 Ping Results 

#### DSW1 to 10.255.0.1 

<img width="733" height="134" alt="DSW1-HS-CORE-R1-test" src="https://github.com/user-attachments/assets/ef27f6ff-c817-490c-90fc-824ce2f63376" />






