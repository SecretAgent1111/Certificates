# FORENSIC INVESTIGATION

## Definition
Forensic Investigation is the process of identifying, collecting, preserving, analyzing, and presenting digital evidence from systems affected by cyber incidents in a legally admissible manner.

## Key Objectives
1. Track and prosecute attackers
2. Gather admissible evidence
3. Determine impact on victims
4. Reduce measurable & non-measurable losses
5. Prevent future incidents

## Core Principles
- Uses structured methodologies + tools
- Ensures evidence integrity, chain of custody, and legal admissibility
- Conducted parallel to incident response (IR)

*Example: After a ransomware attack → Collect logs (EDR, SIEM, firewall) → Identify attacker entry point → Preserve disk images → Present evidence for legal action*

**SOC Relevance:**
- SOC = first responder
- Forensics = deep investigation
- Helps validate: True Positive vs False Positive, Root cause

---

# ROLE OF FORENSICS IN SOC OPERATIONS

## 1. Incident Investigation & Analysis
- Deep analysis of incidents using forensic tools
- Identifies: Attack vector · Root cause · Impact scope

**SOC Detection:**
```splunk
index=auth_logs "Failed password"
```
**Logs:** `auth.log` · Windows Event ID 4625

**IoCs:** Multiple login failures · Unusual login times · Foreign IP addresses

---

## 2. Evidence Preservation

**Key Concept: Chain of Custody**
- Tracks: Who collected evidence · When · Where stored
- Use: Hashing (MD5/SHA256) · Write blockers

**SOC Relevance:**
- Prevents evidence tampering
- Required for compliance & legal cases

---

## 3. Enhanced Threat Detection & Response
- Forensics reveals: Advanced attack techniques · Hidden persistence mechanisms
- Improves: Detection rules · Playbooks

*Example: Malware using scheduled tasks*

---

## 4. Post-Incident Recovery
- Recover data and systems
- Update detection rules after lessons learned

*Example: Restore from backup after ransomware*

---

## 5. Compliance & Legal
- Required for: GDPR · ISO 27001 · HIPAA
- SOC provides logs + evidence for audits

---

## 6. Training & Awareness
- Forensics insights feed into SOC training updates

*Example: New phishing pattern → SOC training update*

---

# ROLE OF SOC ANALYST IN FORENSICS

## Responsibilities

**1. Initial Detection & Analysis**
- Monitor alerts
- Confirm incident

**2. Data Collection**
- Logs: SIEM · Firewall · EDR
- Maintain chain of custody

**3. In-Depth Analysis**
- Identify: Techniques · Scope

**4. Collaboration**
- Work with: IR team · Threat intel · Law enforcement

**5. Mitigation & Recovery**
- Contain threat
- Recommend fixes

**6. Documentation**
- Maintain reports
- Support legal cases

---

## SOC Investigation Flow (Real World)
1. Alert triggered
2. Validate (TP/FP)
3. Collect logs
4. Correlate events
5. Identify attacker behavior
6. Contain threat
7. Document findings

---

# FORENSIC INVESTIGATION METHODOLOGY

## Steps
1. Obtain Search Warrant
2. Evaluate & Secure Scene
3. Collect Evidence
4. Secure Evidence
5. Acquire Data
6. Analyze Data
7. Assess Evidence
8. Prepare Report
9. Testify (if required)

## SOC Mapping

| Forensic Step | SOC Equivalent |
|--------------|---------------|
| Collect Evidence | Log collection |
| Analyze Data | SIEM correlation |
| Report | Incident report |

---

# FORENSIC INVESTIGATION PROCESS

## Key Steps
1. Collect Evidence
2. Create Chain of Custody
3. Analyze Evidence
4. Create Report
5. Escalate if needed

**Decision Points:**
- Internal investigation vs law enforcement
- Third-party involvement

---

# INVESTIGATING NETWORK SECURITY INCIDENTS

## Key Activities
- Analyze: Network traffic · Logs from Routers, Firewalls, IDS/IPS, DNS
- Detect deviations: Unusual traffic patterns · Unknown protocols
- Build attack timeline

**Logs:** NetFlow · Firewall logs · DNS logs

**IoCs:** High traffic spikes → DDoS · Suspicious DNS queries · Lateral movement

---

# DDoS INVESTIGATION

**Tools:** tcpdump · Wireshark · Dshell

**Key Actions:**
- Analyze PCAP files
- Identify: Source IPs · Traffic patterns

