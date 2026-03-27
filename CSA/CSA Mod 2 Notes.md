# CSA Module 2 - Cyber Threats & Attack Vectors

---

## 1. Cyber Threats

### Definition

A **Cyber Threat** is an act where an adversary attempts to:

- Gain Unauthorized access
- Exploit communication paths
- Compromise systems or data

### Key Objectives of Cyber Threats

- **Data theft**
  - Personal information
  - Financial data
  - Login credentials
- **System compromise**
- **Espionage**
- **Disruption of services**

### Core Elements Behind Every Threat

Every cyber threat is based on three fundamental components:

**1. Intent**
- The motivation of the attacker
- Examples:
  - Financial gain
  - Political motives
  - Espionage
  - Revenge

**2. Capability**
- The attacker's skills, tools, and techniques
- Includes:
  - Malware
  - Exploit kits
  - Social engineering
  - Advanced TTPs

**3. Opportunity**
- A weakness or vulnerability that allows attack
- Example:
  - Unpatched system
  - Misconfigured firewall

---

## 2. Tactics, Techniques, and Procedures (TTPs)

### Definition

TTPs describe:
- Patterns of attacker behavior
- Methods used to carry out attacks

### Why TTPs Are Important (SOC Perspective)

- Helps in threat detection, threat hunting, and incident investigation
- Used in MITRE ATT&CK framework

### Components of TTPs

**1. Tactics** - High-level goals or objectives of an attacker
- Initial access
- Privilege escalation
- Lateral movement
- Persistence

**2. Techniques** - Specific methods used to achieve tactics
- Phishing emails
- Credential dumping
- Command and Control (C2) setup
- Data exfiltration

**3. Procedures** - Step-by-step implementation details
- Sending phishing mail → collecting credentials
- Scanning network → identifying weak systems

> **Simple Understanding:** Tactic = **What** attacker wants | Technique = **How** attacker does it | Procedure = **Exact steps** used

---

## 3. Vulnerability, Weakness, Opportunity

A **Vulnerability** is a weakness in design, implementation, or configuration that can lead to security compromise.

### Examples of Vulnerabilities

**1. TCP/IP Protocol Vulnerabilities**
- Inherently insecure protocols: HTTP, FTP, ICMP, SNMP, SMTP
- Reason: Lack encryption/authentication

**2. Operating System Vulnerabilities**
- Unpatched systems
- Outdated software
- Misconfigurations

**3. Network Device Vulnerabilities**
- Routers, Firewalls, Switches
- Weak passwords, no authentication, insecure routing protocols, firewall misconfigurations

---

## 4. Reconnaissance Attacks

Reconnaissance is the initial phase of an attack where attackers gather information about the target.

### Objective
- Identify: Systems, Network structure, Entry points

### Techniques Used
- Social Engineering
- Port Scanning
- DNS Footprinting
- Ping Sweeping

### Information Collected
- Domain names, Internal DNS, Network blocks, IP addresses
- Public/private systems, TCP/UDP services
- ACLs, Routing protocols, VPNs, IDS systems
- Authentication mechanisms

---

## 5. DNS Footprinting

**DNS Footprinting** is used to gather DNS information about a target.

### Purpose
- Identify: Hosts, IP addresses, Mail servers, DNS servers

## 6. Network Sniffing

**Network sniffing** is capturing and analyzing network packets.

### Why Attackers Use Sniffing
- Monitor traffic
- Extract sensitive data

### Conditions That Enable Sniffing
- Open switch ports
- Same network access
- Lack of encryption

### Sensitive Data Captured
- Syslog traffic
- Telnet passwords
- Router configurations
- FTP passwords
- DNS traffic
- Email traffic
- Web traffic
- Chat sessions

> **Key Risk:** Plaintext protocols = **HIGH RISK**

---

## 7. Password Attack Techniques

### 1. Dictionary Attack
- Uses: Predefined wordlist
- Fast but limited

### 2. Brute Force Attack
- Tries: All combinations
- Very slow but effective

