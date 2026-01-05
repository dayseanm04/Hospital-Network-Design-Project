# 🧩 DHCP – Verify DHCP IP Address Assignment Across VLANs

## 📌 Overview

This test verifies that the **DHCP service is functioning correctly across multiple VLANs and floors** in the Hospital Network Design project.

The goal is to confirm that **end devices in different departments automatically receive valid IP addressing information** without manual configuration.

---

## 🎯 Test Objective
Ensure that DHCP clients in various **VLANs and subnets** successfully receive:
- IP address
- Subnet mask
- Default gateway

This confirms that DHCP relay and routing are working correctly across the network.

---

## 🧪 Test Method

### 🔷 For each selected end device:

1. Open the **Command Prompt**
2. Run: **ipconfig /renew**
3. Verify that the device receives an IP address within the correct subnet for its VLAN
