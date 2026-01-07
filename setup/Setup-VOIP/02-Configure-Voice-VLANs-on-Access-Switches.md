# 🔊 Configure Voice VLANs on the Access Switches

## 📌 Overview

This task I will configures **Voice VLANs on the Access Switches** so IP phones **voice traffic** can be from **data traffic**.

## 🎯 Objective
- Create Voice VLANs on Access Switches
- Assign clear, consistent VLAN names
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

#### ♦️ F1-ASW1 and F1-ASW2

```bash
vlan 160
name F1-Voice
```

### 🏢 Floor 2 – Voice VLAN

#### ♦️ F2-ASW1 and F2-ASW2

```bash
vlan 260
name F2-Voice
```

### 🏢 Floor 3 – Voice VLAN

#### ♦️ F3-ASW1 and F3-ASW2

```bash
vlan 360
name F3-Voice
```

## ✅ Verification



