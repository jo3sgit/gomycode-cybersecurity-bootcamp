# Checkpoint 5 — Security Program Management & Penetration Testing Lab

## Overview

This checkpoint covers compliance standards relevant to penetration testing, hands-on IoT device discovery using Shodan, and vulnerability research using CVE and the NIST National Vulnerability Database (NVD).

---

## Question 1 — Compliance-Based Penetration Testing Domains

**List and briefly describe at least three major compliance standards.**

### GDPR (General Data Protection Regulation)
A comprehensive EU law governing the processing of personal data for EU residents globally. It gives individuals control over their data and requires organizations to:
- Have a lawful basis for processing personal data
- Implement strong security measures
- Report breaches within **72 hours**
- Respect user rights (access, correction, deletion)

**Penalty for non-compliance:** Up to **€20 million** or **4% of global annual turnover** — whichever is higher.

---

### HIPAA (Health Insurance Portability and Accountability Act)
A U.S. law protecting sensitive health information (PHI) from unauthorized disclosure. It applies to healthcare providers, insurers, and business associates. HIPAA mandates:
- Administrative, physical, and technical safeguards
- Controls for medical data confidentiality, integrity, and availability
- Secure access controls and transmission

**Penalty for non-compliance:** Significant financial penalties and potential criminal charges.

---

### PCI DSS (Payment Card Industry Data Security Standard)
An industry standard for organizations that store, process, or transmit payment card information. Its goal is to reduce card fraud through strict security controls. Requirements include:
- Secure networks and data encryption
- Regular security testing
- Strong access control around cardholder data

**Note:** PCI DSS is not a government regulation, but non-adherence can result in fines, increased processing fees, and loss of card processing ability.

---

## Question 2 — IoT Device Discovery Using Shodan

### Lab Tasks

**Step 1 — Created a Shodan account and obtained an API key.**

> Screenshots of account creation and API key retrieval are included in the `/screenshots` folder.

---

**Step 2 — Used Shodan to search for vulnerable IoT devices.**

**Selected IP:** `128.214.11.7`  
**Organization:** University of Helsinki, Finland  
**Server:** Apache/2.4.38 (Debian) | PHP/7.4.1

**Open Ports Discovered:**

| Port | Service |
|------|---------|
| 80 | HTTP |
<img width="2484" height="890" alt="Checkpoint 6_ Security Program Management and Penetration Testing Lab_page-0001" src="https://github.com/user-attachments/assets/06d43ecf-533e-45e5-b66d-f4f2332cda38" />

---

### Why Open Ports Matter in Penetration Testing

Knowing which ports are open on a device is a critical first step in any penetration test or security assessment because:

- **Open ports = potential attack surface.** Each open port represents a running service that could have known vulnerabilities.
- **Port 80 (HTTP)** means the device is serving unencrypted web traffic, making it susceptible to man-in-the-middle (MitM) attacks and traffic interception.
- **Service fingerprinting** (e.g., knowing it runs Apache 2.4.38 and PHP 7.4.1) allows an attacker or tester to look up known CVEs for those specific versions.
- In a pentest, this information directly informs which exploits to attempt during the exploitation phase.
<img width="2484" height="3509" alt="Checkpoint 6_ Security Program Management and Penetration Testing Lab_page-0002" src="https://github.com/user-attachments/assets/3c77de04-03e0-4848-9f64-de1f5f500908" />

---

## Question 3 — Vulnerability Research Using CVE & NVD

### CVE-2021-41617 — OpenSSH Privilege Escalation

**Lab Task:** Research CVE-2021-41617 using the official CVE website and NIST NVD.
<img width="2484" height="1019" alt="Checkpoint 6_ Security Program Management and Penetration Testing Lab_page-0003" src="https://github.com/user-attachments/assets/6c82d50c-bcb1-4f6d-ba40-c6eff6e699d1" />

---

**What versions of OpenSSH are affected?**  
OpenSSH **6.2 through 8.x before 8.8**
<img width="2484" height="1112" alt="image" src="https://github.com/user-attachments/assets/9d0b5cd0-ddcb-410c-aff9-5079cb0dd270" />

---

**When was this CVE last updated on the CVE website?**  
**2023-12-26**

---

**What is the CVSS v3.x Base Score according to the NVD?**  
**7.0 — HIGH**

> Vector: `CVSS:3.1/AV:L/AC:H/PR:L/UI:N/S:U/C:H/I:H/A:H`
<img width="2484" height="1010" alt="Checkpoint 6_ Security Program Management and Penetration Testing Lab_page-0004" src="https://github.com/user-attachments/assets/22817dc0-b704-4ca3-a650-bcf6f65aa436" />

---

**What is the vulnerability description (CWE)?**

When certain non-default configurations are used in OpenSSH 6.2–8.x before 8.8, the `sshd` daemon allows **privilege escalation** because supplemental groups are not initialized as expected. Helper programs for `AuthorizedKeysCommand` and `AuthorizedPrincipalsCommand` may run with privileges associated with the group memberships of the `sshd` process, if the configuration specifies running the command as a different user.

**CWE Category:** Improper Privilege Management

---

## Tools & Resources Used

- **Shodan** — Internet-connected device discovery and IoT vulnerability search
- **CVE (cve.org)** — Common Vulnerabilities and Exposures database
- **NVD (nvd.nist.gov)** — NIST National Vulnerability Database for CVSS scoring
- **MITRE Corporation** — CVE Program CNA

---

## Key Takeaways

- Compliance standards like GDPR, HIPAA, and PCI DSS define the legal and regulatory context in which penetration testing must operate.
- Shodan is a powerful OSINT tool that exposes internet-facing devices, open ports, and running services — exactly the recon data an attacker would gather.
- CVE and NVD are essential references for understanding the severity, scope, and patch status of known vulnerabilities.
- A CVSS score of 7.0 (HIGH) on CVE-2021-41617 means it should be prioritized for patching in any production environment running the affected OpenSSH versions.
