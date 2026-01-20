# 🧭 Configure OSPF Between ISP1 and INET Network

## 📌 Overview

In this task, I will configure **OSPF process 10 (Area 0)** between the **ISP1-R1** and the **INET network** so routing information can be exchanged dynamically.

I will also:
- Create **Loopback0** interfaces on both devices (for stable router IDs/testing)
- Enable **OSPF Area 0** on the INET uplink and INET server subnet
- Configure a **default route on ISP1**
- Advertise the default route into OSPF using **default-information originate**

---
