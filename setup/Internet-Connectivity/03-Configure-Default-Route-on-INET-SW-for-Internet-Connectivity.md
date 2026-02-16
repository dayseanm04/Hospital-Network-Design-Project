# 🌐 Configure Default Route on INET-SW for Internet Connectivity

## 📌 Overview
In this task, I will configure a **default route** on **INET-SW** to enable internet reachability.

The default route forwards all unknown traffic to the upstream ISP router (ISP1-R1).


## 🎯 Objective
- Configure a gateway of last resort on INET-SW
- Sends internet-bound traffic toward ISP1


## 🌍 Network Context

| Device | Role |
|--------|------|
| INET-SW | Internet switch |
| ISP1-R1 | Upstream ISP router |
| Next-Hop IP | 10.30.30.1 (ISP1 Po1) |


## 🔧 Configuration

On **INET-SW**, configure the following static default route:

```bash
ip route 0.0.0.0 0.0.0.0 10.30.30.1
```

## 🔍 Verification

#### show ip route on INET-SW

<img width="922" height="346" alt="route" src="https://github.com/user-attachments/assets/9f4f1c1c-eccc-44b3-8e32-b208e594afd9" />