### 3. Hybrid Attack
- Combines: Dictionary + variations
- Example: `password` → `Password123`

### 3.1 Password Spraying Attack
- Low and Slow, 1 password many accounts

### 4. Birthday Attack
- Based on: Hash collision probability
- Targets: Cryptographic hashes

### 5. Rainbow Table Attack
- Uses: Precomputed hash tables
- Faster than brute force

---

## 8. Privilege Escalation

**Privilege escalation** is gaining higher access rights in a system.

### Why Attackers Do It
- Access sensitive data
- Control system
- Deploy malware

### Methods Used
- Exploiting vulnerabilities
- Misconfigurations
- Weak permissions

### Types of Privilege Escalation

**1. Vertical Privilege Escalation**
- User → Admin (Gains higher privileges)
- Example: Exploiting kernel vulnerability

**2. Horizontal Privilege Escalation**
- User → Another user (Same privilege level)
- Example: Accessing another user's account

---

## 9. DNS Poisoning

**DNS Poisoning** is manipulating DNS responses to redirect users.

### How It Works
- Attacker alters DNS mapping
- Result: Legit domain → malicious IP

### Example
- User enters: `google.com`
- Redirected to: Fake malicious website

### Impact
- Phishing
- Data theft
- Malware delivery

---
---

## 11. Advanced Persistent Threats (APTs)

An **Advanced Persistent Threat (APT)** is a targeted cyberattack where an attacker gains unauthorized access and remains undetected for a long period.

### Key Characteristics
- **Advanced** → Uses sophisticated tools and techniques
- **Persistent** → Long-term access maintained
- **Threat** → Highly skilled and organized attackers

### Primary Objective
- Steal sensitive information:
  - Classified documents
  - Credentials
  - Financial data
  - Business strategies

### Information Targeted in APT Attacks
- User credentials
- Personal employee/customer data
- Network architecture details
- Transaction and credit card information
- Organizational strategies
- Control system access (critical infrastructure)

### APT Attack Lifecycle (Important)
1. Initial Access (phishing, exploit)
2. Establish Foothold
3. Privilege Escalation
4. Lateral Movement
5. Data Exfiltration
6. Maintain Persistence

### SOC Perspective
- Hard to detect due to low and slow attacks and legitimate-looking traffic
- Requires behavioral analysis and threat intelligence

---

## 12. Malware Attacks

**Malware** is software designed to disrupt systems, steal data, or gain unauthorized access without user knowledge.

### Common Malware Types

| Type | Description |
|------|-------------|
| **Virus** | Self-replicating, attaches to files/programs |
| **Trojan** | Disguised as legitimate software, does NOT self-replicate |
| **Spyware** | Secretly collects user info (keyloggers, tracking tools) |
| **Adware** | Displays unwanted ads, tracks browsing behavior |
| **Rootkit** | Hides malicious activities, provides stealth access |
| **Backdoor** | Bypasses authentication, allows remote access |

### Impact of Malware
- Data theft
- System compromise
- Network spread
- Persistence

---

## 13. Distributed Denial-of-Service (DDoS)

**DDoS** is an attack using multiple systems (botnets) to flood a target, causing service unavailability.

### DDoS Attack Flow
1. Attacker controls handler servers
2. Handlers control zombie machines
3. Zombies send massive traffic
4. Target server becomes unavailable

### Types of DDoS
- **Network-Centric:** Targets bandwidth (e.g., UDP flooding)
- **Application-Centric:** Targets application layer (e.g., HTTP flood)

### SOC Detection Indicators
- Sudden traffic spike
- High bandwidth usage
- Service downtime

---

## 14. Network-based Denial of Service (DoS)

**DoS attack** from a single system that floods the target and overloads resources.

### Common Techniques
- **TCP SYN Flooding** - Exploits TCP handshake, leaves connections half-open
- **UDP Flooding** - Sends large UDP packets, overwhelms system
- **ICMP Smurf Attack** - Uses broadcast IP, amplifies traffic
- **Intermittent Flooding** - Random bursts, harder to detect

