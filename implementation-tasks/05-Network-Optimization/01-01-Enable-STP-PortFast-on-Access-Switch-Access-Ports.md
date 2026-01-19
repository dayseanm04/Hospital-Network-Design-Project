# ⚡ 01 – Enable STP PortFast on Access Switch Access Ports

In this task, I enabled **Spanning Tree Protocol (STP) PortFast** on **access switch ports connected to end devices** (PCs, printers, etc.).  

PortFast allows access ports to transition immediately to the **forwarding state**, improving **end-device connectivity time** and overall network performance.

---

## 🎯 Objective

- ✅ Enable STP PortFast on all **access switch access port connected to PCs and Printers**
- ✅ Reduce STP convergence delay for user devices
- ✅ Apply configuration consistently across all access switches
  
## Reference Topology

<img width="790" height="168" alt="reference-topology" src="https://github.com/user-attachments/assets/d5aae7b9-f6a8-4cab-a4a8-fe3716da2529" />

---


## 🧠 Scope of Configuration

I enabled PortFast on the following **Access Layer switches**:

- `F1-ASW1`
- `F1-ASW2`
- `F2-ASW1`
- `F2-ASW2`
- `F3-ASW1`
- `F3-ASW2`

