# 🔊 Configure Voice VLANs on the Access Switches

## 📌 Overview

This task I will configure **Voice VLANs on the Access Switches** so IP phones **voice traffic** can be from **data traffic**. I will also add interfaces to te Voice VLANs.

## 🎯 Objective
- Create Voice VLANs on Access Switches
- Assign clear, consistent VLAN names
- Assign interfaces to the Voice VLANs
- Prepare switch ports for IP phone connectivity

## Reference Network Diagram

<img width="514" height="438" alt="reference-topology" src="https://github.com/user-attachments/assets/761d68fd-bea2-4da0-929f-86c5da49b62b" />

---

## 🧱 Voice VLAN Reference

| Location | Voice VLAN ID | VLAN Name |
|--------|---------------|----------|
| Floor 1 | 160 | F1-Voice |
| Floor 2 | 260 | F2-Voice |
| Floor 3 | 360 | F3-Voice |
| Floor 4 | 460 | F4-Voice |
| IT Department | 60 | IT-DPT-Voice |

---

## ⚙️ Configuration Steps

### 🔧 Enter global configuration mode, then create the Voice VLAN.

### 🏢 Floor 1 – Voice VLAN

#### ♦️ On F1-ASW1 and F1-ASW2

```bash
vlan 160
name F1-Voice
```

### 🏢 Floor 2 – Voice VLAN

#### ♦️ On F2-ASW1 and F2-ASW2

```bash
vlan 260
name F2-Voice
```

### 🏢 Floor 3 – Voice VLAN

#### ♦️ On F3-ASW1 and F3-ASW2

```bash
vlan 360
name F3-Voice
```

## 🔹 Part B – Add Interfaces to the Voice VLAN

I this I will assigns **access switch interfaces** to the **Voice VLAN** so IP phones can correctly tag and send voice traffic.

### ⚙️ Configuration Example

### 🏢 Floor 1 – Voice VLAN

#### ♦️ On F1-ASW1 and F1-ASW2

```bash
interface range GigabitEthernet1/0/1 - 20
switchport voice vlan 160
```

**Note:** G1/0/1-20 are all conneced to end devices in Floor1!


## ✅ Verification

### On F1-ASW1 show vlan brief

