# 🔗 Configure HS-CORE-R1 to HS-CORE-FW1 Port-Channel

## 📌 Overview

In this task, I configure a **Layer 3 EtherChannel (static Port-Channel)** between the **HS-CORE-R1** and the **HS-CORE-FW1**.

This design removes the **single point of failure** created by a single uplink between the core and firewall.  

## 🎯 Goals
- Configure Port-Channel for the connection to HS-CORE-FW1
- Bundle them into **Port-channel 1**
- Assign routed /30 IP addressing for the Port-Channel
- Set the firewall Port-Channel as the **inside** interface
- Verify EtherChannel


## Reference Topology

<img width="483" height="313" alt="topology" src="https://github.com/user-attachments/assets/642f493d-b5b0-436e-b8d2-c4658b34ed3b" />

---

## 🔌 Physical Connections

| Device | Interface | Connected To | Interface |
|------|----------|-------------|-----------|
| HS-CORE-R1 | G1/1/1 | HS-CORE-FW1 | G1/1 |
| HS-CORE-R1 | G1/1/2 | HS-CORE-FW1 | G1/2 |
| HS-CORE-R1 | G1/1/3 | DSW1 | G1/1/1 |
| HS-CORE-R1 | G1/1/4 | DSW2 | G1/1/1 |

---

## 🧠 Port-Channel 1 IP Addressing

| Device | Logical Interface | IP Address | Subnet Mask | Network |
|------|-------------------|-----------|------------|---------|
| HS-CORE-FW1 | Port-channel1 | 10.255.255.1 | 255.255.255.252 | 10.255.255.0/30 |
| HS-CORE-R1 | Port-channel1 | 10.255.255.2 | 255.255.255.252 | 10.255.255.0/30 |

---


# 🛠 Step-by-Step Configuration

---

## ✅ Step 1 - Configure EtherChannel on HS-CORE-FW1 (Static)

### 🧩  Add firewall interfaces to Port-Channel 1

```bash
interface g1/1
 no shutdown
 channel-group 1 mode on
```

```bash
interface g1/2
 no shutdown
 channel-group 1 mode on
```

### 🧩 Configure Port-channel1 IP address

```bash
interface port-channel 1
 ip address 10.255.255.1 255.255.255.252
 no shutdown
 nameif inside
```

## ✅ Step 2 - Enable Routing on HS-CORE-R1

On **HS-CORE-R1**, enable Layer 3 routing:

```bash
ip routing
```

## ✅ Step 3 — Configure EtherChannel on HS-CORE-R1 (Static)

### 🧩 Add core interfaces to Port-Channel 1

```bash
interface range g1/1/1-2
 channel-group 1 mode on
```

### 🧩 Configure Port-channel1 IP address

```bash
interface port-channel 1
 ip address 10.255.255.2 255.255.255.252
 no shutdown
```

## ✅ Verification

### Verify EtherChannel Status (HS-CORE-R1)

```bash
show etherchannel summary
```

<img width="686" height="367" alt="HS-CORE-R1-etherchannel" src="https://github.com/user-attachments/assets/3927ebc1-a718-4c8a-af66-5c2dadc4a36a" />

### Ping Test 

#### 🟢 From HS-CORE-R1 ping HS-CORE-FW1 Port-Channel1:

```bash
ping 10.255.255.1
```

<img width="856" height="151" alt="HS-CORE-FW1-ping" src="https://github.com/user-attachments/assets/540351c8-090e-4b94-9998-50e06170b5ef" />

#### 🟢 From HS-CORE-FW1 ping HS-CORE-FW1 Port-Channel1:

```bash
ping 10.255.255.2
```

<img width="961" height="150" alt="HS-CORE-R1-ping" src="https://github.com/user-attachments/assets/be12dbaa-2331-42a6-ba04-d4602e135b1c" />
