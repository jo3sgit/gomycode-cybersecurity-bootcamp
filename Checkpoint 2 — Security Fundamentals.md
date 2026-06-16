# Checkpoint 2 — Security Fundamentals

## Overview

This checkpoint covers the core building blocks of cybersecurity: the CIA Triad, the AAA framework, types of security controls, symmetric vs asymmetric encryption, and steganography.

---

## Questions & Answers

### Q1 — Types of Security Controls (with real-world examples)

**Managerial Control**
- *Action:* Review login reports of every worker assigned to the server room.
- *Type:* **Detective** — identifies incidents after they occur.

**Operational Control**
- *Action:* Place a guard at the server room entrance, allowing only authorized personnel.
- *Type:* **Preventative** — stops unauthorized access before it happens.

**Technical Control**
- *Action:* Conduct daily backups to a backup server in case the main server goes down.
- *Type:* **Corrective** — restores systems after a failure.

**Physical Control**
- *Action:* Install motion detectors activated when offices are closed; contact law enforcement if triggered.
- *Type:* **Detective + Deterrent** — detects intrusions and discourages bad actors.

---

### Q2 — The CIA Triad & AAA Framework

#### CIA Triad

| Principle | Definition | Example |
|-----------|-----------|---------|
| **Confidentiality** | Only authorized users can access resources | An employee cannot access data outside their department |
| **Integrity** | Data is not tampered with in transit or at rest | A message reaches its recipient exactly as it was sent |
| **Availability** | Systems are accessible when needed | An employee can access company resources at any time |

#### AAA Framework

| Principle | Definition | Example |
|-----------|-----------|---------|
| **Authentication** | Verifying a user's identity | Access is denied if the user doesn't belong to the organization |
| **Authorization** | Granting access based on roles | A user cannot access resources outside their job scope |
| **Accounting** | Logging and tracking user actions | All user actions in the system are logged for accountability |

---

### Q3 — Symmetric vs Asymmetric Encryption

| Feature | Symmetric | Asymmetric |
|---------|-----------|-----------|
| Keys used | Single key for encryption & decryption | Public key + Private key |
| Use case | Storing data (e.g., full disk encryption) | Sending/receiving data (e.g., TLS/SSL) |
| Algorithm example | AES (Advanced Encryption Standard) | TLS/SSL session key exchange |
| Speed | Faster | Slower |

**Summary:** Symmetric encryption is efficient for data at rest. Asymmetric encryption is used to securely exchange keys over untrusted networks.

---

### Q4 — Steganography

**Definition:** Steganography is the practice of concealing secret messages or data within an unsuspicious medium such as an image or audio file.

**Steganography vs Encryption:**
- Steganography **hides** the existence of a message within a medium.
- Encryption **scrambles** data to make it unreadable, but the presence of encrypted data is still visible.

**Dual-use nature:**
- **Attackers** can use steganography to bypass firewall rules by embedding malicious code inside images.
- **Defenders** can use it to hide sensitive information from attackers in plain sight.
<img width="2550" height="2934" alt="checkpoint 2_page-0003" src="https://github.com/user-attachments/assets/bb58d7cf-b8ea-435e-be9b-5eaa382e2f6b" />


---

## Key Takeaways

- Security controls are categorized by type (managerial, operational, technical, physical) and function (preventative, detective, corrective).
- The CIA Triad and AAA framework form the foundation of all security policies and designs.
- Encryption type selection depends on the use case — at-rest data vs in-transit data.
- Steganography is a dual-use technique that both attackers and defenders can leverage.
