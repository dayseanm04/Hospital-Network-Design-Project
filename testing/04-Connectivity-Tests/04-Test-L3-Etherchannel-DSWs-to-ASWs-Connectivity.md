# ✅ Test – L3 EtherChannel Connectivity (DSWs To ASWs)

This test validates **Layer 3 (routed) EtherChannel connectivity** between **DSW1 and DSW2**.
This test is to verify that:

- LACP formed the Port-Channel correctly
- The Port-Channel is operating as a **Layer 3 routed link**
- End-to-end connectivity works across the EtherChannel

## Reference Test Area

<img width="684" height="415" alt="test-area" src="https://github.com/user-attachments/assets/39a09217-792d-4f84-9713-e378c4bf8496" />

---

## 🧪 Connectivity Tests (Ping)

### F1-ASW1 pings DSW1 Po1 and DSW2 Po1

<img width="728" height="291" alt="F1-ASW1-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/0b072f55-049c-459e-9c1e-15efb6f3849e" />

### F1-ASW2 pings DSW1 Po2 and DSW2 Po2

<img width="706" height="277" alt="F1-ASW2-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/601af65d-f2e7-49c2-a5a3-d8396b9b0c72" />

### F2-ASW1 pings DSW1 Po3 and DSW2 Po3

<img width="809" height="268" alt="F2-ASW1-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/bdea6196-5d3f-4f38-a2b5-3f9d95c85113" />

### F2-ASW2 pings DSW1 Po4 and DSW2 Po4

<img width="738" height="270" alt="F2-ASW2-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/9aa52f21-c575-4278-b008-ebc88a7d555a" />

### F3-ASW1 pings DSW1 Po5 and DSW2 Po5

<img width="773" height="294" alt="F3-ASW1-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/5c0e298c-a5ba-470b-b268-fdfe370f13db" />

### F3-ASW2 pings DSW1 Po6 and DSW2 Po6

<img width="766" height="281" alt="F3-ASW2-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/451e8bb3-a928-49e3-81d7-4f6c515a0f17" />

### Service-ASW pings DSW1 Po7 and DSW2 Po7

<img width="853" height="278" alt="SASW-Port-Channels-Connectivity-Tests" src="https://github.com/user-attachments/assets/94e0b5be-1d20-4b8b-9a3b-dd5d1da8acda" />

### DSW1 pings F1-F3 Po1

<img width="839" height="782" alt="DSW1-F1-F3-PC-pings" src="https://github.com/user-attachments/assets/34ce9e14-322f-44af-a2c1-ec3ec6f8f420" />






