# 🧪 Test – Floor 3 Endpoint to Distribution Connectivity

## 📌 Purpose

This test verifies that Floor 3 endpoints can reach Distribution Switch infrastructure (DSW1 / DSW2 loopbacks and Port-Channels).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution layer.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

## 🏢 Floor 3 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| Rad-1 | 330 – Radiology | 172.16.3.128/26 | 172.16.3.134 (DHCP) | F3-ASW1 |
| ICU-3 | 310 – ICU | 172.16.3.64/26 | 172.16.3.76 (DHCP) | F3-ASW2 |


Note: there are multple PCs in on Floor 3 and I some of them for demonstration. 

---

## 🧪 Test 1 – Rad-1 → DSW1


```bash
ping 10.0.0.1       # DSW Loopback
ping 10.10.0.13     # DSW1 Port-Channel4
```

## Rad-1 to DSW1 ping was successful ✅

<img width="1021" height="784" alt="Rad1-DSW1" src="https://github.com/user-attachments/assets/92418dfd-b141-46a1-a69a-94be849a10d9" />


---

## 🧪 Test 2 – ICU-3 → DSW2

```bash
ping 10.0.0.11      # DSW2 Loopback
ping 10.20.0.22     # DSW2 Port-Channel

```

## ICU-3 to DSW2 ping was successful ✅

<img width="871" height="658" alt="ICU-3-DSW2" src="https://github.com/user-attachments/assets/39c6cdc4-47fb-49c6-a3dc-c55793f12bb0" />


---

## 🎯 Result

Floor 3 endpoints can reach both Distribution switches
