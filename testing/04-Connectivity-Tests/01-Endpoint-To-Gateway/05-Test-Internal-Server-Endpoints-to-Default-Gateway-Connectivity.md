# Test – Internal Server Endpoints to Default Gateway Connectivity

## Purpose
This test verifies that **Hospital internal servers** can successfully reach their **default gateway** within the Servers VLAN.

> These servers provide critical network services.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

## Internal Servers VLAN Overview

| Server Name | Service Role | VLAN ID | Subnet | Default Gateway | Connected Switch |
|------------|-------------|--------|--------|----------------|------------------|
| DHCP-SRV | DHCP Server | VLAN 700 | 10.10.10.0/27 | 10.10.10.1 | Service-ASW |
| NTP-SRV | NTP Server | VLAN 700 | 10.10.10.0/27 | 10.10.10.1 | Service-ASW |
| SYSLOG-SRV | Syslog Server | VLAN 700 | 10.10.10.0/27 | 10.10.10.1 | Service-ASW |

---

## Test – Internal Services VLAN (VLAN 700)

**Devices Tested**
- **DHCP-SRV**
- **NTP-SRV**
- **SYSLOG-SRV**

**Test Command**

```bash
ping 10.10.10.1
```

### DHCP-SRV ping was successful ✅

<img width="876" height="486" alt="DHCP-SRV" src="https://github.com/user-attachments/assets/e95c2367-5c25-4c43-a930-04d890118cb8" />

### NTP-SRV ping was successful ✅

<img width="877" height="461" alt="NTP-SRV" src="https://github.com/user-attachments/assets/821ac205-cb2c-4747-a7e0-947e89b31db2" />

### SYSLOG-SRV ping was successful ✅

<img width="875" height="479" alt="SYSLOG-SRV" src="https://github.com/user-attachments/assets/5ca86988-de9a-466a-893a-84c3a10dd935" />
