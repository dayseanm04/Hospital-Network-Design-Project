# 🌐 04 – Update NAT ACL to Exclude Internal Servers

##  Overview

In this task I will exclude the internal server VLAN hosts from NAT translation.

## Reference Toplogy

<img width="977" height="463" alt="topology" src="https://github.com/user-attachments/assets/1a6a6992-db35-4fa8-b6c6-58d28caec93d" />

##  Internal Server VLAN

**Server VLAN:** 10.10.10.0/27

| Server | IP Address (Static) | Function |
|--------|------------|----------|
| DHCP-SRV | 10.10.10.2 | DHCP Services |
| NTP-SRV | 10.10.10.3 | Time Synchronization |
| SYSLOG-SRV | 10.10.10.4 | Log Collection |

These infrastructure servers must NOT be translated by NAT.

---

### Configuration Steps for HS-EDGE-R1 and HS-EDGE-R2  

Enter global configuration mode:

### Add Server Deny Entries

```bash
ip access-list standard Translate-NAT
41 deny host 10.10.10.2
42 deny host 10.10.10.3
43 deny host 10.10.10.4
```

##  Verification

On HS-EDGE-R1 show ip access-list Translate-NAT

<img width="659" height="350" alt="1" src="https://github.com/user-attachments/assets/3bece482-7690-41e6-8f89-f4e2882671c4" />

