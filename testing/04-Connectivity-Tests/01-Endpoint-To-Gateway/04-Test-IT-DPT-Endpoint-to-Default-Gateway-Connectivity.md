# 🧪 Test – IT Department Endpoint to Default Gateway Connectivity

## 📌 Purpose
This test verifies that **IT Department endpoints** can successfully reach their **default gateway** within the IT VLAN.

---

## 🏢 IT Department VLAN Overview

| PC Name | Department | VLAN ID | Subnet | Default Gateway | Connected Switch |
|------|-----------|--------|--------|----------------|------------------|
| IT-PC1 | IT Department | VLAN 240 | 10.50.50.0/27 | 10.50.50.1 | Service-ASW |
| IT-PC2 | IT Department | VLAN 240 | 10.50.50.0/27 | 10.50.50.1 | Service-ASW |

---

## 🧪 Test – IT Department (VLAN 240)

**Devices Tested**
- **IT-PC1**
- **IT-PC2**

**Test Command**

```bash
ping 10.50.50.1
```

### IT-PC1 ping was successful ✅

<img width="871" height="471" alt="IT-PC1" src="https://github.com/user-attachments/assets/6b565c19-c143-4b69-8ee3-b6737ebc22f6" />







