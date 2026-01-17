# 🌐 01 – Configure Internet Edge Router and ISP Link

In this task I will set up **Internet connectivity** for the Hospital Network by configuring an **Internet Edge Router** and establishing a **WAN link to the ISP router**.  
This simulated Internet will allows users in the Hospital Network to access **external services** such as DNS and HTTP/HTTPS

---

## 🎯 Objectives

- ✅ Configure the **ISP router** serial interface
- ✅ Configure the **INET Edge router** WAN interface
- ✅ Establish a point-to-point **/30 WAN link**
- ✅ Verify basic connectivity between ISP and INET Edge

## Reference INET


<img width="1156" height="302" alt="INET" src="https://github.com/user-attachments/assets/24a28233-08b2-41f2-adc5-827166b06c5d" />

---

## 🧠 Devices Involved

| Device | Role |
|---|---|
| `ISP1-R1` | ISP router (connects hospital to INET network) |
| `INET-Edge-01` | INET edge router (front-end of simulated Internet services) |

---

## 🌐 WAN Link Addressing

**WAN Network:** `198.51.100.0/30`

| Device | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| `ISP1-R1` | `S4/0` | `198.51.100.1` | `255.255.255.252` |
| `INET-Edge-01` | `S0/1/0` | `198.51.100.2` | `255.255.255.252` |

---

## ⚙️ Configure ISP Router (ISP1-R1)

### ♦️ Configure ISP1-R1 S4/0 interface:

```bash
enable
configure terminal
interface s4/0
```

### ♦️ Sets the clock rate:

```bash
clock rate 4000000

```








