# 🧪 Test – Inter-VLAN Endpoint-to-Endpoint Connectivity

## 📌 Purpose
This test verifies **Layer 3 (Inter-VLAN) connectivity** between endpoints located in **different VLANs across multiple floors**.

### 💡 Successful results confirm that:
- Inter-VLAN routing is functioning correctly
- Default gateways are properly configured
- Core/distribution routing (OSPF) is operating as expected

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# 🌐 Inter-VLAN Connectivity Tests

---

## 🧪 Test 1 – Floor 1 to Floor 2

### 🔎 Devices
- **ED-1** – VLAN 101 (172.16.1.0/26) – Floor 1  
- **MRD-1** – VLAN 200 (172.16.2.0/27) – Floor 2  

### 🔧 Test Command

```bash
ping 172.16.2.4
```

## ED-1 to MRD-1 ping was successful ✅

<img width="700" height="371" alt="ED1-MRD-1" src="https://github.com/user-attachments/assets/32dbb301-b27a-4c53-8225-4becd422aeee" />

---

## 🧪 Test 2 – Floor 1 to Floor 3

### 🔎 Devices
- **ED-1** – VLAN 101 (172.16.1.0/26) – Floor 1  
- **Rad-1** – VLAN 330 (172.16.3.128/26) – Floor 3

### 🔧 Test Command

```bash
ping 172.16.3.133
```

## ED-1 to Rad-1 ping was successful ✅

<img width="697" height="373" alt="ED1-Rad-1" src="https://github.com/user-attachments/assets/eae8cc52-7284-4d52-a680-d1753f28a5e6" />

---

## 🧪 Test 3 – Floor 2 to Floor 1

### 🔎 Devices
- **Fin-1** – VLAN 210 (172.16.2.32/27) – Floor 2 
- **ED-1** – VLAN 101 (172.16.1.0/26) – Floor 1

### 🔧 Test Command

```bash
ping 172.16.1.4
```

## Fin-1 to ED-1 ping was successful ✅

<img width="701" height="365" alt="F3-Nrs1-ED1" src="https://github.com/user-attachments/assets/1bc66610-b86c-4ef6-9b84-91efa536c53a" />

---

## 🧪 Test 4 – Floor 2 to Floor 3

### 🔎 Devices
- **Fin-1** – VLAN 210 (172.16.2.32/27) – Floor 2 
- **ICU-1** – VLAN 310 (172.16.3.64/26) –Floor 3

### 🔧 Test Command

```bash
ping 172.16.3.70
```

## Fin-1 to ICU-1 ping was successful ✅

<img width="701" height="370" alt="Fin1-ICU1" src="https://github.com/user-attachments/assets/0c157352-2d4e-4c03-a689-3f7fded4dcb9" />





