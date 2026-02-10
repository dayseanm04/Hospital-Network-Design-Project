# 🧪 Test – Floor 2 Endpoints to Default Gateway Connectivity

## 📌 Purpose
This test verifies that **Floor 2 endpoints** can successfully reach their **default gateway** within their assigned VLANs.

> 💡 Although there are multiple PCs for the VLAN in this project, I will use **some PC sper VLAN** to validate connectivity and avoid repetition.

---

## 🏢 Floor 2 VLAN Overview

| PC Name | Department | VLAN ID | Subnet | Default Gateway | Connected Switch |
|------|-----------|--------|--------|----------------|------------------|
| MRD-1 | Medical Records | VLAN 200 | 172.16.2.0/27 | 172.16.2.3 | F2-ASW1 |
| MRD-3 | Medical Records | VLAN 200 | 172.16.2.0/27 | 172.16.2.3 | F2-ASW2 |
| Fin-1 | Billing & Finance | VLAN 210 | 172.16.2.32/27 | 172.16.2.35 | F2-ASW1 |
| Fin-3 | Billing & Finance | VLAN 210 | 172.16.2.32/27 | 172.16.2.35 | F2-ASW2 |
| HR-1 | Human Resources | VLAN 220 | 172.16.2.64/27 | 172.16.2.67 | F2-ASW1 |

---

## 🧪 Test 1 – Medical Records Department (VLAN 200)

**Devices Tested**
- **MRD-1** (connected to F2-ASW1)
- **MRD-3** (connected to F2-ASW2)

**Test Command**

```bash
ping 172.16.2.3
```

### MRD-1 ping was successful ✅

<img width="876" height="424" alt="MRD-1" src="https://github.com/user-attachments/assets/e0149eea-5d26-4462-8d3d-11ad0cc3e81b" />

### MRD-3 ping was successful ✅

<img width="880" height="480" alt="MRD-3" src="https://github.com/user-attachments/assets/630bd482-a41a-40be-82ea-eaf0e00eae93" />

---

## 🧪 Test 2 – Billing & Finance Department (VLAN 210)

**Devices Tested**
- **Fin-1** (connected to F2-ASW1)
- **Fin-3** (connected to F2-ASW2)

**Test Command**

```bash
ping 172.16.2.35
```

### Fin-1 ping was successful ✅

<img width="876" height="429" alt="FIN-1" src="https://github.com/user-attachments/assets/142ae73d-a9d5-41c4-8730-52780cf1d733" />

### Fin-3 ping was successful ✅

<img width="875" height="481" alt="FIN-3" src="https://github.com/user-attachments/assets/22510a1c-ab52-4034-9b99-9e14c809cd08" />

## 🧪 Test 3 – Human Resources Department (VLAN 220)

**Devices Tested**
- **HR-1** (connected to F2-ASW1)

**Test Command**

```bash
ping 172.16.2.67
```