---

## 15. MAC Spoofing / Duplicating

**MAC Spoofing** is changing MAC address to impersonate another device.

### How It Works
1. Attacker scans network for MAC addresses
2. Spoofs a legitimate MAC address
3. Receives traffic intended for that user

### Impact
- Unauthorized access
- Data interception
- Identity impersonation

---

## 16. Switch Port Stealing

A **man-in-the-middle attack** where attacker floods switch MAC table.

### How It Works
1. Attacker sends forged packets
2. Switch associates attacker's MAC with victim's MAC
3. Traffic redirected to attacker

### Impact
- Traffic interception
- Data theft
- Network disruption

---

## 17. DHCP Spoofing Attack

Attacker introduces a **rogue DHCP server**.

### How It Works
1. Client requests IP
2. Rogue server responds faster
3. Assigns fake IP and malicious gateway

### Impact
- Traffic redirection
- Man-in-the-middle attack
- Data interception

---

## 18. DHCP Starvation Attack

**Exhausts DHCP IP pool** by sending multiple requests with fake MAC addresses.

### Result
- All IPs get allocated to attacker
- Legit users cannot get IP
- Denial of service / Network access failure

---

## 19. ARP Poisoning

Sending **fake ARP messages** to map attacker MAC with victim IP.

### How It Works
1. Attacker sends fake ARP replies
2. Victim updates ARP table
3. Traffic redirected to attacker

### Impact
- Man-in-the-middle attack
- Data interception
---

# Advanced Topics

## APT Lifecycle Phases

| Phase | Objective | Key Activities | SOC Indicators |
|-------|-----------|----------------|----------------|
| **1. Preparation** | Plan and gather intelligence | Recon, vulnerability ID, tool prep, C2 setup | OSINT collection, external scanning |
| **2. Initial Intrusion** | Gain initial access | Phishing, exploits, malicious attachments | Suspicious attachments, unusual outbound traffic |
| **3. Expansion** | Expand network control | Priv esc, credential harvesting, lateral movement | Multiple login attempts, cross-host access |
| **4. Persistence** | Maintain long-term access | Backdoors, scheduled tasks, registry mods, rootkits | Unknown services, persistence in registry |
| **5. Search & Exfiltration** | Locate and steal data | Database search, compression, data exfil | Large outbound traffic, encrypted anomalies |
| **6. Cleanup** | Remove traces | Delete logs, remove malware, obfuscate | Missing logs, log tampering |

### Key Characteristics of APT Lifecycle
- Long-term attack
- Stealth-focused
- Targeted
- Data-driven objective

> **Full APT Flow:** Preparation → Initial Intrusion → Expansion → Persistence → Search & Exfiltration → Cleanup

---

## Supply Chain Attack

A **Supply Chain Attack** targets an organization by exploiting third-party vendors, suppliers, or partners to gain indirect access.

### Key Concept
Instead of attacking the organization directly, the attacker compromises a **trusted entity** and uses that trust to infiltrate.

### Supply Chain Components
- People
- Software vendors
- Hardware providers
- Service providers
- Processes
- Infrastructure

### Attack Flow
1. Attacker compromises vendor/supplier
2. Injects malicious code or gains access
3. Trusted connection used to access target organization
4. Establishes backdoor
5. Data exfiltration occurs

### Attack Techniques Used
- **Malware Injection** - Inject malicious code into software updates/applications
- **Social Engineering** - Target vendor employees for credentials
- **Brute Force Attacks** - Target supplier systems with weak passwords
- **Exploiting Vulnerabilities** - Use unpatched vendor systems
- **Physical Access Modification** - Tampering with hardware
- **Open-Source Modification** - Insert malicious code into libraries
- **Counterfeiting** - Replace legitimate hardware/software

### SOC Detection Challenges
---

# Host Security Threats

## Definition of Host Security

