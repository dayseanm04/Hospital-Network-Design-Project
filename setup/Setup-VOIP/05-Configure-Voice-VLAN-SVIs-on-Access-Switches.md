# 🔊 Configure Voice VLAN SVIs on Access-Switches

## 📌 Overview

I this task I will configure **SVIs (Switched Virtual Interfaces)** for the **Voice VLANs** on the **Access Switches**.  
Each SVI provides the **default gateway** for IP phones in that Voice VLAN.

## Reference Network Diagram

<img width="796" height="371" alt="network-diagram" src="https://github.com/user-attachments/assets/4760b50a-76e8-452c-a214-d7eb81876b0f" />

---

## 🧠 Voice SVI Plan (Gateways)
| Access Switch | Voice VLAN | SVI / Default Gateway | Subnet Mask |
|---|---:|---|---|
| F1-ASW1 | 160 | 172.16.10.1 | 255.255.255.128 |
| F2-ASW1 | 260 | 172.16.20.1 | 255.255.255.128 |
| F3-ASW1 | 360 | 172.16.30.1 | 255.255.255.128 |
| Service-ASW | 60 | 172.16.60.1 | 255.255.255.224 |

---

## ⚙️ Configuration (SVI Template)

Use this template on each F1-ASW1, F2-ASW1 and F3-ASW1, adjusting the **VLAN ID** and **IP address**:

**Note I configure the VOICE vlan SVI on 1 F-ASW1 beacuse they are interconecrted F-ASW1. An I allowed the VOICE vlan on the Access switch interconnection**

```bash
interface vlan <VOICE-VLAN>
ip address <GATEWAY-IP> 255.255.255.128
no shutdown
```

---

## 1️⃣ F1-ASW1 (VLAN 160)

```bash
interface vlan 160
ip address 172.16.10.1 255.255.255.128
no shutdown
```

## 2️⃣ F2-ASW1 (VLAN 260)

```bash
interface vlan 160
ip address 172.16.20.1 255.255.255.128
no shutdown
```

## 3️⃣ F3-ASW1 (VLAN 360)

```bash
interface vlan 360
ip address 172.16.30.1 255.255.255.128
no shutdown
```

## 4️⃣ Service-ASW (VLAN 60)

```bash
interface vlan 60
ip address 172.16.60.1 255.255.255.224
no shutdown
```

## ✅ Verification

#### ♦️ On F1-ASW1 show ip interface brief | include Vlan

<img width="828" height="139" alt="F1-ASW1-voice-vlan-verify" src="https://github.com/user-attachments/assets/e5c08abc-7b2b-4d42-93ea-3e7d35ebefcc" />


#### ♦️ On F2-ASW1 show ip interface brief | include Vlan

<img width="810" height="138" alt="F2-ASW1-voice-vlan-verify" src="https://github.com/user-attachments/assets/e8f6a9f2-1941-4064-aec4-401ced867ddb" />

#### ♦️ On F3-ASW1 show ip interface brief | include Vlan

<img width="835" height="135" alt="F3-ASW1-voice-vlan-verify" src="https://github.com/user-attachments/assets/15406cd2-186d-4a41-8959-feb24e5a2623" />

#### ♦️ On Service-ASW show ip interface brief | include Vlan

<img width="797" height="120" alt="S-ASW-voice-vlan-verify" src="https://github.com/user-attachments/assets/6df60d77-8afe-4878-82e0-923061c20e8f" />