**Example Commands:**
```bash
dshell> decode -r dns.pcap
dshell> followstream file.pcap
```

**SOC Indicators:** High requests/sec · Same IP flooding · SYN floods

---

# SESSION RECONSTRUCTION

**Tool:** NetworkMiner

**Purpose:** Rebuild sessions and file transfers

**SOC Value:** Understand attacker communication patterns

---

# APPLICATION SECURITY INCIDENTS

## Investigation Areas
1. Logs (web, APM)
2. Code review
3. Network traffic
4. Malware analysis

---

## SQL Injection (SQLi)

**Definition:** Injection of malicious SQL queries into application input.

**Indicators:** `' OR 1=1--` · `UNION SELECT` · Unexpected DB queries

**Logs to Check:** Web server logs · DB logs · WAF logs

**Example Log Pattern:**
```sql
SELECT * FROM users WHERE id='1' OR '1'='1'
```

---

## XSS (Cross-Site Scripting)

**Definition:** Injection of malicious scripts into web pages.

**Indicators:**
- `<script>` tags
- Encoded payloads: `%3C` → `<` · `%3E` → `>`

**SOC Detection:** URL parameters with script tags

---

## Cookie / Session Poisoning

**Definition:** Manipulation of session tokens.

**Indicators:**
- Modified cookies
- Missing security flags: `HttpOnly` · `Secure`

---

## CSRF (Cross-Site Request Forgery)

**Definition:** Unauthorized actions via authenticated user.

**Indicators:** Missing CSRF tokens · Suspicious POST requests

---

## CAPTCHA Bypass

**Indicators:** Same IP repeated attempts · Automated requests · Unusual user-agent

---

## Directory Traversal

**Definition:** Accessing restricted directories.

**Indicators:** `../` · `%2e%2e%2f`

*Example: `/etc/passwd` access attempt*

---

## Forensic Tool — ManageEngine EventLog Analyzer

**Features:** Log correlation · Threat detection · SQL injection detection · Real-time alerts

---

# EMAIL SECURITY INCIDENTS

## Investigation Areas

**1. Email Logs** — SMTP logs

**2. Email Headers** — Trace origin

**3. Content Analysis** — Links · Attachments

**4. Phishing Detection** — Suspicious URLs

**Email Authentication Tools:** Email Dossier · Email Address Verifier · MXToolbox

## Email Investigation Steps
1. Extract sender IP
2. Perform IP lookup
3. Identify: Location · Organization

**SOC Indicators:** Spoofed domains · Suspicious links · Attachments (`.exe`, `.zip`)

---

# INVESTIGATING INSIDER INCIDENTS

## Definition
An insider incident involves a legitimate user (employee, contractor, partner) misusing authorized access to compromise systems, data, or operations.

**Types:**
- Malicious insider (intentional)
- Negligent insider (accidental)
- Compromised insider (account takeover)

**Why Dangerous:** Bypass perimeter defenses · Already have valid credentials · Operate slow and stealthy

---

## Investigation Areas

### 1. User Activity Monitoring (UEBA)
- Detect deviations from normal behavior using baseline + anomaly detection
- Tools: UEBA, SIEM
- Logs: Login logs · File access logs

**IoCs:** Unusual login times · Access to sensitive data not part of role

*Example: User accessing files at 3 AM · Sudden spike in data downloads*

---

### 2. Access Control Analysis
- Analyze IAM logs
- Track: Privilege escalation · Unauthorized access
- Logs: Active Directory logs · IAM logs (AWS/Azure)

*Example: Normal user accessing admin panel*

---

### 3. Data Exfiltration Analysis
- Identify large data transfers
- Tools: DLP tools · Proxy logs

**IoCs:** Large outbound traffic · Use of unauthorized cloud apps

*Example: Upload to Dropbox/Google Drive*

---

### 4. Communication Analysis
- Monitor: Emails · Messaging apps
- Purpose: Detect collusion · Detect data leaks

---

## SOC Investigation Workflow
1. Alert from UEBA/DLP
2. Validate anomaly
3. Check user activity logs
4. Correlate access + data movement
5. Identify intent
6. Escalate

---

# BRUTE FORCE INVESTIGATION (JUMPLISTS)

## Definition
Brute force = repeated login attempts to guess credentials.

## Key Tool: JumpListsView
- Windows artifact
- Tracks recently accessed files
- Identifies: Files accessed post-login · Attacker activity timeline

**SOC Relevance:** Confirms successful compromise after brute force

**IoCs:** Multiple failed logins · Sudden successful login · New file access activity

