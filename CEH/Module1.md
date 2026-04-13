# Module 1

## Information Security

Information Security refers to the protection of information and systems from unauthorized access, disclosure, alteration, or destruction, ensuring minimal risk of theft, tampering, and disruption.

## Core Elements (CIA + Additional)

### 1. Confidentiality

**Definition:**  
Ensures that information is accessible only to authorized users.

**Explanation:**  
Prevents unauthorized disclosure.

**Achieved using:**  
- Encryption (AES, RSA)  
- Access control (RBAC)  
- Authentication mechanisms  

**Example:**  
Only HR can access employee salary data.

---

### 2. Integrity

**Definition:**  
Ensures data is accurate and not altered improperly.

**Explanation:**  
Prevents:
- Unauthorized modification  
- Data corruption  

**Achieved using:**  
- Hashing (SHA‑256)  
- Digital signatures  
- File integrity monitoring  

**Example:**  
Detecting file tampering using hash mismatch.

---

### 3. Availability

**Definition:**  
Ensures systems and data are accessible when needed.

**Explanation:**  
Prevents service downtime.

**Achieved using:**  
- Redundancy  
- Load balancing  
- Backup systems  
- DDoS protection  

**Example:**  
Website remains accessible during high traffic.

---

### 4. Authenticity

**Definition:**  
Ensures data or communication is genuine and verified.

**Explanation:**  
Confirms identity of sender.

**Achieved using:**  
- Digital certificates  
- Multi‑factor authentication  

**Example:**  
Verifying a signed email.

---

### 5. Non-Repudiation

**Definition:**  
Ensures a sender cannot deny sending a message.

**Explanation:**  
Provides proof of origin and delivery.

**Achieved using:**  
- Digital signatures  
- Logging mechanisms  

**Example:**  
Signed transaction in banking.

---

## Classification of Attacks

### 1. Passive Attacks

**Definition:**  
Do not alter data; only monitor or intercept traffic.

**Examples:**  
- Sniffing  
- Eavesdropping  

---

### 2. Active Attacks

**Definition:**  
Modify or disrupt data or services.

**Examples:**  
- DoS  
- Man‑in‑the‑Middle  
- SQL Injection  
- Session Hijacking  

---

### 3. Close‑in Attacks

**Definition:**  
Require physical proximity.

**Examples:**  
- Shoulder surfing  
- Social engineering  
- Dumpster diving  

---

### 4. Insider Attacks

**Definition:**  
Performed by trusted users with access.

**Examples:**  
- Installing malware  
- Data theft  
- Backdoors  

---

### 5. Distribution Attacks

**Definition:**  
Tampering with hardware or software before deployment.

**Example:**  
Supply chain attack (infected firmware).

---

## Information Warfare

**Definition:**  
Use of ICT (Information & Communication Technologies) to gain advantage over an opponent.

### Defensive Information Warfare

**Purpose:**  
Protect systems from attacks.

**Activities:**  
- Prevention  
- Detection  
- Response  
- Alerts  
- Preparedness  

---

### Offensive Information Warfare

**Purpose:**  
Attack opponent systems.

**Examples:**  
- Web application attacks  
- Malware attacks  
- MITM attacks  
- System hacking  

---

## Why Ethical Hacking is Necessary

**Key Idea:**  
“To beat a hacker, think like a hacker.”

**Reasons:**  
1. Prevent unauthorized access.  
2. Avoid security breaches.  
3. Identify vulnerabilities before exploitation.  
4. Protect customer data.  
5. Improve security posture.  
6. Increase awareness.  

---

## ChatGPT‑Powered AI Tools for Ethical Hackers

**Definition:**  
AI tools leveraging NLP/ML to assist cybersecurity tasks.

**Features:**  
- Automates repetitive tasks  
- Analyzes threats  
- Integrates with threat intelligence  
- Assists in scripting and analysis  

**Example Tools:**  
- HackerGPT  
- PentestGPT  
- BugHunterGPT  
- ShellGPT  

**Real Use Cases:**  
- Log analysis  
- Script generation  
- Threat intelligence summarization  

---

## CEH Ethical Hacking Framework

**Phases:**  
1. Reconnaissance  
   - Information gathering  
   - Footprinting  
2. Scanning  
   - Open ports  
   - Services  
3. Gaining Access  
   - Exploitation  
