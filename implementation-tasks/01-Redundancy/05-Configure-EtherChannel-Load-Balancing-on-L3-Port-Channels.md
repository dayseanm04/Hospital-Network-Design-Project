# 🔀 Configure EtherChannel Load Balancing on L3 Port-Channels

## 📌 Overview
This task, I will configure **EtherChannel load balancing** for all **Layer 3 Port-Channels** in the network.

The **source–destination IP** load balancing method is used to ensure that packets belonging to the same traffic flow always use the same physical link within the Port-Channel.

## 🎯 Objective
- Configure a consistent load-balancing method across all devices
- Improve bandwidth utilization while maintaining packet order


## Reference Topology

<img width="841" height="636" alt="toplogy2" src="https://github.com/user-attachments/assets/7c8bfb7a-0ada-4f28-b135-b2ca46f41a6a" />

---

## 🔧 Configuration

In Global config mode:

```bash
port-channel load-balance src-dst-ip
```

**Note:** This setting applies globally to all Port-Channels on the device

I ran this command on all of the network device in the hospital LAN except the firewalls because it didnt allow me to! (Cisco Packet Tracer Limitation)
