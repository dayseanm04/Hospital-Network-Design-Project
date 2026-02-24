#  Enable Routing and Configure Loopback Interfaces

**Purpose:** Configure **Loopback interface** on HS-CORE-R1 Loopback interfaces used for routing, testing, and router IDs for dynamic routing protocols such as OSPF.

---

## Reference Network Diagram

<img width="574" height="256" alt="reference-diagram" src="https://github.com/user-attachments/assets/5e1604d3-8a57-40b3-8934-8825e9c8800a" />



---

## What I will do in this task:
- Configure **Loopback0** interfaces on HS-CORE-R1

---

##  Configure Loopbacks on **HS-CORE-R1**

| HS-CORE-R1 | Loopback IP |
|---|---|
| HS-CORE-R1 | 10.0.0.15/32 |


### Steps

```bash
interface loopback0
ip address 10.0.0.15 255.255.255.255
end
```

---

## Verification

### Verify Loopback Interface

#### On HS-CORE-R1 show ip interface brief | include Loopback

<img width="800" height="85" alt="HS-CORE-R1-Loopback-int" src="https://github.com/user-attachments/assets/faf2cd4d-5ffd-41db-a76b-11b4f5430751" />
