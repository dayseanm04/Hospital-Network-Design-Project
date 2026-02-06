# 🌐 Configure OSPF Between ISP1 and ISP2 Routers

In this task, I will configure **OSPF** between **ISP1-R1** and **ISP2-R1** so both ISP routers can dynamically exchange routing information.  

## 🎯 Objectives

- ✅ Configure a loopback interface on ISP2-R1
- ✅ Enable OSPF process **10** on both ISP routers
- ✅ Advertise the **point-to-point link** between ISP1 and ISP2
- ✅ Verify OSPF neighbor adjacency

## Reference Topology

<img width="416" height="332" alt="topology " src="https://github.com/user-attachments/assets/de2bfd6c-08cc-43be-ab4b-e4fa5ed49180" />

## 🔗 OSPF-Enabled Networks

### 📡 Point-to-Point Link (ISP1-R1 ↔ ISP2)

| Network | Wildcard Mask | Area |
|---|---|---|
| 10.50.50.0 | 0.0.0.3 | Area 0 |

### 🖧 Loopback Network (ISP2-R1 Only)

| Network | Wildcard Mask | Area |
|---|---|---|
| 10.10.10.20 | 0.0.0.0 | Area 0 |

---