Host security refers to the protection of individual computing devices:
- Desktop, Laptop, Server, Workstation
- Virtual machine, Mobile endpoint

### Why Hosts Are Targeted
Hosts store: User data, Credentials, Applications, Configuration files, Logs, Access tokens, Cached sessions.

## Common Threat Categories

### 1. Malware Infection
Malware executes unauthorized actions on a host:
- Modifying files, Stealing information, Opening remote access
- Encrypting data, Disabling security tools, Creating persistence mechanisms

### 2. Accidental or Intentional Data Deletion
- **Accidental:** User deletes important files by mistake
- **Intentional:** Malicious insider removes/destroys data

### 3. Unauthorized Access
Methods include:
- Guessing passwords
- Exploiting software vulnerabilities
- Stealing credentials
- Escalating privileges (user → admin)
- Using backdoors or remote access tools

## Host-based DoS Attacks

Host-based DoS focuses on **overloading the target machine itself** (not network bandwidth).

### Resources Targeted
- CPU, Memory (RAM), Disk I/O, Process table, Kernel buffers, Application threads, Authentication services

### Types of Host-based DoS

| Attack | Description | Impact |
|--------|-------------|--------|
| **Ping of Death** | Malformed/oversized ICMP packets | System crash, freeze, reboot |
| **Teardrop** | Fragmented packets with overlapping offsets | Crash, reboot, instability |

> **Difference:** Host-based DoS → exhausts internal resources | Network-based DoS → saturates bandwidth

## Brute Force Attacks

Gaining access by **systematically trying all password combinations**.

### How It Works
1. Attacker prepares usernames and passwords list
2. System tested repeatedly with login attempts
3. Cycle continues until success

### Common Variants
- **Pure Brute Force** - Tries every possible combination
- **Dictionary Attack** - Tries common words
- **Hybrid Attack** - Dictionary words with symbols/numbers
- **Credential Stuffing** - Uses leaked username/password pairs
- **Password Spraying** - Common password across many accounts

### Prevention
- Strong password policies, MFA, Account lockout, Login throttling, CAPTCHA

## Spyware Attacks

Malicious software that **secretly monitors user activity**.

### Keylogger Spyware
Records keystrokes to capture: Passwords, Credit card numbers, Personal messages, Corporate credentials.

### Attack Flow
Attacker prepares payload → Delivers via phishing → User executes → Keylogger installed → Attacker tracks activity

## Ransomware Attacks

Attackers **encrypt victim's files** and demand payment for decryption.

---

## Host Threat Sources Summary

| Source | Description |
|--------|-------------|
| **Unpatched Systems** | Exploited known vulnerabilities |
| **Email** | Phishing, malware attachments |
| **Blended Threats** | Multiple attack methods combined |
| **Social Engineering** | Manipulating people |
| **File Shares** | Malware propagation |
| **Internet Downloads** | Pirated software, fake updates |

---

# Web Application Attacks

## 1. SQL Injection (SQLi)

Injecting **malicious SQL queries** into input fields to bypass authentication and access/modify/delete database data.

### How SQLi Works
- Application doesn't validate user input
- User input directly used in SQL queries

### Example
```
Normal: SELECT * FROM users WHERE username='admin' AND password='123'
Attack: admin' OR '1'='1
Result: SELECT * FROM users WHERE username='admin' OR '1'='1' → Always TRUE
```

### What Attackers Can Do
- Bypass authentication
- Dump database (usernames, passwords, PII)
- Modify/delete records
- Execute stored procedures

### Prevention
- Prepared statements (parameterized queries)
- Input validation & sanitization
- Use ORM frameworks
- WAF (Web Application Firewall)

## 2. Cross-Site Scripting (XSS)

Malicious scripts injected into web pages and **executed in the user's browser**.

### Types of XSS

| Type | Description |
|------|-------------|
| **Stored XSS** | Stored in database, executes for every user |
| **Reflected XSS** | Reflected via URL/input, immediate execution |
| **DOM-based XSS** | Client-side script manipulation |

