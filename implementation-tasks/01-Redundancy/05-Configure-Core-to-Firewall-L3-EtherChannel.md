# 🔗 Configure Core to Firewall L3 EtherChannel

## 📌 Overview

In this task, I will configure **Layer 3 EtherChannel (static Port-Channel)** between the **Hospital Core device (HS-CORE-R1)** and the **Core Firewall (HS-CORE-FW1)**.

This design removes the **single point of failure** created by a single uplink between the core and firewall. By bundling **two physical links** into one logical link, the hospital core gains:

- ✅ Redundancy (link failover)
- ✅ Higher bandwidth

**📝 Note:** To implement L3 EtherChannel in Cisco Packet Tracer, **I changed the Router to a Layer 3 switch**.

## Reference Topology

<img width="483" height="313" alt="topology" src="https://github.com/user-attachments/assets/959b455c-c96c-459f-8a54-6ca557f24bb3" />

