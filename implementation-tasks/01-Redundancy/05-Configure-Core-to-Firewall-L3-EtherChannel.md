# 🔗 Configure Core to Firewall L3 EtherChannel

### Note this is the same as the one in the setup folder [HERE](/setup/15-Configure-HS-CORE-R1-to-HS-CORE-FW1-Port-Channel.md)


## 📌 Overview

In this task, I will configure **Layer 3 EtherChannel (static Port-Channel)** between the **Hospital Core device (HS-CORE-R1)** and the **Core Firewall (HS-CORE-FW1)**.

This design removes the **single point of failure** created by a single uplink between the core and firewall. By bundling **two physical links** into one logical link, the hospital core gains:

- ✅ Redundancy (link failover)
- ✅ Higher bandwidth

**📝 Note:** To implement L3 EtherChannel in Cisco Packet Tracer, **I changed the Router to a Layer 3 switch**.

## Reference Topology

<img width="483" height="313" alt="topology" src="https://github.com/user-attachments/assets/959b455c-c96c-459f-8a54-6ca557f24bb3" />

---

## 🎯 Goals

- Connect the Distribution Switches and HS-CORE-FW1 to the new HS-CORE-R1
- Bundle them into **Port-channel 1**
- Assign in IP address for the Port-Channel
- Set the firewall Port-Channel as the **inside** interface
- Verify EtherChannel

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

### 🧩 Add firewall interfaces to Port-Channel 1

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

### 🧩  Configure Port-channel1 IP address

```bash
interface port-channel 1
 ip address 10.255.255.1 255.255.255.252
 no shutdown
 nameif inside
```

## ✅ Step 2 - Enable Routing on HS-CORE-R1

#### 🔹 On HS-CORE-R1, enable Layer 3 routing:

```bash
ip routing
```

## ✅ Step 3 - Configure EtherChannel on HS-CORE-R1 (Static “on”)

### 🧩 Add firewall interfaces to Port-Channel 1

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

#### On HS-CORE-R1:

```bash
show etherchannel summary
```

<img width="686" height="367" alt="HS-CORE-R1-etherchannel" src="https://github.com/user-attachments/assets/2cf6c74b-25e6-445b-ab6a-0b7070d80134" />

#### On HS-CORE-R1:

```bash
show ip interface brief | include Port-channel
```

<img width="797" height="85" alt="HS-CORE-R1-ip" src="https://github.com/user-attachments/assets/824b428b-86ce-41ae-8471-27ed0527233a" />