### What Attackers Can Do
- Steal cookies/session IDs
- Hijack user sessions
- Redirect users
- Capture keystrokes

### Prevention
- Input validation, Output encoding, Content Security Policy (CSP)
- Secure cookies (HttpOnly, Secure flags)

## 3. Parameter Tampering

**Manipulating parameters** exchanged between client and server.

### What Can Be Modified
- Price values, User roles, Account IDs, Quantity, Permissions

### Example
- Original: `price=100`
- Tampered: `price=1`

## 4. Directory Traversal

Allows attackers to **access restricted files/directories** outside the web root.

### How It Works
Uses `../` sequences
Example: `../../../etc/passwd`

### What Attackers Access
- System files, Configuration files, Password files, Logs, Source code

## 5. Application-Level DoS

Targets **application resources** (not just network).

### How It Works
- Sends many resource-intensive requests
- Database-heavy queries, Large file requests

### Targets
- CPU, Memory, Disk, Database bandwidth, Worker processes

## 6. Session Attacks

### 6.1 Session Fixation
- Attacker forces user to use a known session ID
- Victim logs in → Same session used → Attacker hijacks

### 6.2 Cookie Poisoning
- Modifying cookie data to gain unauthorized access
- **Weak Practice:** Encoding cookies (Base64/ROT13) is NOT secure

## 7. OWASP Top 10 (2021)

| # | Risk |
|---|------|
| 1 | Broken Access Control |
| 2 | Cryptographic Failures |
| 3 | Injection |
| 4 | Insecure Design |
| 5 | Security Misconfiguration |
| 6 | Vulnerable and Outdated Components |
| 7 | Identification and Authentication Failures |
| 8 | Software and Data Integrity Failures |
| 9 | Security Logging and Monitoring Failures |
| 10 | Server-Side Request Forgery (SSRF) |

## 8. Social Engineering (Physical)

| Attack | Description |
|--------|-------------|
| **Dumpster Diving** | Searching trash for sensitive information |
---

# Email & Insider Attacks

## Email Attacks

Email is one of the most common initial attack vectors.

### 1. Phishing
Social engineering attack sending legitimate-looking emails to trick victims.

**Attack Flow:**
1. Attacker sends fake email (bank, company)
2. Email contains malicious link or form
3. Victim clicks link → redirected to fake website
4. Victim enters credentials → data sent to attacker

### 2. Malicious Email Attachments
Delivers malware through attachments: `.exe`, `.doc/.docx` (macros), `.pdf`, `.zip/.rar`

### 3. Malicious User Redirection
- User clicks link → multiple redirects → malicious site
- Credential theft, malware infection, financial fraud

### 4. Spamming
Unsolicited commercial emails sent in bulk - used for phishing delivery and malware distribution.

## Insider Attacks

Threats from within the organization (employees, contractors, partners).

### 1. Unauthorized Access
Accessing data/systems/resources outside permitted scope.

### 2. Malicious Software Installation
Insider intentionally installs: Spyware, Keyloggers, Backdoors.

### SOC Indicators of Insider Threats
- Access outside job role
- Unusual login times
- Data access spikes
- Unauthorized software installation

---

# Indicators of Compromise (IoCs)

**IoCs** are artifacts or evidence that indicate a system has been compromised.

## Examples of IoCs
- IP addresses
- File hashes
- Domain names
- URLs
- Registry changes
- Log anomalies

## Why IoCs Are Important

| Benefit | Description |
|---------|-------------|
| **Detect Threats** | Identify malware and attacks early |
| **Understand Incidents** | Answer: What happened? How? |
| **Improve Response** | Faster detection → faster response |
| **Improve Detection Rate** | Better rules and alerts |
| **Enable Automation** | Feed IoCs into SIEM/SOAR |
| **Support Investigation** | Is file malicious? Is network compromised? |

## Network Attack IoCs

