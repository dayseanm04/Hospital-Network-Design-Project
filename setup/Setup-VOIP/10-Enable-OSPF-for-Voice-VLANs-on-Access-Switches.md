# 🔊 Enable OSPF for Voice VLANs on Access Switches

## 📌 Overview

In this task I will **OSPF routing** on the **Access Switches** to advertise **Voice VLAN** into the routing domain.  

This allows **end-to-end IP connectivity** between IP phones, the VoIP router, and the rest of the hospital network.

In all off the configurations I used **OSPF Process ID 1** and **Area 1**.

---

## Reference Network Diagram

<img width="796" height="371" alt="network-diagram" src="https://github.com/user-attachments/assets/4760b50a-76e8-452c-a214-d7eb81876b0f" />

---

## 🔁 Enable OSPF on Access Switches

### 🏢 F1-ASW1 (Voice VLAN 160)

```bash
router ospf 1
 network 172.16.10.0 0.0.0.127 area 1
```

### 🏢 F2-ASW1 (Voice VLAN 260)

```bash
router ospf 1
network 172.16.20.0 0.0.0.127 area 1
```

### 🏢 F3-ASW1 (Voice VLAN 360)

```bash
router ospf 1
network 172.16.30.0 0.0.0.127 area 1
```

### 🏥 Service-ASW (Voice VLAN 60)

```bash
router ospf 1
network 172.16.60.0 0.0.0.31 area 1
```