4. Maintaining Access  
   - Persistence (backdoors)  
5. Clearing Tracks  
   - Remove logs  

**Example Tools:**  
- Nmap  
- Wireshark  
- Metasploit  
- Burp Suite  

---

## Cyber Kill Chain Methodology

**Definition:**  
Framework to understand attacker stages.

**Phases:**  
1. Reconnaissance  
2. Weaponization  
3. Delivery  
4. Exploitation  
5. Installation  
6. Command & Control  
7. Actions on Objectives  

---

## MITRE ATT&CK Framework

**Definition:**  
Knowledge base of attacker tactics and techniques.

**Key Points:**  
- Based on real‑world attacks  
- Used for:  
  - Threat modeling  
  - Detection engineering  

**Structure:**  
- **Tactics** (Why)  
- **Techniques** (How)  

**Example:**  
- Tactic: Persistence  
- Technique: Registry Run Keys  

---

## Diamond Model of Intrusion Analysis

**Definition:**  
Framework to analyze cyber incidents using relationships.

**Components:**  
1. **Adversary (Who)**  
   - Attacker  
2. **Victim (Target)**  
   - Organization/system  
3. **Capability (How)**  
   - Tools/techniques  
4. **Infrastructure (What)**  
   - Servers, domains used  

**Use Case:**  
Correlating attacks across incidents.

---

## Information Assurance (IA)

**Definition:**  
Ensures:
- Confidentiality  
- Integrity  
- Availability  
- Authenticity  

**Processes:**  
- Policy development  
- Authentication design  
- Vulnerability identification  
- Resource planning  
- Security planning  
- Control implementation  
- Certification  
- Training  

---

## Defense‑in‑Depth

**Definition:**  
Multiple layers of security.

**Layers:**  
- Policies & Awareness  
- Physical Security  
- Perimeter Security  
- Network Security  
- Host Security  
- Application Security  
- Data Security  

**Key Idea:**  
If one layer fails, others still protect.

---

## Risk Management

**Definition:**  
Process of identifying and reducing risk.

**Phases:**  
1. Risk Identification  
   - Identify threats  
2. Risk Assessment  
   - Likelihood + Impact  
3. Risk Treatment  
   - Mitigate, transfer, accept  
4. Risk Tracking  
   - Monitor risks  
5. Risk Review  
   - Evaluate effectiveness  

---

## Cyber Threat Intelligence (CTI)

**Definition:**  
Collection and analysis of threat data.

**Types:**  
- **Strategic**  
  - High‑level (Executives)  
- **Tactical**  
  - TTPs (Managers)  
- **Operational**  
  - Specific attack info  
- **Technical**  
  - IOCs (IPs, hashes)  

---

## Threat Intelligence Lifecycle

**Phases:**  
1. Planning & Direction  
   - Define goals  
2. Collection  
   - OSINT, HUMINT, etc.  
3. Processing  
   - Convert data  
4. Analysis  
   - Generate insights  
5. Dissemination  
   - Share intelligence  

---

## Threat Modeling

**Definition:**  
Risk assessment approach used to identify, analyze, and prioritize threats to an application by understanding how it works and where it can be attacked.

**Purpose:**  
- Identify potential threats before exploitation  
- Understand system weaknesses  
- Improve secure design  

**Threat Modeling Process:**  

1. **Identify Security Objectives**  
   - Explanation: Define what needs protection (data, systems, users).  
   - Example: Protect customer payment data in an e‑commerce app.  

2. **Application Overview**  
   - Explanation: Understand components (servers, DB), data flow, and trust boundaries.  
   - Example: Web app → API → Database.  

3. **Decompose the Application**  
   - Explanation: Break system into smaller parts and identify entry points.  
   - Example: Login module, payment module.  

4. **Identify Threats**  
   - Explanation: Use frameworks like STRIDE.  
   - STRIDE:  
     - Spoofing  
     - Tampering  
     - Repudiation  
     - Information disclosure  
     - DoS  
     - Elevation of privilege  

5. **Identify Vulnerabilities**  
   - Explanation: Map threats to weaknesses.  
   - Example: Weak authentication → brute force possible.  

---

## Incident Management

**Definition:**  
A structured process to:
- Identify  
- Analyze  
- Prioritize  
- Resolve incidents  

**Goal:**  
Restore normal operations quickly and prevent recurrence.

