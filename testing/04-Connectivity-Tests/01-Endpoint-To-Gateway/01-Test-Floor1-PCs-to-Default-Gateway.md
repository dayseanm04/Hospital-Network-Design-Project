# 🧪 Test – Floor 1 PCs to Default Gateway

## 📌 Purpose
This test verifies that **Floor 1 end devices** can successfully reach their **default gateway** within their respective VLANs.

> 💡 Although there are multiple PCs for the VLAN in this project, I will use **some PC sper VLAN** to validate connectivity and avoid repetition.

---

## 🏢 Floor 1 VLAN Overview

| PC Name | Department | VLAN ID | Subnet | Default Gateway | Connected Switch |
|------|-----------|--------|--------|----------------|------------------|
| ED-1 | Emergency DPT | VLAN 101 | 172.16.1.0/26 | 172.16.1.3 | F1-ASW1 |
| ED-3 | Emergency DPT | VLAN 101 | 172.16.1.0/26 | 172.16.1.3 | F1-ASW2 |
| X-R-1 | XRay DPT | VLAN 110 | 172.16.1.64/27 | 172.16.1.67 | F1-ASW1 |
| Nrs-1 | ED Nurse Offices | VLAN 121 | 172.16.1.96/27 | 172.16.1.99 | F1-ASW2 |

---

## 🧪 Test 1 – Emergency Department PCs (VLAN 101)

**Devices Tested**
- **ED-1** (connected to F1-ASW1)
- **ED-3** (connected to F1-ASW2)

**Test Command**

```bash
ping 172.16.1.3
```

### ED-1 ping was successful ✅
<img width="875" height="437" alt="ED1" src="https://github.com/user-attachments/assets/f03439f9-ce20-449e-a424-4bbb564886dd" />

### ED-3 ping was successful ✅

<img width="875" height="421" alt="ED3" src="https://github.com/user-attachments/assets/ab3ff59a-de5a-47a1-bbf1-0c0d6f6dd2da" />

---

## 🧪 Test 2 – XRay Department PC (VLAN 110)

**Device Tested**
- **X-R-1** (connected to F1-ASW1)

**Test Command**

```bash
ping 172.16.1.67
```

### X-R-1 ping was successful ✅

<img width="879" height="467" alt="XR-1" src="https://github.com/user-attachments/assets/f83e01ef-82be-441f-aa2d-f07acecd86f0" />

---

## 🧪 Test 3 – Nurse Offices PC (VLAN 120)

**Device Tested**
- **Nrs-1** (connected to F1-ASW2)

**Test Command**

```bash
ping 172.16.1.99
```

### Nrs-1 ping was successful ✅

<img width="871" height="471" alt="Nrs-1" src="https://github.com/user-attachments/assets/3ac10f6a-d150-466a-9ba8-a7d1998409b3" />
