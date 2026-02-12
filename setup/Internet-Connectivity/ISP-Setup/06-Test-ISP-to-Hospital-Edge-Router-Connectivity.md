# 🧪 Test – ISP to Hospital Edge Router Connectivity

## 📌 Overview

In this task I will verify **Layer 3 connectivity** between the **ISP routers** and the **Hospital Edge Routers**.  

## 🎯 Test Objective

Ensure that:
- **ISP1-R1** can reach **HS-EDGE-R1**
- **ISP2-R1** can reach **HS-EDGE-R2**


## Topology For Reference

<img width="782" height="406" alt="topology" src="https://github.com/user-attachments/assets/f52f12ed-6697-4a1e-bc2e-15e693bb3312" />


### ▶️ Test 1: ISP1 to Hospital Edge Router 1

From **ISP1-R1**, ping the hospital edge router:

```bash
ping 69.45.12.2
```

<img width="710" height="137" alt="ISP1-Ping" src="https://github.com/user-attachments/assets/ebda1490-273f-4a4d-87b3-e96a568c0b47" />

✅ ISP1-R1 successfully reached HS-EDGE-R1

### ▶️ Test 1: ISP2 to Hospital Edge Router 2

From **ISP2-R1**, ping the hospital edge router:

```bash
ping 100.45.12.2
```

<img width="756" height="129" alt="ISP2-Ping" src="https://github.com/user-attachments/assets/a68d9bc1-58a8-4c7f-aa50-654da64d4c79" />

✅ ISP2-R1 successfully reached HS-EDGE-R2
