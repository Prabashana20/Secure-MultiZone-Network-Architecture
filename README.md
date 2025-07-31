# Secure Multi-Zone Network Architecture (Cisco Packet Tracer)

## 📘 Overview

This project is a simulation of a secure enterprise network environment using **Cisco Packet Tracer**. The network is segmented into multiple departments and zones, each with specific access permissions, secured routing, centralized authentication, and network management features.

It demonstrates key enterprise network concepts including:
- OSPFv2 Dynamic Routing
- Secure Time Synchronization (NTP)
- Centralized Authentication (TACACS+)
- Port Security Policies
- Remote Device Management
- Access Control using ACLs

---

## 🖥️ Topology Summary

| Network/Zone       | IP Range            | Purpose                   |
|--------------------|---------------------|---------------------------|
| HR Department      | 192.168.10.0/24     | Network A                 |
| Sales Department   | 192.168.20.0/24     | Network B                 |
| R&D Department     | 192.168.30.0/24     | Network C                 |
| Finance Department | 192.168.40.0/27     | Network D                 |
| Marketing Dept     | 192.168.40.32/27    | Network E                 |
| QA Team            | 192.168.40.64/27    | Network F                 |
| R1 ↔ R2 Link       | 192.168.1.0/30      | Network G                 |
| R1 ↔ R3 Link       | 192.168.1.4/30      | Network H                 |
| NTP/TACACS+ Server | 192.168.5.8/29      | Network I                 |
| Admin PCs          | 192.168.5.16/29     | Network J                 |
| Web Server         | 192.168.5.0/29      | Network K                 |

---

## 🌐 Routers and Switches

| Device         | Hostname         | Connected Networks |
|----------------|------------------|--------------------|
| Router 1       | CoreRouter_R1    | J, K, I            |
| Router 2       | BranchRouter_R2  | A, B, C            |
| Router 3       | BranchRouter_R3  | D, E, F            |
| Switch 1       | SecureSW_SW1     | Servers/Admin PC   |
| Switch 2       | AccessSW_SW2     | A, B, C            |
| Switch 3       | AccessSW_SW3     | D, E, F            |

---

## ✅ Configuration Tasks Completed

### 1. 🧱 Topology Creation
- Designed 3-router, 3-switch topology with 9 IP subnets.
- All devices appropriately labeled and connected.

### 2. 📡 IP Addressing
- Used the **first usable IP address** for each router interface.
- Static IP configuration for servers and Admin PC.

### 3. 🔐 OSPFv2 Routing
- Enabled OSPFv2 on all routers.
- Each router advertises its connected networks securely.

### 4. 📶 Connectivity Test
- Verified full device-to-device communication.
- Sent PING from **HR-PC** (Network A) to all other devices.

### 5. ⏰ NTP Server
- Configured secure **NTP server** in Network I.
- Synchronized time across all routers and switches.
- Screenshots of correct timestamps are included.

### 6. 🧑‍💻 TACACS+ Secure Management
- Configured centralized login via TACACS+ server (Network I).
- Enabled **AAA model**, used login method `tacacs+`.

### 7. 🔒 Port Security
- **Switch 1**: Static MAC bindings for Servers and Admin PC. Ports set to shutdown on violation.
- **Switch 2 & 3**: Allowed 2 dynamic MAC addresses. Violation action set to restrict.

### 8. 🌍 Web Access Control
- Networks A, B, D, E can access the **Web Server** only.
- Verified using **extended ACLs** on R1.

### 9. 🔐 Isolated Communication
- Networks C and F can **only communicate with each other**.
- Denied all other communication with ACL rules.

---

## 📂 Project Folder Structure

