# 🔗 Configure Core to Firewall L3 EtherChannel

## 📌 Overview

In this task, I will configure **Layer 3 EtherChannel (static Port-Channel)** between the **Hospital Core device (HS-CORE-R1)** and the **Core Firewall (HS-CORE-FW1)**.

This design removes the **single point of failure** created by a single uplink between the core and firewall. By bundling **two physical links** into one logical link, the hospital core gains:

