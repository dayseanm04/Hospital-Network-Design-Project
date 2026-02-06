# 🧪 Test – ISP to Hospital Edge Router Connectivity

## 📌 Overview

In this task I will verify **Layer 3 connectivity** between the **ISP routers** and the **Hospital Edge Routers**.  

## 🎯 Test Objective

Ensure that:
- **ISP1-R1** can reach **HS-EDGE-R1**
- **ISP2-R1** can reach **HS-EDGE-R2**


## Topology For Reference

<img width="724" height="358" alt="topology" src="https://github.com/user-attachments/assets/8b78884b-49b1-4567-99d1-3a749232606e" />

---


### ▶️ Test 1: ISP1 to Hospital Edge Router

From **ISP1-R1**, ping the hospital edge router:

```bash
ping 69.45.12.2
```

<img width="710" height="137" alt="ISP1-Ping" src="https://github.com/user-attachments/assets/ebda1490-273f-4a4d-87b3-e96a568c0b47" />

✅ ISP1-R1 successfully reached HS-EDGE-R1