| Indicator | Description |
|-----------|-------------|
| **Unusual Traffic Patterns** | Abnormal spikes, unexpected protocols |
| **Anomalous DNS Requests** | Requests to suspicious domains |
| **Port Scanning** | Multiple ports probed |
| **C2 Traffic** | Communication with attacker servers |
| **Abnormal ARP Traffic** | ARP poisoning |
| **High Failed Logins** | Brute force attempt |
| **Large Data Transfers** | Data exfiltration |

## Host Attack IoCs

| Indicator | Description |
|-----------|-------------|
| **Unusual Processes** | Unknown/suspicious programs running |
| **File System Changes** | New/modified files, unknown executables |
| **Persistence Mechanisms** | Registry changes, startup entries |
| **Log Deletion** | Attempt to hide activity |
| **Privilege Escalation** | Exploiting vulnerabilities |

## Email Attack IoCs

| Indicator | Description |
|-----------|-------------|
| **Suspicious Attachments** | Malware payloads |
| **Phishing Emails** | Fake sender, credential harvesting |
| **Email Spoofing** | Forged sender addresses |
| **Malicious URLs** | Hidden or obfuscated links |
| **Forwarding Rules** | Automatic forwarding (compromise sign) |
| **Domain Impersonation** | Look-alike domains |

## Insider Attack IoCs

| Indicator | Description |
|-----------|-------------|
| **Unauthorized Data Access** | Access outside job role |
| **Data Exfiltration** | Copying sensitive data |
| **Suspicious Account Usage** | Access from unusual locations |
| **Privilege Misuse** | Admin actions without reason |
| **Frequent USB Usage** | Data copying to external drives |
| **Unauthorized Accounts** | Backdoor access creation |

## Application Attack IoCs

| Indicator | Description |
|-----------|-------------|
| **Unusual API Requests** | Abnormal/unauthorized API calls |
---

# Security Frameworks & Models

## 1. Lockheed Martin Cyber Kill Chain

Describes stages of a cyberattack.

| Phase | Description |
|-------|-------------|
| **1. Reconnaissance** | Gather information about target |
| **2. Weaponization** | Create malware/exploit |
| **3. Delivery** | Send payload (email, USB, etc.) |
| **4. Exploitation** | Execute exploit |
| **5. Installation** | Install malware |
| **6. C2** | Establish communication channel |
| **7. Actions on Objectives** | Data theft, system control |

> **SOC Importance:** Helps detect early stages and break the attack chain.

---

## 2. MITRE ATT&CK Framework

A knowledge base of attacker behavior (TTPs).

### Purpose
- Standardize threat detection
- Map attacks to techniques
- Improve threat hunting

### Structure
- **Tactics** - High-level goals
- **Techniques** - Methods
- **Procedures** - Implementation

### Example Tactics
- Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Lateral Movement, Exfiltration

> **Used in:** SOC detection rules, threat intelligence, incident response.

---

## 3. Unified Kill Chain

Combines Cyber Kill Chain + MITRE ATT&CK.

| Phase | Stages |
|-------|--------|
| **IN** | Reconnaissance, Resource development, Delivery |
| **THROUGH** | Execution, Persistence, Lateral movement, Privilege escalation |
| **OUT** | Data exfiltration, Impact, Objectives achieved |

> **Benefit:** More detailed than traditional kill chain, covers full attack lifecycle.

---

## 4. MITRE D3FEND Framework

Focused on **defensive techniques**.

### Stages
1. Model
2. Harden
3. Detect
4. Isolate
5. Deceive
6. Evict
7. Restore

> **Purpose:** Map defenses to attacks. Answers "How do we defend this attack?"

---

## 5. Diamond Model of Intrusion Analysis

Analyzes attacks using four core elements:

| Element | Description |
|---------|-------------|
| **Adversary** | Who performed the attack |
| **Victim** | Target of attack |
| **Capability** | Tools/malware used |
| **Infrastructure** | Systems used by attacker (IP, domains) |

> **Purpose:** Understand relationships, improve threat intelligence, link events together.

---

## 6. Kill Chain Scenario - Spear Phishing

