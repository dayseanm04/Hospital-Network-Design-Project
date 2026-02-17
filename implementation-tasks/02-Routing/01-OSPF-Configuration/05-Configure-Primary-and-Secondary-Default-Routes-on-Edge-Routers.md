# 🌐 Configure Primary and Secondary Default Routes on Edge Routers

## 📌 Overview
In this task, I will configure **primary and secondary default routes** on the Hospital **Edge Routers** to  **ISP1**. 

I will configure **ISP1** as the **primary path** and **ISP2** as a **backup path** using administrative distance. I will then  **advertised the default routes into the OSPF domain** so internal devices can reach external networks.

## Reference Topology

<img width="1250" height="622" alt="toplogy" src="https://github.com/user-attachments/assets/4782bc94-0409-4950-85dd-3edb90d04536" />

---

## 🎯 Objective
- Configure a **primary default route** via ISP1
- Configure a **secondary default route** via ISP2 using a higher metric
- Advertise the default routes into the OSPF domain
- Verify default route propagation to access switches

---

## 🖧 Edge Router Default Route Configuration

### 🔵 HS-EDGE-R1 (Primary ISP)

```bash
ip route 0.0.0.0 0.0.0.0 69.45.12.1 1
```

### 🔵 HS-EDGE-R2 (Secondary ISP)

```bash
ip route 0.0.0.0 0.0.0.0 100.45.12.1 50
```

Note: A higher administrative distance ensures ISP2 is only used if the primary route becomes unavailable.

## 🔁 Advertise Default Route into OSPF

### ♦️ On the Edge Routers (Area 0 – Backbone)

On HS-EDGE-R1 and HS-EDGE-R2:

```bash
router ospf 10
 default-information originate
```

## 🔍 Verification

#### show ip route on HS-EDGE-R1

<img width="970" height="511" alt="HS-EDGE-R1" src="https://github.com/user-attachments/assets/bc1d588c-c492-451c-a037-de81789aec1f" />

#### show ip route on HS-EDGE-R2

<img width="913" height="472" alt="HS-EDGE-R2" src="https://github.com/user-attachments/assets/c904fb2f-c4af-4b88-a325-7b280269fc08" />

#### show ip route | include 0.0.0.0 on HS-CORE-FW1

<img width="1027" height="479" alt="Core-1" src="https://github.com/user-attachments/assets/6ad833a8-0b81-4684-9fc2-4fa220d43748" />

#### show ip route | include 0.0.0.0 on HS-CORE-FW2

<img width="1031" height="474" alt="Core-2" src="https://github.com/user-attachments/assets/16df8310-9e3c-417a-8419-ba92068c5458" />

#### show ip route | include 0.0.0.0 on DSW1

<img width="847" height="99" alt="DSW1" src="https://github.com/user-attachments/assets/86037350-a45a-4304-9f92-a689ca076cc9" />

#### show ip route | include 0.0.0.0 on DSW2

<img width="788" height="97" alt="DSW2" src="https://github.com/user-attachments/assets/815799b5-9791-44c5-81a2-22334984f266" />

#### show ip route | include 0.0.0.0 on the Access switches

<img width="712" height="101" alt="F1-ASW1" src="https://github.com/user-attachments/assets/9b449c47-bc57-4779-bb40-953351a7db3c" />

<img width="773" height="98" alt="F1-ASW2" src="https://github.com/user-attachments/assets/c354f9d9-61ea-4750-b7df-c3d84a8e6ce3" />
