# 🔒 Disable CDP on All Network Devices

In this task, I disabled **Cisco Discovery Protocol (CDP)** on all network devices in the hospital network to improve **security** and reduce **unnecessary control-plane traffic**.

By disabling CDP, devices no longer advertise information such as **hostnames, interface details, and platform types** to neighboring devices, which helps limit information exposure and slightly reduces CPU usage.

## 🎯 Objective

- ✅ Disable CDP globally on all network devices
- ✅ Prevent devices from sharing neighbor information
- ✅ Reduce periodic CDP message exchanges (every 60 seconds by default)

## Rerefencce Topology

<img width="511" height="441" alt="topology" src="https://github.com/user-attachments/assets/55a9fd85-d39d-497b-b7d4-827d5f6fae9e" />

---

## 🧠 Background

- CDP is **enabled by default** on Cisco devices  
- In this project, CDP was enabled on **all network devices except the firewall**

---
