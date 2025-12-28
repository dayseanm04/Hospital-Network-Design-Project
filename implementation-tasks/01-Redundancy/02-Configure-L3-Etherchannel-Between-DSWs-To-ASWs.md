# 🔗 Configure Layer 3 EtherChannel for DSWs to ASWs

## 📌 Overview
In this task I will configure **Layer 3 EtherChannels** between the **Distribution Switches (DSW1 and DSW2)** and the **Access Switches (ASWs)**.

I removed the **Layer 2 port-channels** and replaced with **routed EtherChannels** using **LACP**.  
Each DSW–ASW connection uses a dedicated **point-to-point /30 network**, allowing the access layer.

This approach provides:
- Better scalability
- Faster convergence
- Simplified troubleshooting
- Reduced Layer 2 dependency

## Reference Diagram

<img width="539" height="341" alt="topology" src="https://github.com/user-attachments/assets/ec132bce-d3eb-40b6-b22b-b0d694a93232" />


## 🔄 Design Change Summary

| Before | After |
|------|------|
| Layer 2 Port-Channels | Layer 3 Routed EtherChannels |
| Trunk links | Point-to-point routed links |


## 🌐 Layer 3 Point-to-Point Networks

Each DSW–ASW connection uses a dedicated **/30 subnet**.

---

## 🏢 Floor 1 – Access Switches

### 🔹 DSW1 ↔ F1-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.0 /30 |
| DSW1 Po1 IP | 10.10.0.1 |
| F1-ASW1 Po1 IP | 10.10.0.2 |
| EtherChannel | Po1 |

---

### 🔹 DSW2 ↔ F1-ASW1

| Item | Details |
|----|--------|
| Network | 10.20.0.0 /30 |
| DSW2 Po1 IP | 10.20.0.1 |
| F1-ASW1 Po2 IP | 10.20.0.2 |
| EtherChannel | Po2 |

---

### 🔹 DSW1 ↔ F1-ASW2

| Item | Details |
|----|--------|
| Network | 10.10.0.4 /30 |
| DSW1 Po2 IP | 10.10.0.5 |
| F1-ASW2 Po1 IP | 10.10.0.6 |
| EtherChannel | Po2 |

---

### 🔹 DSW2 ↔ F1-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.4 /30 |
| DSW2 Po2 IP | 10.20.0.5 |
| F1-ASW2 Po2 IP | 10.20.0.6 |
| EtherChannel | Po2 |

---

## 🏥 Floor 2 – Access Switches

### 🔹 DSW1 ↔ F2-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.8 /30 |
| DSW1 Po3 IP | 10.10.0.9 |
| F2-ASW1 Po1 IP | 10.10.0.10 |
| EtherChannel | Po3 |

---

### 🔹 DSW1 ↔ F2-ASW2

| Item | Details |
|----|--------|
| Network | 10.10.0.12 /30 |
| DSW1 Po4 IP | 10.10.0.13 |
| F2-ASW2 Po1 IP | 10.10.0.14 |
| EtherChannel | Po4 |

---

### 🔹 DSW2 ↔ F2-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.12 /30 |
| DSW2 Po4 IP | 10.20.0.13 |
| F2-ASW2 Po2 IP | 10.20.0.14 |
| EtherChannel | Po4 |

---

## 🏬 Floor 3 – Access Switches

### 🔹 DSW1 ↔ F3-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.16 /30 |
| DSW1 Po5 IP | 10.10.0.17 |
| F3-ASW1 Po1 IP | 10.10.0.18 |
| EtherChannel | Po5 |

---

### 🔹 DSW2 ↔ F3-ASW1

| Item | Details |
|----|--------|
| Network | 10.20.0.16 /30 |
| DSW2 Po5 IP | 10.20.0.17 |
| F3-ASW1 Po2 IP | 10.20.0.18 |
| EtherChannel | Po5 |

---

### 🔹 DSW1 ↔ F3-ASW2

| Item | Details |
|----|--------|
| Network | 10.10.0.20 /30 |
| DSW1 Po6 IP | 10.10.0.21 |
| F3-ASW2 Po1 IP | 10.10.0.22 |
| EtherChannel | Po6 |

---

### 🔹 DSW2 ↔ F3-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.20 /30 |
| DSW2 Po6 IP | 10.20.0.21 |
| F3-ASW2 Po2 IP | 10.20.0.22 |
| EtherChannel | Po6 |

---

## ✅ Verification

### 