**Components:**  
- Vulnerability Handling  
- Artifact Handling  
- Alerts  
- Announcements  

**Incident Handling (Core):**  
- Detection  
- Reporting  
- Triage  
- Response  
- Analysis  

---

## Incident Handling and Response (IH&R)

**Definition:**  
Process of responding to cyber incidents in a systematic and organized manner.

**Steps:**  
1. **Preparation**  
   - Tools, policies, training  
2. **Incident Recording & Assignment**  
   - Log incident  
   - Assign to analyst/team  
3. **Incident Triage**  
   - Determine severity and priority  
4. **Notification**  
   - Inform stakeholders  
5. **Containment**  
   - Limit damage (Example: isolate infected system)  
6. **Evidence Gathering & Forensics**  
   - Collect logs, memory dumps  
7. **Eradication**  
   - Remove root cause (malware, backdoor)  
8. **Recovery**  
   - Restore systems to normal  
9. **Post‑Incident Activities**  
   - Documentation  
   - Lessons learned  
   - Policy updates  
   - Incident closure  

---

## PCI DSS (Payment Card Industry Data Security Standard)

**Definition:**  
A global security standard for organizations handling cardholder data.

**Applies To:**  
- Merchants  
- Payment processors  
- Banks  
- Service providers  

**Key Requirements:**  
- Build secure network  
- Protect cardholder data  
- Vulnerability management  
- Strong access control  
- Monitor networks  
- Maintain security policy  

**Consequences of Non‑Compliance:**  
- Heavy fines  
- Loss of payment processing rights  

---

## ISO/IEC Security Standards

**Definition:**  
International standards for information security management.

**Important Standards:**  
- **ISO 27001** – ISMS framework  
- **ISO 27701** – Privacy Information Management  
- **ISO 27002** – Security controls best practices  
- **ISO 27005** – Risk management  
- **ISO 27018** – Cloud privacy (PII protection)  
- **ISO 27032** – Cybersecurity guidelines  
- **ISO 27033** – Network security  
- **ISO 27036** – Supply chain security  
- **ISO 27040** – Storage security  

---

## HIPAA (Health Insurance Portability and Accountability Act)

**Definition:**  
US law protecting healthcare data (PHI).

**Rules:**  
1. Privacy Rule – Protect patient data  
2. Security Rule – Ensure CIA of electronic PHI  
3. Transaction Standards – Standard formats  
4. Identifier Requirements – Unique identifiers  
5. Enforcement Rule – Compliance enforcement  

---

## Sarbanes‑Oxley Act (SOX)

**Definition:**  
Law to protect investors by ensuring accurate financial reporting.

**Key Features:**  
- Auditor independence  
- Corporate responsibility  
- Fraud accountability  

---

## DMCA & FISMA

### DMCA (Digital Millennium Copyright Act)

**Definition:**  
Protects copyrighted content.

**Key Points:**  
- Prevents unauthorized copying  
- Protects digital rights  

---

### FISMA (Federal Information Security Management Act)

**Definition:**  
Framework for securing US federal systems.

**Includes:**  
- Risk management  
- Security controls  
- Continuous monitoring  

---

## GDPR (General Data Protection Regulation)

**Definition:**  
Strict EU law for data protection and privacy.

**Key Principles:**  
- Lawfulness & transparency  
- Purpose limitation  
- Data minimization  
- Accuracy  
- Storage limitation  
- Integrity & confidentiality  
- Accountability  

**Key Feature:**  
- Heavy fines (millions of euros)  

---

## Data Protection Act 2018 (DPA)

**Definition:**  
UK law aligned with GDPR.

**Key Points:**  
- Governs personal data processing  
- Replaces 1998 Act  
- Gives rights to individuals  

**Features:**  
- Lawful processing  
- Data subject rights  
- Role of Information Commissioner  

---

## Cyber Law in Different Countries

**Purpose:**  
Defines legal frameworks for cybersecurity globally.

**Examples:**  
- Italy → Penal Code Article 615  
- Japan → Trademark Law  
- Canada → PIPEDA  
- Singapore → Computer Misuse Act  
- South Korea → Industrial Design Protection  
- Brazil → LGPD  
- Hong Kong → Basic Law  
- Philippines → Republic Act 10175  

**Importance:**  
- Legal compliance  
- International operations  
