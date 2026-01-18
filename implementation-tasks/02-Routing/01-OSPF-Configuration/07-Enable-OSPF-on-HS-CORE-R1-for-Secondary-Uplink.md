# 🌐 07 Enable OSPF on HS CORE R1 for Secondary Uplink

## 📌 Overview

I this task, I will enable **OSPF on HS-CORE-R1 and HS-CORE-FW1** for the **new secondary point-to-point link** connecting the **core router to the core firewall**.  

The purpose of this step is to ensure the newly added internal link is **advertised within the hospital**.

⚠️ **Important:**  
I will not enable OSPF toward ISP1.  
This configuration applies **only to the internal firewall-to-core router link**.

## Reference Topology

<img width="968" height="310" alt="reference-topology" src="https://github.com/user-attachments/assets/87fc634c-6ce6-49ac-b1c1-fa64cdf7a90a" />

---

## 🎯 Objectives

- Enable OSPF on **HS-CORE-R1** and **HS-CORE-FW1**
- Advertise the **secondary core firewall P2P network**
- Maintain strict separation between **internal routing** and **ISP connectivity**

---


