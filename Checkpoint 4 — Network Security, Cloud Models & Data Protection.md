# Checkpoint 4 — Network Security, Cloud Models & Data Protection

## Overview

This checkpoint covers defensive strategies across servers, endpoints, and networks. It also addresses cloud service models, zero-trust architecture, firewall vs IDS vs IPS distinctions, data classification, and backup & resilience strategies.

---

## Questions & Answers

### Q1 — Hardening Strategies Across the Infrastructure

#### Server Hardening
- Implement a **Web Application Firewall (WAF)**
- Set up **regular automated backups**
- Secure remote access using **VPNs** and **jump boxes** for administrative access

#### Endpoint / Host Hardening
- Implement **phishing-resistant MFA**
- Conduct regular **user security awareness training**
- Enforce **full disk encryption**
- Apply **application allowlisting** to prevent unauthorized software from executing

#### Network Hardening
- Apply **network segmentation** to isolate critical systems
- Require a **VPN or Zero-Trust Network Access (ZTNA)** for all remote connections

---

### Q2 — Cloud Service Models

| Model | Full Name | What's Managed by the Provider |
|-------|-----------|-------------------------------|
| **IaaS** | Infrastructure as a Service | Hardware, networking, virtualization |
| **PaaS** | Platform as a Service | Infrastructure + OS + runtime |
| **SaaS** | Software as a Service | Everything — just use the app |

**XAMPP Use Case:**  
XAMPP is best suited to **IaaS** in a cloud context. Since XAMPP is a pre-configured software bundle that requires OS-level control (Apache, MySQL, PHP, Perl), IaaS gives the same level of control over the underlying infrastructure needed to configure and run it correctly.

---

### Q3 — Zero-Trust Zones

The network zones described — where no user or device is trusted by default regardless of location — are called **Zero-Trust Zones**.

> In Zero-Trust architecture, every access request is verified explicitly, least-privilege access is enforced, and breach is always assumed.
<img width="1536" height="1024" alt="img7" src="https://github.com/user-attachments/assets/afeb8cd3-fba7-4835-a123-a0f0856930e9" />

---

### Q4 — Firewall vs IDS vs IPS

| Tool | Role | Type |
|------|------|------|
| **Firewall** | Operates using rules that define what traffic is allowed or denied through the network | Preventative |
| **IDS** (Intrusion Detection System) | Detects and alerts on threats that have **already entered** the system | **Detective** |
| **IPS** (Intrusion Prevention System) | Actively scans and **blocks** threats before they access the network | **Preventative** |

**Key distinction:** An IDS watches and warns; an IPS watches and acts.

---

### Q5 — Data Classification Levels

Standard data classification levels used in enterprise security:

1. **Public** — No restrictions; freely shareable
2. **Private** — Internal use only; not for public disclosure
3. **Sensitive** — Requires careful handling; limited distribution
4. **Confidential** — Restricted to specific teams; business-critical
5. **Restricted** — Tightly controlled; regulatory or legal implications
6. **Critical** — Highest sensitivity; severe impact if disclosed

**Applied scenario:**  
In the given scenario, data was classified as **Confidential** and **Restricted**.

**Security measures applied:**
- Encrypt data using robust encryption standards
- Conduct regular **security awareness training** on handling sensitive information
- Grant access **only to HR professionals**, not directly to managers
- Deploy **Data Loss Prevention (DLP)** tools to monitor and block sensitive data from leaving the corporate network (e.g., blocking outbound emails containing credit card numbers)

---

### Q6 — Backup vs Resilience

| Concept | Definition |
|---------|-----------|
| **Backup** | The process of creating copies of data so it can be restored after loss or corruption |
| **Resilience** | A strategy ensuring **continuous system operation**, uptime, and rapid recovery during disruptions |

#### Backup Techniques & Tools

**Techniques:**
- Incremental backups
- Full backups
- Differential backups

**Tools:**
- Google Drive
- OneDrive

#### Resilience Techniques

- **Load balancing** — Distributes traffic across multiple servers to prevent single points of failure
- **Cloud data replication** — Copies data across geographic regions
- **Data sovereignty** — Ensuring data is stored and processed within legal jurisdictions
- **Platform diversity** — Using multiple platforms/vendors to avoid over-reliance on one system

---

## Key Takeaways

- Defense-in-depth means hardening at every layer — server, endpoint, and network.
- IaaS is the right cloud model when you need OS-level control over your stack.
- Zero-Trust means never trust, always verify — regardless of whether traffic is internal or external.
- IDS detects; IPS prevents — both are needed in a mature security architecture.
- Data classification drives access control and DLP policy decisions.
- Resilience goes beyond backups — it ensures systems stay operational even during incidents.
