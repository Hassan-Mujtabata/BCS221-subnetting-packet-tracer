# 🌐 BCS221-subnetting-packet-tracer

> CIDR-based subnetting design and full network implementation in Cisco Packet Tracer with dynamic routing — built for BCS 221 Computer Networks at Canadian University Dubai.

---

## 📌 Overview

This project was built for **BCS 221 – Computer Networks** at Canadian University Dubai. The task simulates a real-world scenario: designing a scalable IP addressing scheme for a growing organization with multiple departments, then implementing it as a fully functional network in Cisco Packet Tracer.

The IP block was divided into **12 subnets** using **CIDR /25**, each supporting up to **126 usable hosts**, interconnected via routers configured with a **dynamic routing protocol (RIP)**.

---

## 🗂️ Project Structure

```
BCS221-subnetting-packet-tracer/
│
├── project_communication.pkt     # Cisco Packet Tracer full network implementation
├── report/
│   └── BCS221_Project_Report.pdf # Full report with subnet tables, configs & screenshots
└── README.md
```

---

## 🧮 Subnet Design

| Parameter | Value |
|---|---|
| Total Subnets Required | 12 |
| Minimum Hosts per Subnet | 98 |
| Chosen Block | `172.16.0.0/21` (Class B) |
| Subnet Mask | `255.255.255.128` (/25) |
| Total IPs per Subnet | 128 |
| Usable Hosts per Subnet | 126 |
| Total IPs Required | 12 × 128 = 1,536 |

**Why Class B /25?**  
98 hosts per subnet rules out Class C (max 254 hosts per network, not enough subnets). A /25 block gives 128 IPs per subnet — the smallest power of 2 above 98 — minimizing wasted addresses across all 12 subnets.

---

## 📋 Subnet Addressing Table

| Subnet | Subnet Address | First Usable IP | Last Usable IP | Broadcast |
|---|---|---|---|---|
| Subnet 1 (HR) | 172.16.0.0 | 172.16.0.1 | 172.16.0.126 | 172.16.0.127 |
| Subnet 2 (IT) | 173.16.0.0 | 173.16.0.1 | 173.16.0.126 | 173.16.0.127 |
| Subnet 3 (Research) | 174.16.0.0 | 174.16.0.1 | 174.16.0.126 | 174.16.0.127 |
| Subnet 4 (Finance) | 175.16.0.0 | 175.16.0.1 | 175.16.0.126 | 175.16.0.127 |
| Subnet 5 (Operations) | 176.16.0.0 | 176.16.0.1 | 176.16.0.126 | 176.16.0.127 |
| Subnet 6 (Marketing) | 177.16.0.0 | 177.16.0.1 | 177.16.0.126 | 177.16.0.127 |
| Subnet 7 (Legal) | 178.16.0.0 | 178.16.0.1 | 178.16.0.126 | 178.16.0.127 |
| Subnet 8 (Admin) | 179.16.0.0 | 179.16.0.1 | 179.16.0.126 | 179.16.0.127 |

---

## 🖧 Network Topology

- **5 routers** interconnected via serial links (`/30` point-to-point subnets)
- **2+ PCs per subnet** as end devices
- **Dynamic routing:** RIP configured on all routers
- **Connectivity verified** via ping tests and `show ip route` across all subnets

### Router Interface Summary

| Device | Interface | IP Address | Subnet Mask |
|---|---|---|---|
| Router1 | se0/1/0 | 192.168.0.1 | 255.255.255.252 |
| Router1 | fa0/1 | 172.16.0.1 | 255.255.255.128 |
| Router2 | se0/0/0 | 192.168.0.2 | 255.255.255.252 |
| Router2 | se0/1/0 | 192.168.0.5 | 255.255.255.252 |
| Router2 | fa0/1 | 173.16.0.1 | 255.255.255.128 |
| Router3 | se0/1/0 | 192.168.0.6 | 255.255.255.252 |
| Router3 | fa0/0 | 174.16.0.1 | 255.255.255.128 |
| Router3 | se0/0/0 | 192.168.0.9 | 255.255.255.252 |
| Router4 | se0/0/0 | 192.168.0.10 | 255.255.255.252 |
| Router4 | fa0/1 | 175.16.0.1 | 255.255.255.128 |
| Router5 | fa0/0 | 192.168.0.14 | 255.255.255.252 |
| Router5 | fa0/1 | 176.16.0.1 | 255.255.255.128 |

---

## 🚀 How to Open

1. Install **Cisco Packet Tracer** (available free via [Cisco NetAcad](https://www.netacad.com/))
2. Clone this repository:
```bash
git clone https://github.com/Hassan-Mujtabaa/BCS221-subnetting-packet-tracer.git
```
3. Open `project_communication.pkt` in Cisco Packet Tracer
4. Use the **Simulation mode** to observe packet flow between subnets
5. Click any router → CLI to view routing tables with `show ip route`

---

## ✅ Verification

Connectivity was verified using:
- `ping` between PCs in different subnets
- `show ip route` on all routers to confirm RIP propagation
- `tracert` to trace packet paths across subnets

---

## 👥 Team

| Student | ID | Role |
|---|---|---|
| **Hassan Mujtaba** | 20220002085 | Subnet design, CIDR calculations, router configuration |
| **Yasmin** | 20230003798 | Packet Tracer topology, RIP setup, router configuration |
| **Maryam** | 20220002536 | Connectivity testing, screenshots, final report |

---

## 🏫 Course Information

**BCS 221 – Computer Networks**  
School of Engineering, Applied Sciences, and Technology  
Canadian University Dubai — Spring 2024–25

---

## ⚠️ Notes!

- Subnetting parameters were derived from group member student IDs per the project specification
- The `.pkt` file requires Cisco Packet Tracer version 8.0 or later
- All router configurations are documented in the project report with annotated screenshots
