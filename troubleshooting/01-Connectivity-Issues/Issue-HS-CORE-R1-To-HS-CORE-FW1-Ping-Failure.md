# 🚨 Issue: HS-CORE-FW1 to HS-CORE-FW1 ping failure

## Refernce Diagram

<img width="569" height="263" alt="HS1-CORE-FW1-HS-CORE-R1" src="https://github.com/user-attachments/assets/8955fd02-a101-4e98-97c5-6484cc844c8f" />

## 📌 Problem Description

When I pinged HS-CORE-FW1 **10.255.255.1** from HS-CORE-R1 it failed, and also when I pinged the HS-CORE-R1 from the Fw it also failed.

## 📝 Ping Results 

#### Test 1: HS-CORE-R1 to 10.255.255.1 

<img width="752" height="131" alt="HS-CORE-R1-To-HS-CORE-FW1-failed" src="https://github.com/user-attachments/assets/b397a990-92a5-4ef5-a872-b7da046947d4" />

#### Test 2: HS-CORE-FW1 to 10.255.255.2

<img width="749" height="126" alt="HS-CORE-FW1-To-HS-CORE-R1-failed" src="https://github.com/user-attachments/assets/b058801b-6f75-4e82-a5a9-7df067fede99" />
 
The ping test Failed.

## 🌐 Affected Devices
- HS-CORE-R1
- HS-CORE-FW1

## 🔍 Troubleshooting Steps Taken
- I viewed the running config of the HS-CORE-FW1
- I viewed the interface IP and status

### I pinged HS-CORE-FW1 and oberved in simulation mode

<img width="586" height="280" alt="HS-CORE-R1-HS-CORE-FW1-ping-test-sim" src="https://github.com/user-attachments/assets/ff5d2942-5f3e-430e-a7d4-bfc21db54cda" />


## 🛠 Root Cause
Since I was pining the firewall the first that came to mind was that the **firewall was blocking the ICMP echo requests** which is the root cause.


## ✅ Resolution

### 🔍 Identified Cause
The ping failure between **HS-CORE-R1** and **HS-CORE-FW1** was caused by the firewall **blocking ICMP traffic by default**.  
Since no security policies had been configured yet, the firewall’s **implicit deny rule** prevented ICMP echo requests from reaching HS-CORE-FW1.

**Note:** HS-CORE-FW1 G1/7 interface is connected to HS-CORE-R1 G0/0 interface

## ♦️ Actions performed on **HS-CORE-FW1**:

#### 🔷 In interface config mode for **G1/7**, I assigned the interface a logical name (**inside**)
  - With the command `nameif inside`
 
**See bellow:**

<img width="576" height="64" alt="HS-CORE-FW1-inside" src="https://github.com/user-attachments/assets/3b6565f5-2fd4-4c9c-905a-341aac0af120" />

**Note:** the security is set to 100 the maximum meaning trusted.

### 🔷 The in Global config mode I configued an extended ACL permitting ICMP from HS-CORE-R1 to HS-CORE-FW1

**Command ⚒:**

```bash
access-list allow-icmp-from-HS-CORE-R1 permit icmp host 10.255.255.2 host 10.255.255.1 
```

### 🔷 Applied the ACL inbound on the firewall interface

```bash
access-group allow-icmp-from-HS-CORE-R1 in interface inside
```

---

## 🧪 Verification

After applying the ACL:

### HS-CORE-R1 pings HS-CORE-FW1 (10.255.255.1)

<img width="728" height="124" alt="HS-CORE-FW1-ping-success" src="https://github.com/user-attachments/assets/83fc7495-6b32-44e5-82bb-4816dbe3a5d2" />

### HS-CORE-FW1 pings HS-CORE-R1 (10.255.255.2)

<img width="727" height="127" alt="HS-CORE-R1-ping-success" src="https://github.com/user-attachments/assets/accc103c-e47a-4129-a51e-9b61905c7865" />

The ping were successful

--- 

### Check the ACL on HS-CORE-FW1

<img width="942" height="133" alt="HS-CORE-FW1-view-ACL" src="https://github.com/user-attachments/assets/aa720b3a-882b-46f5-8ad4-bb56d0409ebf" />

The ACL I configured permited the pings from **HS-CORE-R1**. The hit count was 5 and it matches the ICMP echos sent by **HS-CORE-R**1

**Save the configuration on HS-CORE-FW1**

```bash
write memory
```
