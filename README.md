# 🌐 Enterprise Network Design — Cisco Packet Tracer

> Scalable, redundant enterprise network with Layer 3 Inter-VLAN Routing, VLSM addressing, and Rapid-PVST+ loop prevention.

---

## 📋 Project Overview

This project demonstrates the design and implementation of a two-department enterprise network built in **Cisco Packet Tracer**. The topology supports a **Sales** and **Production** department with full network isolation, optimized IP addressing, and high availability through physical redundancy.

---

## 🏗️ Network Topology

```
                        [PC0]
                          |
                      [Switch0] ──────────── [SAP Server - VLAN 10]
                        / |
[Multilayer Switch2] ── [Switch1] ──────── [PC1]
                        \ |
                      [Switch2] ──────────── [MSSQL Server - VLAN 20]
```

**Core Layer:** Cisco 3560-24PS Multilayer Switch (Inter-VLAN Routing)  
**Access Layer:** 3× Cisco 2960 Switches

---

## 📡 IP Addressing (VLSM)

| Department  | VLAN | Subnet              | Usable Hosts | Required |
|-------------|------|---------------------|--------------|----------|
| Sales       | 10   | 192.168.10.0/25     | 126          | 100      |
| Production  | 20   | 192.168.20.0/23     | 510          | 300      |

---

## ⚙️ Key Technologies

| Feature                  | Detail                              |
|--------------------------|-------------------------------------|
| Inter-VLAN Routing       | Layer 3 on Multilayer Switch        |
| Loop Prevention          | Rapid-PVST+ (`spanning-tree mode rapid-pvst`) |
| Trunk Links              | IEEE 802.1Q between all switches    |
| Redundancy               | Dual uplinks per Access Switch      |
| Address Optimization     | VLSM (Variable Length Subnet Masking) |

---

## 🖥️ Servers

| Server               | VLAN | Role                        |
|----------------------|------|-----------------------------|
| Server0              | 10   | SAP Business One App Server |
| Server1              | 20   | MSSQL Database Server       |

---

## ✅ Verification

Connectivity tested via ICMP ping across VLANs:

- **PC0 → PC1** (VLAN 10 → VLAN 20): ✅ Successful
- First packet drop is expected behavior due to ARP resolution — not a configuration error.

---

## 🚀 How to Open

1. Install **[Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer)** (v8.0+ recommended)
2. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   ```
3. Open `Monitoring_of_Computer_System_Security_project.pkt` in Packet Tracer

---

## 📚 Concepts Covered

- VLAN segmentation and trunking
- VLSM subnetting
- Layer 3 Inter-VLAN Routing
- Rapid Spanning Tree Protocol (Rapid-PVST+)
- Physical redundancy and failover
- Enterprise hierarchical network design

---

## 🛠️ Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI

---

*This project was developed as part of a Computer System Security Monitoring course.*
