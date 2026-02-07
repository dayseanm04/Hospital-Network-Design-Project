# 🌐 Configure Primary and Secondary Default Routes on Edge Routers

## 📌 Overview
In this task, I will configure **primary and secondary default routes** on the Hospital **Edge Routers** to support **dual ISP connectivity**. 

I will configure **ISP1** as the **primary path** and **ISP2** as a **backup path** using administrative distance. I will then  **advertised the default routes into the OSPF domain** so internal devices can reach external networks.

---

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

### ♦️ Distribution Switches (Area 1)

On DSW1 and DSW2:

```bash
router ospf 1
 default-information originate
```

## 🔍 Verification

