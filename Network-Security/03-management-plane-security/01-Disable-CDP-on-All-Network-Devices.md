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

## 🔍 Check CDP on DSW1

```bash
show cdp neighbors
```

<img width="803" height="171" alt="DSW1-show-cdp" src="https://github.com/user-attachments/assets/a75f8a6e-0131-419c-99b7-fa39200663e9" />

## ⚙️ Disable CDP (Apply on All Network Devices)

#### 🟢 Enter global configuration mode and disable CDP:

```bash
no cdp run
```

**Note**  This command disables CDP globally on the device, stopping all CDP advertisements and neighbor discovery.

### 🔎 Verification

#### 🟢 After disabling CDP, verify that it is no longer running :

On DSW1

```bash
show cdp
```

<img width="853" height="81" alt="DSW1-CDP-disabled" src="https://github.com/user-attachments/assets/a9c8f107-f434-4f3c-b8fa-36823cf812d0" />

**Note:** I disabled CDP on all network devices in this project, but I only show it on DSW1!
