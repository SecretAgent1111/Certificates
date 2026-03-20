# Domain 2 – Threats, Vulnerabilities, and Mitigations (22%)

This domain focuses on understanding attackers, vulnerabilities, attack techniques, indicators of compromise, and mitigation strategies used to protect enterprise systems.

---

## 2.1 Threat Actors and Motivations

### Threat Actors

| Threat Actor        | Description | Example |
|--------------------|------------|---------|
| Nation-State       | Government-sponsored attackers with advanced tools and large resources | Cyber warfare, intelligence gathering |
| Script Kiddie      | Low-skilled attacker using pre-built tools | Downloading tools to attack websites |
| Hacktivist         | Politically or ideologically motivated attacker | Website defacement, DDoS |
| Insider Threat     | Authorized user causing harm (intentional or accidental) | Data theft, accidental exposure |
| Organized Crime    | Criminal groups focused on financial gain | Ransomware, fraud |
| Shadow IT          | Unauthorized systems used without IT approval | Personal cloud apps, unauthorized tools |

---

### Types of Insider Threats

- **Malicious Insider** – Intentional damage or theft  
- **Negligent Insider** – Accidental exposure  
- **Compromised Insider** – Account taken over  

---

### Threat Actor Attributes

| Attribute            | Description |
|---------------------|------------|
| Internal            | Employees or insiders |
| External            | Outside attackers |
| Resources/Funding   | Low (script kiddie) → High (nation-state) |
| Sophistication      | Low (automated) → High (APT) |

---

### Threat Actor Motivations

- Data exfiltration  
- Espionage  
- Service disruption (e.g., DDoS)  
- Blackmail (e.g., ransomware)  
- Financial gain  
- Political/ideological reasons  
- Ethical testing  
- Revenge  
- Chaos/disruption  
- Cyber warfare  

---

## 2.2 Threat Vectors and Attack Surfaces

- **Threat Vector**: Path used to gain access  
- **Attack Surface**: Total entry points in a system  

---

### Message-Based Threats

| Vector | Description |
|--------|------------|
| Email  | Phishing, malware attachments |
| SMS    | Smishing attacks |
| IM     | Malicious links via chat apps |

---

### Other Attack Vectors

| Vector                | Description |
|----------------------|------------|
| Image-Based          | Malware hidden in images (steganography) |
| File-Based           | Malicious PDFs, docs, executables |
| Voice Call           | Vishing attacks |
| Removable Devices    | USB malware (USB drop attacks) |

---

### System & Network Vectors

| Vector                | Description |
|----------------------|------------|
| Vulnerable Software  | Exploitable flaws |
| Unsupported Systems  | No security updates |
| Wireless Networks    | Weak Wi-Fi security |
| Wired Networks       | Unsecured internal networks |
| Bluetooth            | Bluejacking, Bluesnarfing |
| Open Ports           | Exploitable services |
| Default Credentials  | Weak default login credentials |

---

### Supply Chain Attacks

Targets third-party vendors:

- MSPs  
- Software providers  
- Hardware vendors  

---

### Social Engineering (Human Vectors)

| Attack Type | Description |
|-------------|------------|
| Phishing    | Fake emails |
| Vishing     | Voice phishing |
| Smishing    | SMS phishing |
| BEC         | Business email compromise |
| Pretexting  | Fake scenario |
| Impersonation | Pretending to be trusted entity |
| Watering Hole | Compromised trusted site |
| Brand Impersonation | Fake websites |
| Typosquatting | Misspelled domains |

---

## 2.3 Types of Vulnerabilities

A vulnerability is a weakness that can be exploited.

---

### Application Vulnerabilities

| Type              | Description |
|-------------------|------------|
| Memory Injection  | Injecting malicious code |
| Buffer Overflow   | Exceeding memory limits |
| Race Conditions   | Timing-based flaws (TOC/TOU) |
| Malicious Update  | Compromised updates |

---

### Operating System Vulnerabilities

- Kernel flaws  
- Privilege escalation  

---

### Web-Based Vulnerabilities

| Type | Description |
|------|------------|
| SQL Injection (SQLi) | Malicious database queries |
| Cross-Site Scripting (XSS) | Injecting scripts |

---

### Other Vulnerabilities

| Category            | Description |
|--------------------|------------|
| Hardware           | Firmware flaws, legacy systems |
| Virtualization     | VM escape, resource reuse |
| Cloud              | Misconfigurations |
| Supply Chain       | Vendor weaknesses |
| Cryptographic      | Weak encryption, poor key management |
| Misconfiguration   | Incorrect settings (e.g., open ports) |
| Mobile             | Sideloading, jailbreaking |

---

### Zero-Day Vulnerability

Previously unknown vulnerability exploited before a fix is available.

---

## 2.4 Indicators of Malicious Activity

Indicators of Compromise (IoCs) help detect attacks.

---

### Malware Types

| Malware     | Description |
|-------------|------------|
| Ransomware  | Encrypts data for payment |
| Trojan      | Disguised malware |
| Worm        | Self-replicating |
| Spyware     | Monitors activity |
| Virus       | Attaches to files |
| Keylogger   | Records keystrokes |
| Rootkit     | Hides attacker presence |
| Logic Bomb  | Trigger-based malware |

---

### Attack Categories

#### Network Attacks
- DDoS (amplified, reflected)  
- DNS attacks  
- Man-in-the-Middle  
- Credential replay  

#### Application Attacks
- Injection  
- Buffer overflow  
- Privilege escalation  
- Directory traversal  

#### Cryptographic Attacks
- Downgrade attacks  
- Collision attacks  
- Birthday attacks  

#### Password Attacks
- Brute force  
- Password spraying  

---

### Indicators of Compromise

- Account lockouts  
- Concurrent sessions  
- Impossible travel  
- Resource spikes  
- Missing logs  
- Out-of-cycle logging  
- Blocked content  
- System inaccessibility  

---

## 2.5 Mitigation Techniques

Mitigation reduces security risks.

---

### Network & Access Controls

| Technique              | Description |
|-----------------------|------------|
| Segmentation          | Isolating network sections |
| Access Control        | Restricting access |
| ACLs                  | Traffic filtering rules |
| Permissions           | User privilege control |
| Application Allow List | Only approved apps allowed |

---

### System Protection

- Isolation (quarantine systems)  
- Patching (fix vulnerabilities)  
- Encryption (protect data)  
- Monitoring (continuous tracking)  
- Least privilege (minimum access)  
- Configuration enforcement  

---

### Lifecycle Management

- Decommissioning outdated systems  

---

### Hardening Techniques

- Encryption  
- Endpoint protection  
- Host-based firewall  
- HIPS (Host Intrusion Prevention System)  
- Disable unused ports/protocols  
- Change default passwords  
- Remove unnecessary software  

---
