# 🌐 Configure ISP1 to ISP2 Interconnection and Static Routes

## 📌 Overview
This task establishes a **point-to-point interconnection** between **ISP1-R1** and **ISP2-R1** using a /30 subnet.

I configured Static routes are configured on both ISP routers to allow reachability.

## Topology For Reference

<img width="380" height="376" alt="topology" src="https://github.com/user-attachments/assets/14e638b2-942a-4a57-a73e-fbf651d60806" />


---

## 🎯 Objective
- Configure ISP1 ↔ ISP2 interconnection
- Assign the 70.1.1.0/30 IP
- Configure static routes for ISP1-ISP2 reachability
- Verify connectivity using ping

---

## 🧱 Interconnection Design


| Subnet | 70.1.1.0/30 |
|------|-------|
| ISP1-R1 Interface | G1/0/1 |
| ISP1-R1 IP | 70.1.1.1/30 |
| ISP2-R1 Interface | G1/1/4 |
| ISP2-R1 IP | 70.1.1.2/30 |

---

## 🔧 Interface Configuration

### ISP1-R1

```bash
interface G1/0/1
 ip address 70.1.1.1 255.255.255.252
 no shutdown
```

### ISP2-R1

```bash
interface G1/1/4
 ip address 70.1.1.2 255.255.255.252
 no shutdown
```

## 🛣 Static Route Configuration

### On ISP1-R1

Route to ISP2 public IP:

```bash
ip route 100.45.12.1 255.255.255.255 70.1.1.2
```

### On ISP2-R1

Route to ISP2 public IP:

```bash
ip route 69.45.12.1 255.255.255.255 70.1.1.1
```

---

## 🔍 Verification

### Ping ISP2-R1 From ISP1-R1: ping 70.1.1.1

<img width="703" height="291" alt="ISP1" src="https://github.com/user-attachments/assets/6d1701a0-4a49-44cb-a4a4-a977d1f3df85" />

---

### Ping ISP1-R1 From ISP2-R1: ping 70.1.1.2

<img width="691" height="295" alt="ISP2" src="https://github.com/user-attachments/assets/85671181-f348-4de9-bef7-c8b9c6606ad3" />

✅ The pings were succesful
