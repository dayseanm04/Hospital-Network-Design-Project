# 🧪 Test – IT Department Endpoint to Default Gateway Connectivity

## 📌 Purpose
This test verifies that **IT Department endpoints** can successfully reach their **default gateway** within the IT Department VLAN.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

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

### IT-PC2 ping was successful ✅

<img width="870" height="471" alt="IT-PC2" src="https://github.com/user-attachments/assets/897454d6-43bb-4f3b-ad02-b87c4a14dca0" />





