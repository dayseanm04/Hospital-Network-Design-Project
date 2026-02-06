# 🧪 Test ISP1 and ISP2 Connectivity and Reachability

This task I will verify **Layer 3 connectivity** and **routing reachability** between **ISP1-R1** and **ISP2-R1**.  
The goal is to confirm that the ISP interconnection is operational and that routes are being exchanged correctly.

## 🎯 Test Objectives

- ✅ Verify IP connectivity between ISP routers
- ✅ Confirm reachability of advertised networks

## Reference Topology

<img width="704" height="538" alt="topology" src="https://github.com/user-attachments/assets/96054ddf-55d6-42f3-9943-76aa16c12d1c" />

---

## 🔗 Inter-ISP Link Verification

### Test 1: ISP1 → ISP2 (Point-to-Point Link)

From **ISP1-R1**:

```bash
ping 10.50.50.1
```

<img width="745" height="133" alt="ISP1-ping" src="https://github.com/user-attachments/assets/71f3b0e5-1e1c-49ae-8a54-86fd4b34e04b" />

✅ successful


### Test 2: ISP2 → ISP1 (Point-to-Point Link)

From **ISP2-R1**:

```bash
ping 10.50.50.2
```

<img width="717" height="151" alt="ISP2-ping" src="https://github.com/user-attachments/assets/a2ef4806-2f8c-41a0-878d-75683b170f6e" />

✅ successful


### Test 2: ISP2 → INET Servers 

From **ISP2-R1**:

```bash
ping 10.20.20.10
ping 10.20.20.11
ping 10.20.20.12
```

<img width="795" height="376" alt="INET-ping-from-ISP2" src="https://github.com/user-attachments/assets/ae37fa0c-dece-44df-aa81-9bd78a55daf4" />

✅ ISP2-R1 successfully pinged the INET Servers
