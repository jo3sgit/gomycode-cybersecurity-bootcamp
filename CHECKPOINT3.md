<img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/e741a3ba-a5bc-48d3-bc20-3201bd781526" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/ad6f121d-2028-48ee-9beb-31fdc0bc9b6f" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/f41c0c48-b2d4-411f-a1d9-94cc16fed7ab" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/bf438631-45cd-409c-95af-f4c6885383cc" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/a15c2276-3979-4470-8350-dddc09518c59" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/0f7b39ce-627d-4325-9bba-8546764027fa" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/28dbe471-e0b1-4e56-bcf5-c7be49223b8f" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/87074bb1-c036-40f2-a4d4-1240a7d6fe5d" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/81e69a56-7d01-4c9b-a9e5-b85a2ec24f72" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/d52bd9e6-957a-4dad-bed1-a73eed8c4b65" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/4a966bad-e49d-404e-8a1a-03cc85102989" /><img width="2550" height="3300" alt="checkpoint 3_page-0003" src="https://github.com/user-attachments/assets/4880af9c-f68e-43fa-a395-32b97d09c816" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/d3d2a6e6-0dd6-4dd5-beb7-19f0176ed1db" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/3026cd62-33c3-482d-9725-e927fc296224" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/79556598-4a23-4453-959e-f576735b45c1" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/3d94c87b-768c-4dfd-8e4f-4e4ffc7f5127" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/aef6043f-e698-4c3a-b36a-106d8413c54d" /><img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/05786486-e118-4801-af4f-e153a12a2791" /># Checkpoint 3 — Threat Actors, Malware & Social Engineering

## Overview

This checkpoint covers the threat landscape: who attacks systems and why, how different malware types operate, how social engineering works, and how to analyze suspicious scripts and scan for vulnerabilities.

---

## Questions & Answers

### Q1 — Threat Actor Categories

| Threat Actor | Motivation | Real-World Example |
|-------------|-----------|-------------------|
| **Nation-State Actors** | Political control, cyber warfare, espionage | The Stuxnet worm (targeted Iran's nuclear centrifuges) |
| **Unskilled Actors (Script Kiddies)** | Fun, boredom | Running an off-the-shelf DDoS tool to take down a game server |
| **Insider Threats** | Revenge, carelessness, financial gain | An employee stealing customer data and selling it |
| **Hacktivists** | Promoting a cause, exposing injustice | Hacking a government site to expose corruption |
| **Organised Crime Groups** | Financial gain | Encrypting a company's data and demanding a ransom to restore it |

---

### Q2 — Malware Types

| Malware Type | How It Works | Real-World Example |
|-------------|-------------|-------------------|
| **Virus** | Attaches to legitimate files/applications and activates when the user interacts with them | ILOVEYOU worm |
| **Worm** | Self-replicates and spreads across systems through network vulnerabilities — no user interaction needed | Morris Worm |
| **Trojan Horse** | Disguises itself as legitimate software to trick users into installing it | Zeus (keylogging trojan) |
| **Ransomware** | Encrypts victim's files and demands payment for decryption | LockBit |
| **Spyware** | Secretly gathers information about a user and sends it to a third party | Pegasus, keyloggers, browser hijackers |
| **Rootkit** | Grants an attacker administrative-level (root) access to a device while remaining hidden | ZeroAccess |

---

### Q3 — Malicious Bash Script Analysis

**Task:** Decoded and analyzed an obfuscated base64 bash script.

**Script (decoded):**

```bash
#!/bin/bash
echo "Hacked! Your system is compromised"
rm -rf /*
```

**Line-by-line breakdown:**

| Line | Meaning |
|------|---------|
| `#!/bin/bash` | Shebang — instructs the OS to execute this script using the Bash shell |
| `echo "Hacked! Your system is compromised"` | Prints a message to the terminal |
| `rm -rf /*` | **Destructive:** Recursively deletes all files in the root directory and everything the root has access to, including the OS, personal files, and mounted drives |

**Is this script harmful?**  
Yes. The `rm -rf /*` command causes a complete system wipe, rendering the machine unbootable and destroying all data.

**Why was it encoded in Base64?**  
The attacker encoded the script in Base64 to bypass security filters that scan for plain-text keywords like `rm -rf`. Once decoded, the script becomes fully executable.
<img width="2550" height="1213" alt="checkpoint 3_page-0002" src="https://github.com/user-attachments/assets/f8776fa1-55b6-49d3-960b-04f3b100fc95" />



---

### Q4 — Social Engineering & Phishing

**Definition:** Social engineering relies on manipulating human behavior to gain unauthorized access to systems or sensitive information. It is considered a major threat because it exploits human error, which is harder to predict and defend against than technical vulnerabilities.

**Phishing Email Analysis:**

The sample email analyzed was a **phishing attack** with the following characteristics:

- Creates **urgency** (e.g., "verify your account before service is disrupted")
- Uses **appropriate grammar** and formatting to appear legitimate
- Difficult to detect as fake at first glance
- Most likely to target someone who **recently registered for a service**

---

### Q5 — Vulnerability Scanning Results (Nikto/Nmap)

**Open Ports:**

| Port | Service |
|------|---------|
| 80 / 443 | HTTP / HTTPS |
| 135 | Microsoft RPC |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL/MariaDB |

**Vulnerabilities Identified:**

| Vulnerability | Risk |
|--------------|------|
| Outdated PHP version | Exposes server to known exploits |
| Missing `X-Frame-Options` header | Site vulnerable to clickjacking attacks |
| Missing `X-Content-Type-Options` header | Browser MIME-type sniffing attacks possible |
| HTTP TRACE method enabled | Host vulnerable to Cross-Site Tracing (XST) |

---

### Q6 — VirusTotal Scan

Analyzed a website URL using **VirusTotal**.

The scan was reviewed by multiple security vendors including Avast, Bitdefender, Kaspersky, Fortinet, and Google Safe Browsing — all returned a **clean** result.

**VirusTotal** aggregates threat intelligence from dozens of antivirus engines and URL scanners, making it a powerful tool for quick threat verification.

---

## Tools Used

- `nmap` — Port scanning
- **Nikto** — Web vulnerability scanning
- **VirusTotal** — URL and file reputation analysis
- Base64 decoding — Script obfuscation analysis

---

## Key Takeaways

- Different threat actors have different motivations — understanding intent helps with threat modeling.
- Malware types vary by how they spread, persist, and cause damage.
- Obfuscation (e.g., Base64 encoding) is commonly used to bypass security filters.
- Social engineering targets the weakest link in any security chain — humans.
- Vulnerability scanners reveal misconfigurations and missing security headers that attackers actively exploit.
