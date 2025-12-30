# 🚨 Issue: OSPF Area Mismatch Between DSW1 and Service-ASW

## 📌 Problem Description
OSPF adjacency failed to form between **DSW1** and **Service-ASW** over the **10.255.2.0/30** point-to-point Port-Channel link. Even though I enabled OSPF on both devices, they did not become neighbors.

---

## 🌐 Affected Devices
- DSW1  
- Service-ASW

---

## ❌ Symptoms Observed
- Service-ASW displayed OSPF error messages
- This error was displayed on Service-ASW **See Below**

<img width="946" height="127" alt="SASW-area-mismatch" src="https://github.com/user-attachments/assets/fb6431ac-4cb3-4ee0-a062-32fb357fad75" />

---

## 🔍 Troubleshooting Steps Taken
- 1️⃣ Ran show ip protocols on DSW1 and Service-ASW to see the networks I enabled OSPF on
- 2️⃣ Checked the Port-Channel interface status (up/up)
- 3️⃣ Compared OSPF **area numbers** for the 10.255.2.0/30 network on DSWS1 and DSW2 (See Below)

<img width="799" height="259" alt="DSW1-ip-protocols" src="https://github.com/user-attachments/assets/b9675652-40f3-4c2d-b35a-a16f7d6cf39b" />

<img width="721" height="224" alt="Service-ASW-ip-protocols" src="https://github.com/user-attachments/assets/be4850a6-8601-4cb3-a4ce-1aafcf4bd953" />

---

## 🛠 Root Cause
The **10.255.2.0/30** network was configured as:
- **Area 0** on **DSW1**
- **Area 1** on **Service-ASW**

This caused an **OSPF area mismatch**, preventing the devices from forming an adjacency.

---

## ✅ Resolution

#### 1️⃣ Removed the incorrect OSPF network statement on DSW1:

```bash
no network 10.255.2.0 0.0.0.3 area 0
```

#### 2️⃣ Reconfigured the network in the correct OSPF area:

```bash
network 10.255.2.0 0.0.0.3 area 1
```

After correcting the area number, OSPF adjacency successfully formed.

## 🧪 Verification

- OSPF neighbor state changed to **FULL**
- Service-ASW transitioned from **LOADING** to **FULL**

<img width="923" height="91" alt="SASW-resolved" src="https://github.com/user-attachments/assets/d741b646-74f7-48f4-a66e-799e75e990e2" />

<img width="737" height="99" alt="DSW1-resaolved" src="https://github.com/user-attachments/assets/77b3a44b-c843-41e7-b27c-e6294a026b7d" />




