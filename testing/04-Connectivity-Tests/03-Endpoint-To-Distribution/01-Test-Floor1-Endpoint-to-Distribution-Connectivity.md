# 🧪 Test – Floor 1 Endpoint to Distribution Connectivity

## 📌 Purpose

This test verifies that Floor 1 endpoints can reach Distribution Switch infrastructure (DSW1 / DSW2 loopbacks and Port-Channels).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution layer.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

## 🏢 Floor 1 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| ED-1 | 101 – Emergency | 172.16.1.0/26 | 172.16.1.4 (DHCP) | F1-ASW1 |
| F1-ED-Nrs-1 | 120 – Nurses | 172.16.1.64/27 | 172.16.1.100 (DHCP) | F1-ASW2 |

Note: there are multple PCs in on Floor 1 and I some of them for demonstration. 

---

## 🧪 Test 1 – ED-1 → DSW1

```bash
ping 10.0.0.10      # DSW1 Loopback
ping 10.10.0.1      # DSW1 Port-Channel1
```

## ED-1 to DSW1 ping was successful ✅

<img width="1051" height="765" alt="ED1-DSW1" src="https://github.com/user-attachments/assets/87cced50-82bc-4f68-88a6-52825fb5130d" />

---

## 🧪 Test 2 – F1-ED-Nrs-1 → DSW2

```bash
ping 10.0.0.11      # DSW2 Loopback
ping 10.20.0.5      # DSW2 Port-Channel2

```

## F1-ED-Nrs-1 to DSW2 ping was successful ✅

<img width="991" height="751" alt="F1-ED-Nrs-DSW2" src="https://github.com/user-attachments/assets/d800bfb7-6db9-4db8-b449-6c7ab7a10110" />








