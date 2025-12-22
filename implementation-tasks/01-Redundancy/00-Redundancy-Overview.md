# 🔁 01 – Redundancy Overview

This document explains how **redundancy** is implemented across the
**access, distribution, and core layers** of the hospital network.

The goal of this design is to **eliminate single points of failure** and ensure
continuous connectivity for critical hospital services.

---

## 🏗️ Redundancy Design Summary

The hospital network follows a **hierarchical campus design** with redundancy
built into each layer:

- Redundant uplinks at the **Access layer**
- Dual Distribution Switches
- Redundant paths from Distribution to the **Core Router (HS-CORE-R1)**

This layered approach ensures the network can tolerate **link failures** and
**device failures** without service interruption.

---