| Phase | Activity |
|-------|----------|
| **Reconnaissance** | Gather employee details |
| **Weaponization** | Create malicious attachment |
| **Delivery** | Send phishing email |
| **Exploitation** | User opens attachment |
| **Installation** | Malware installed |
| **C2** | Connect to attacker server |
| **Actions on Objectives** | Data theft, lateral movement |

---

## 7. Gaining TTP Knowledge via Hacker Forums

Attackers share techniques, tools, exploits, and evasion methods on platforms like:
- Hackaday, Ethical Hacker Network, Hack This Site
- Hack Forums, Evil Zone

> **SOC Relevance:** Threat intelligence gathering, early warning of new attacks.

---

## 8. NIST Cybersecurity Framework 2.0

A standardized framework for managing cybersecurity risk.

### Core Functions

| # | Function | Description |
|---|----------|-------------|
| **1. Govern** | Risk management, Policies |
| **2. Identify** | Assets, Risks, Vulnerabilities |
| **3. Protect** | Safeguards, Controls |
| **4. Detect** | Identify incidents |
| **5. Respond** | Handle incidents |
| **6. Recover** | Restore systems |

> **Importance:** Widely used globally, aligns with SOC operations, helps build security strategy.

---

## 9. MITRE ATT&CK TTPs

| Tactic | Description |
|--------|-------------|
| **Initial Access** | Ways to get into a network |
| **Execution** | Running malicious code |
| **Persistence** | Maintaining presence |
| **Privilege Escalation** | Gaining higher privileges |
| **Defense Evasion** | Avoiding detection |
| **Credential Access** | Stealing credentials |
| **Discovery** | Learning about environment |
| **Lateral Movement** | Moving through network |
| **Collection** | Gathering data |
| **Command and Control** | Communicating with attacker |
| **Exfiltration** | Stealing data |
| **Impact** | Manipulating/destroying data |

---

## 10. ATT&CK Technique Examples

| Technique | ID | Description |
|-----------|-----|-------------|
| **Phishing** | T1566 | Email with malicious attachment/link |
| **Brute Force** | T1110 | Repeated login attempts |
| **Remote Services** | T1021 | Access via RDP, SSH, VNC |
| **Spearphishing** | T1534 | Targeted phishing |
| **Drive-by Compromise** | T1189 | Malicious website visits |
| **Valid Accounts** | T1078 | Using stolen/legit credentials |

---

# Final Summary - Big Picture (VERY IMPORTANT)

## Full SOC Understanding

### Attack Side
| Framework | Purpose |
|-----------|---------|
| **TTPs** → MITRE ATT&CK | Attacker behavior patterns |
| **Kill Chain** | Attack stages |
| **APT** | Advanced persistent attacks |

### Detection Side
| Category | Types |
|----------|-------|
| **IoCs** | Network, Host, Application, Email, Insider |

### Defense Side
| Framework | Focus |
|-----------|-------|
| **MITRE D3FEND** | Defensive techniques |
| **NIST Framework** | Risk management strategy |

### Analysis Side
| Model | Elements |
|-------|---------|
| **Diamond Model** | Adversary, Victim, Capability, Infrastructure |

---

> **Remember:** A good SOC analyst understands both the **attack side** (how threats work) and the **defense side** (how to detect and respond). These frameworks and models are your toolkit for thinking like a defender while understanding the attacker's mindset.

---

## Quick Revision Checklist

