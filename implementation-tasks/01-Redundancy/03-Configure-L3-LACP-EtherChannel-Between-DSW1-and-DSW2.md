# 🔗 03 – Configure L3 LACP EtherChannel between DSW1 ↔ DSW2

In this task I will configure a **Layer 3 (routed) LACP EtherChannel**
between **DSW1** and **DSW2**.

## Rererence Diagram

<img width="620" height="233" alt="implement-l3-LACP" src="https://github.com/user-attachments/assets/05665561-547b-40e2-982b-bc594b839fb5" />

### ✅ Why L3 EtherChannel here?
- Keeps the inter-distribution link **routed** (no VLANs carried)
- Reduces STP complexity since its a routed port
- Provides **redundancy + bandwidth** using LACP

---

## 🧠 Design Summary

| Item | Value |
|------|------|
| Devices | DSW1 ↔ DSW2 |
| EtherChannel Type | Layer 3 (Routed) |
| LACP Mode | active |
| Port-Channel | Po10 |
| Physical Interfaces | G1/1/2–G1/1/3 (both switches) |
| IP Network | 10.255.1.0/30 |
| DSW1 IP | 10.255.1.1/30 |
| DSW2 IP | 10.255.1.2/30 |

---

## ✅ Step-by-Step 

### 1️⃣ Enable Routing on the Distribution Switches
On each distribution switch, enable Layer 3 routing:
- Enter global configuration mode
- Enable routing on the switch (`ip routing`)

> 📌 Only required if routing is not already enabled.

---

### 2️⃣ Convert the Physical Links to Routed Ports
On **DSW1 and DSW2**:
- Enter interface range configuration for the uplinks used for EtherChannel
- Convert interfaces to Layer 3 with `no switchport`

| Switch | Interface Range | Purpose |
|--------|------------------|---------|
| DSW1 | Gi1/1/2 – Gi1/1/3 | Links to DSW2 |
| DSW2 | Gi1/1/2 – Gi1/1/3 | Links to DSW1 |

---

### 3️⃣ Configure the LACP EtherChannel (Channel-Group 10)
On both switches:
- Add the interface range to **channel-group 10**
- Use **LACP mode active**

**Command:**

```bash
channel-group 10 mode active
```

| Switch | Channel-Group | LACP Mode | Members |
|--------|--------------:|----------:|---------|
| DSW1 | 10 | active | Gi1/1/2–Gi1/1/3 |
| DSW2 | 10 | active | Gi1/1/2–Gi1/1/3 |

---

### 4️⃣ Configure the Port-Channel as Layer 3 + Add Description
On both switches:
- Enter **interface Port-channel10**
- Ensure it is Layer 3 (`no switchport`)
- Add a clear description

| Switch | Port-Channel | Description |
|--------|--------------|-------------|
| DSW1 | Po10 | To-DSW2 |
| DSW2 | Po10 | To-DSW1 |

---

### 5️⃣ Assign IP Addresses to the L3 Port-Channel
Assign a /30 network for the routed Port-Channel:

| Switch | Port-Channel | IP Address | Subnet Mask |
|--------|--------------|------------|-------------|
| DSW1 | Po10 | 10.255.1.1 | 255.255.255.252 |
| DSW2 | Po10 | 10.255.1.2 | 255.255.255.252 |

---

## 🔍 Verification

Run these checks on **both DSW1 and DSW2**:

### show etherchannel summary on DSW1

<img width="855" height="444" alt="DSW1-L3-LACP" src="https://github.com/user-attachments/assets/50f435f5-fb3d-4a1b-9895-b59c5de5f670" />

### show etherchannel summary on DSW2

<img width="806" height="443" alt="DSW2-L3-LACP" src="https://github.com/user-attachments/assets/0e89197c-8077-41d4-aa57-910cda48293f" />

### show interface brief DSW1

<img width="759" height="156" alt="DSW1-show-ip-int-brief" src="https://github.com/user-attachments/assets/7df7e894-b683-4ea6-abef-be588ea007a5" />




