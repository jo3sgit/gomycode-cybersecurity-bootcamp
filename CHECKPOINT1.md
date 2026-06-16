# Checkpoint 1 — Networking Fundamentals & Lab Setup

## Overview

This checkpoint covers foundational networking concepts using hands-on tools like `ping`, `traceroute`, and `nmap`. It also explores how virtual machine network modes (NAT vs Bridged) affect connectivity, and includes a basic vulnerability scan of a local XAMPP web server.

---

## Questions & Answers

### Q1 — What is Ping and why is it used?

**Ping** checks if a server is live and tests network connectivity.

The IP address `8.8.8.8` (Google's DNS) is commonly used as the target since Google's servers are almost always online, making it a reliable benchmark.

**Objective:** To check for packet loss and measure the TTL (Time To Live) of packets sent across the network.
<img width="2252" height="2276" alt="Checkpoint 1_page-0001" src="https://github.com/user-attachments/assets/14a9dbdb-0611-46c4-b572-7596f84162c6" />


---

### Q2 — What does Traceroute show?

Traceroute shows the number of hops packets take to reach their destination.

- In this lab, **two hops** were observed.
- Each line in the output displays the address of a router/node that the packet passes through before being forwarded to the next hop.
- <img width="2330" height="2152" alt="Checkpoint 1_page-0002" src="https://github.com/user-attachments/assets/6ece0458-e5e9-4d4d-901b-871d3e457025" />


---

### Q3 — Ping results from VM and Host

Ping requests were **successful from both** the virtual machine and the host machine when tested under the same network conditions.
<img width="2550" height="3300" alt="Checkpoint 1_page-0004" src="https://github.com/user-attachments/assets/c9e7eddb-5cee-4583-b339-1fd530c75d2a" />

---

### Q4 — NAT vs Bridged Network Mode (VirtualBox)

| Mode | Ping Result | Reason |
|------|------------|--------|
| NAT | ❌ Unsuccessful | VM gets an IP from the hypervisor's virtual DHCP server — not visible on the LAN |
| Bridged | ✅ Successful | VM gets an IP directly from the LAN's DHCP server — appears as a real device on the network |

**Key Insight:** In NAT mode, the VM is behind a virtual NAT router and cannot be reached from other LAN devices. In Bridged mode, the VM behaves like a physical machine on the network.
<img width="2550" height="3300" alt="Checkpoint 1_page-0005" src="https://github.com/user-attachments/assets/f091e71a-249b-4187-bc0c-4e2c497fbab6" />

---

### Q5 — XAMPP Web Server Access

Successfully reached the XAMPP page while the VM was in **Bridged network mode**.

> **Note:** Windows Firewall was temporarily disabled to allow the connection.
<img width="2550" height="2292" alt="Checkpoint 1_page-0006" src="https://github.com/user-attachments/assets/80a218a9-1748-4dfe-8c47-3c5a6d3befda" />

---

### Q6 — Nmap Scan Results

**Open Ports Detected:**

| Port | Service |
|------|---------|
| 80 / 443 | HTTP / HTTPS |
| 135 | Microsoft RPC |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL/MariaDB |

**Web Server:** Apache HTTPD 2.4.58  
**Database:** MariaDB 10.3.23
<img width="2550" height="3300" alt="Checkpoint 1_page-0008" src="https://github.com/user-attachments/assets/35c64b76-ce0a-4140-910e-7012dd56bb21" />

---

## Tools Used

- `ping` — Connectivity testing
- `tracert` / `traceroute` — Hop analysis
- `nmap` — Port scanning and service detection
- VirtualBox — NAT & Bridged network mode testing
- XAMPP — Local web server setup

---

## Key Takeaways

- NAT mode isolates the VM behind a virtual router; Bridged mode exposes it directly to the LAN.
- Nmap can fingerprint both open ports and running service versions, which is critical for attack surface analysis.
- Basic firewall misconfigurations (like disabling Windows Firewall) can expose a host to unnecessary risk.