---

# CREDENTIAL THEFT INVESTIGATION

## Metadata Analysis

**Definition:** Metadata = data about data (timestamps, ownership, etc.)

**Types:** File metadata · Document metadata · Network metadata · Email metadata

**What to Look For:**
- File creation/modification times
- Access history
- Hidden data

*Example: File modified at unusual time → insider activity*

**Tools:** FTK Imager · EnCase

---

## Memory Analysis

**Memory Contains:** Running processes · Credentials (in RAM) · Network connections

**Tools:** Volatility · Magnet RAM Capture

**Key Commands:**
```bash
pslist    # running processes
pstree    # process hierarchy
malfind   # hidden processes
```

**SOC IoCs:** Suspicious processes · Credential dumping tools (Mimikatz) · Hidden processes

---

# MALWARE ANALYSIS

## Definition
The process of reverse engineering malware to understand: Behavior · Origin · Impact

## Objectives
- Determine what happened
- Identify IoCs
- Understand attacker sophistication
- Find exploited vulnerabilities
- Assess damage

**SOC Relevance:** Build detection rules · Improve threat hunting · Identify persistence mechanisms

---

# TYPES OF MALWARE ANALYSIS

| Type | Description | Tools |
|------|-------------|-------|
| **Static Analysis** | Analyze without execution | PEview, Strings |
| **Dynamic Analysis** | Execute in controlled environment | Wireshark, tcpdump |

> **Best Practice: Use both static + dynamic analysis**

---

# STAGES OF MALWARE ANALYSIS
1. Static Properties Analysis
2. Interactive Behavior Analysis
3. Fully Automated Analysis
4. Manual Code Reversing

---

# SOC ANALYST APPROACH TO MALWARE

## Key Actions

**1. Analyze Unknown Programs**
- Check source
- Verify signature

**2. Examine Behavior**
- File changes
- Network activity

**3. Monitor Legitimate Tools Misuse**
- PowerShell abuse
- cmd.exe usage

**4. Memory Forensics**
- Detect in-memory malware

**5. Persistence Detection**
- Startup entries
- Scheduled tasks

**IoCs:** Suspicious processes · Unusual network connections · Registry changes

---

# MALWARE ANALYSIS CHALLENGES

- Obfuscation
- Encryption
- Large data volume
- Legal restrictions
- Privacy concerns
- Anti-analysis techniques

> **SOC Reality:** Malware often detects sandbox and changes behavior.

---

# MALWARE ANALYSIS TOOLS

| Category | Tools |
|----------|-------|
| Static Analysis | PEview, IDA Pro |
| Dynamic Analysis | Wireshark, tcpdump |
| Memory Analysis | Volatility |
| Debugging | OllyDbg |
| String Analysis | BinText |
| Hardware | Write blockers, Sandbox environment |

---

# DYNAMIC MALWARE ANALYSIS

## Definition
Execute malware in sandbox to observe behavior.

**Requirements:** Virtual Machine · Isolated environment

## Two Stages

### 1. System Baselining
- Take system snapshot before execution

### 2. Host Integrity Monitoring
- Observe changes after execution

---

# SYSTEM BASELINING

## Steps
1. Take baseline snapshot
2. Run malware
3. Take second snapshot
4. Compare differences

**Tool:** WhatChanged Portable

**SOC Value:** Detect Registry changes · File changes

---

# HOST INTEGRITY MONITORING

## System Behavior Analysis

**Monitor:**
- Registry changes
- Processes
- Services
- API calls
- Drivers
- Files

## Network Behavior Analysis

**Monitor:**
- IP connections
- Ports
- DNS queries
- Browsing activity

**IoCs:** New registry keys · Suspicious outbound traffic · New services

---

# MALWARE ANALYSIS TOOLS (DETAILED)

## ANY.RUN (Cloud Sandbox)
- Real-time interaction
- Behavior analysis
- Detailed reports
- **SOC Use:** Quick malware triage

---

## AUTORUNS
- **Purpose:** Detect persistence
- **Shows:** Startup programs · Registry autoruns
- **IoCs:** Unknown startup entries

---

## PROCESS HACKER
- **Purpose:** Monitor processes
- **Detection:** Suspicious parent-child processes
- *Example: PowerShell spawning cmd.exe*

---

## REDLINE
- Memory analysis
- Process analysis
- **Use:** Analyze RAM dumps

---

## VOLATILITY (Memory Forensics Framework)

**Key Functions:**