- [ ] Cyber Threats - Intent, Capability, Opportunity
- [ ] TTPs - Tactics, Techniques, Procedures
- [ ] Password Attacks - Dictionary, Brute Force, Rainbow Table
- [ ] APT Lifecycle - 6 phases from prep to cleanup
- [ ] Malware Types - Virus, Trojan, Spyware, Ransomware
- [ ] DoS/DDoS - Single vs Multiple sources
- [ ] Network Attacks - ARP, DHCP, MAC Spoofing
- [ ] Web Attacks - SQLi, XSS, Directory Traversal
- [ ] OWASP Top 10 - Industry standard web risks
- [ ] IoCs - Network, Host, Application, Email, Insider
- [ ] Cyber Kill Chain - 7 phases
- [ ] MITRE ATT&CK - TTPs knowledge base
- [ ] MITRE D3FEND - Defensive techniques
- [ ] Diamond Model - 4 elements of intrusion
- [ ] NIST CSF 2.0 - Govern, Identify, Protect, Detect, Respond, Recover
| **Injected Code** | SQL injection, XSS payloads |
| **Unauthorized Access** | Restricted endpoints (/admin, /config) |
| **Abnormal Traffic Patterns** | Sudden spikes, resource-heavy requests |
| **Failed Logins** | Brute force attacks |
| **Malformed Requests** | Broken syntax, invalid parameters |

## Social Engineering IoCs

| Indicator | Description |
|-----------|-------------|
| **Phishing Emails** | Fake domains, urgent requests |
| **Vishing** | Suspicious phone calls |
| **Smishing** | SMS scams |
| **Fake Job Offers** | Credential harvesting |
| **Fake IT Support** | Social engineering scams |
| **Piggybacking** | Authorized person allows unauthorized entry |
| **Tailgating** | Unauthorized person follows closely (no permission) |

> **Key Difference:** Piggybacking → permission given | Tailgating → no permission

---

## Web Attacks Quick Summary

- **SQL Injection** → `‘ OR 1=1` → database attack
- **XSS** → `<script>` → browser attack
- **Parameter Tampering** → strange parameters → data manipulation
- **Directory Traversal** → `../` → file access
- **Session Fixation** → same session ID reused
- **Cookie Poisoning** → modified cookies → identity manipulation

### Modern Ransomware (Double Extortion)
- Steal data before encrypting
- Threaten public leak
- Disable backups
- Move laterally across network
- Target domain controllers

### Prevention
- Offline and tested backups
- Patch management
- MFA for remote access
- Restrict RDP
- EDR/XDR monitoring
- Network segmentation
- Traffic appears legitimate
- Comes from trusted sources
- Hard to differentiate normal vs malicious

---

## APT vs Supply Chain Comparison

| Aspect | APT Attack | Supply Chain Attack |
|--------|------------|--------------------|
| **Target** | Specific organization | Indirect via vendor |
| **Duration** | Long-term | Can be both |
| **Entry** | Direct intrusion | Third-party compromise |
| **Goal** | Data theft | Access + spread |
| **Detection** | Very difficult | Extremely difficult |
- Session hijacking

---

## Attack Comparison Table

| Attack Type | Goal | Method |
|------------|------|--------|
| DoS | Disrupt service | Single source |
| DDoS | Disrupt service | Multiple sources |
| APT | Stealth data theft | Long-term attack |
| Malware | System compromise | Malicious software |
| ARP Poisoning | Interception | Fake ARP |
| DHCP Spoofing | Redirection | Fake DHCP |
| MAC Spoofing | Impersonation | Fake MAC |

## 10. DNS Cache Poisoning

**DNS Cache Poisoning** involves injecting fake DNS records into DNS cache.

### How It Works (Step-by-Step)
1. User sends DNS query
2. DNS resolver forwards request
3. Attacker sends fake response
4. Resolver accepts fake record
5. Cache stores malicious mapping
6. Future users redirected to attacker site

> **Key Difference:** DNS Poisoning → General manipulation | DNS Cache Poisoning → Stored manipulation in cache

### DNS Record Types

| Record | Description |
|--------|-------------|
| A | Maps hostname → IP |
| MX | Mail server mapping |
| NS | Name server |
| CNAME | Alias |
| SOA | Domain authority info |
| SRV | Service records |
| PTR | Reverse lookup |
| RP | Responsible person |
| HINFO | Host info (CPU, OS) |
| TXT | Additional text info |

> **Importance:** Used in Recon phase, Social engineering, Attack planning

---
