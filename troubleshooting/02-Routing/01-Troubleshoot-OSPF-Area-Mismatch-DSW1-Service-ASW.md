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
1️⃣ Ran show ip protocols on DSW1 and Service-ASW to see the networks I enabled OSPF on
2️⃣ Checked the Port-Channel interface status (up/up) 
3️⃣ Compared OSPF **area numbers** for the 10.255.2.0/30 network on DSWS1 and DSW2 (See Below)

<img width="799" height="259" alt="DSW1-ip-protocols" src="https://github.com/user-attachments/assets/b9675652-40f3-4c2d-b35a-a16f7d6cf39b" />

<img width="721" height="224" alt="Service-ASW-ip-protocols" src="https://github.com/user-attachments/assets/be4850a6-8601-4cb3-a4ce-1aafcf4bd953" />