| Command | Purpose |
|---------|---------|
| `pslist` | List running processes |
| `pstree` | Show process hierarchy |
| `malfind` | Detect hidden/injected processes |

**SOC Use Case:** Detect rootkits and in-memory malware

---

# STATIC MALWARE ANALYSIS

## Definition
Analyzing a malware file **without executing it** to determine: Malicious intent · Capabilities · IoCs

**Key Advantage:** No risk of infection

**Limitation:** Cannot observe runtime behavior

**SOC Usage:** Email attachment analysis · Malware triage · Threat intelligence enrichment

---

## Static Analysis Techniques
1. File Fingerprinting
2. Local & Online Malware Scanning
3. Strings Analysis
4. PE Analysis
5. File Dependency Analysis
6. Disassembly / Reverse Engineering
7. Packing / Obfuscation Detection

---

## File Fingerprinting (Hash Analysis)

**Definition:** Creating a unique hash (MD5, SHA1, SHA256) to identify a file.

- Every file → unique fingerprint
- Even 1-byte change → different hash

**Process:**
1. Generate hash
2. Compare with threat databases
3. Track changes during analysis

**Tools:** HashMyFiles · HashCalc · VirusTotal

**SIEM Example:**
```
file_hash="e99a18c428cb38d5f260853678922e03"
```

**IoCs:** Known malicious hash · Hash mismatch after modification

---

## Local & Online Malware Scanning

**Local Scan:** Use AV engine · Detect known signatures

**Online Scan:** Upload to multi-engine platforms

**Example: VirusTotal** — Checks file against 70+ AV engines

**Limitation:** Cannot detect zero-day or obfuscated malware

**IoCs:** Detection by multiple AV engines · Known malware family tags

---

## Strings Analysis

**Definition:** Extract readable text (strings) from binary files.

**Why Important — Malware often contains:**
- URLs
- IP addresses
- File paths
- Commands

**Tools:** `strings` (Linux) · BinText · FLOSS

**Example Command:**
```bash
strings malware.exe
```

**What to Look For:**
- Suspicious domains
- Hardcoded credentials
- Registry keys
- File paths

**IoCs:**
```
http://malicious-domain.com/c2
```

---

## Portable Executable (PE) Analysis

**Definition:** Analyzing Windows executable file structure.

**PE Structure Includes:** Headers · Sections (.text, .data) · Imports/Exports · Metadata

**Key Information Extracted:**
- Compilation time
- Imported libraries
- Embedded strings
- Version info

**Tools:** PE Explorer · pestudio

**IoCs:** Suspicious DLL imports (e.g., `CreateRemoteThread`) · Unusual compile time

---

## File Dependency Analysis

**Definition:** Analyzing external libraries used by malware.

**Tools:** Dependency Walker · Dependency-Check · Snyk

**Suspicious APIs to Watch:**
- `WinExec`
- `LoadLibrary`
- `CreateProcess`

**SOC Relevance:** Identifies malware capabilities and persistence mechanisms

---

## pestudio Analysis

**Features:** Analyze imports/exports · Strings · Indicators

**SOC Value:** Risk scoring of malware · Quickly identify suspicious behavior

---

## Malware Disassembly

**Definition:** Converting machine code into assembly code.

**Purpose:** Understand logic · Behavior · Exploitation techniques

**Tools:** IDA Pro · Ghidra · WinDbg

**SOC Note:** Mostly used by Malware Analysts (L2/L3) — not daily L1 task, but important knowledge.

---

## Packing & Obfuscation Detection

**Definition:** Techniques used to hide malware code.

**Indicators:**
- High entropy
- No readable strings
- Suspicious section names

> Packed malware is designed to **evade detection.**

---

# FULL STATIC ANALYSIS WORKFLOW (SOC)

## Step-by-Step
1. Receive suspicious file
2. Compute hash
3. Check VirusTotal
4. Extract strings
5. Analyze PE structure
6. Check dependencies
7. Identify IoCs
8. Create detection rule

---

# REAL-WORLD SOC SCENARIO

## Suspicious Email Attachment
1. Download attachment
2. Generate SHA256 hash
3. Upload to VirusTotal
4. Extract strings
5. Identify: C2 domain · File path
6. Create SIEM alert

---

# IOC SUMMARY — STATIC ANALYSIS

| Category | IoCs |
|----------|------|
| **File-Based** | Hash values · File name patterns |
| **Network** | IPs · Domains |
| **Host-Based** | Registry keys · File paths |

---

