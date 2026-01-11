# 🔁 11-Configure-DHCP-Relay-for-Voice-VLANs

## 📌 Overview

In this this task, I will configure **DHCP relay (ip helper-address)** on **Voice VLAN SVIs** across the **Access Switches**.  
Because the I configured **DHCP server for the IP phones**  on the **VoIP Router**, DHCP broadcast requests must be **forwarded** to the VOIP router.

---

## 🧠 Notes

- **DHCP Server:** VoIP Router  
- **DHCP Server IP:** `10.0.0.13` (VoIP Router Loopback)  
- **Applies To:** Voice VLAN SVIs on Access Switches  
- **Purpose:** Allow IP phones to obtain IP addresses from the VoIP Router

---

## 🔁 Configure DHCP Relay (ip helper-address)

### 🏢 F1-ASW1 (Voice VLAN 160)

#### ♦️ In global config mode

```bash
interface vlan 160
ip helper-address 10.0.0.13
```

### 🏢 F2-ASW1 (Voice VLAN 260)

#### ♦️ In global config mode

```bash
interface vlan 260
ip helper-address 10.0.0.13
```

### 🏢 F3-ASW1 (Voice VLAN 360)

#### ♦️ In global config mode

```bash
interface vlan 360
ip helper-address 10.0.0.13
```

### 🏢 Service-ASW (Voice VLAN 60)

#### ♦️ In global config mode

```bash
interface vlan 60
ip helper-address 10.0.0.13
```

## 📋 DHCP Relay Summary

| Access Switch | Voice VLAN | DHCP Relay Destination |
| ------------- | ---------: | ---------------------- |
| F1-ASW1       |        160 | 10.0.0.13              |
| F2-ASW1       |        260 | 10.0.0.13              |
| F3-ASW1       |        360 | 10.0.0.13              |
| Service-ASW   |         60 | 10.0.0.13              |
