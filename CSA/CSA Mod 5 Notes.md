# CYBER THREAT INTELLIGENCE (CTI)

## Definition
Cyber Threat Intelligence is the collection, processing, and analysis of information about cyber threats, adversaries, and attack patterns to support informed decision-making for security operations.

> CTI is not just raw data — it is **actionable intelligence.**

---

## Core Functions

**Collection** → Gathering data from multiple sources (logs, threat feeds, OSINT)

**Analysis** → Identifying patterns, attacker behavior, trends

**Contextualization** → Turning raw data into meaningful insights

**Decision Support** → Helps organizations prevent attacks, detect threats early, and respond effectively

---

## CTI Covers
- Cybercrime (financial attacks)
- Hacktivism (political motives)
- Espionage (APT groups, nation-state attacks)

---

## Key Concept: Converting Unknown → Known
CTI helps convert unknown threats → known threats, reduce uncertainty, and improve proactive defense.

**Intelligence Output is delivered as:**
- Indicators of Compromise (IoCs)
- Threat reports
- Threat feeds

---

## Intelligence Analysis Triad

| Component | Meaning |
|-----------|---------|
| **Intent** | Why attacker is targeting (financial, espionage) |
| **Capability** | Skill level, tools, malware |
| **Opportunity** | Vulnerabilities, exposure |

---

## SOC Relevance
- Improves alert accuracy
- Reduces false positives
- Enables proactive defense
- Helps analysts prioritize threats

---

## Detection — Where CTI is Used

| Tool | Purpose |
|------|---------|
| SIEM (Splunk, Sentinel) | Log correlation |
| EDR (CrowdStrike, Defender) | Endpoint detection |
| Firewalls / IDS / IPS | Network-level blocking |

**Detection Logic Examples:**

```splunk
# IP Reputation Check
index=firewall src_ip IN (threat_intel_ip_list)

# Hash Matching
index=edr file_hash IN (known_malware_hashes)
```

**What to Monitor:**
- Known malicious IPs/domains
- Suspicious process execution
- Abnormal network behavior
- Threat feed matches

---

## Indicators (IoCs / Behavior)

**Network IoCs**
- Malicious IPs
- Suspicious domains
- C2 communication

**Host IoCs**
- Unknown processes
- Registry changes
- Suspicious file hashes

**Behavioral Indicators**
- Lateral movement
- Privilege escalation
- Data exfiltration

---

## SOC Workflow Using CTI
1. Alert triggered
2. Check IoCs in threat intelligence feeds
3. Validate → Is IP/domain malicious?
4. Analyze behavior → Matches known attack pattern?
5. Classify → True Positive / False Positive
6. Respond → Block IP / Isolate host / Escalate

---

# OBJECTIVES OF THREAT INTELLIGENCE

## Why CTI is Used

**1. Enhanced & Automated Incident Prevention**
- Block threats before execution
- Use threat feeds for auto-blocking

**2. Automation of Security Operations**
- SOAR integration
- Automated IP blocking, alert triaging

**3. Guidance to Cybersecurity Activities**
- Helps SOC focus on real threats and prioritize alerts

**4. Improved Risk Management**
- Identify high-risk assets
- Understand threat landscape

**5. Improved Incident Detection**
- Detect attacks faster using known patterns

---

# THREAT INTELLIGENCE LIFECYCLE

## 5 Phases

```
Planning → Collection → Processing → Analysis → Dissemination
```

**Phase 1: Planning & Direction**
- Define intelligence goals
- Identify requirements

**Phase 2: Collection**

| Source | Type |
|--------|------|
| OSINT | Open-source intelligence |
| HUMINT | Human intelligence |
| IMINT | Image intelligence |
| MASINT | Measurement intelligence |

**Phase 3: Processing & Exploitation**
- Clean and structure raw data
- Convert into usable format

**Phase 4: Analysis & Production**
- Combine data and generate insights (findings, predictions)
- Must be: Accurate · Timely · Actionable

**Phase 5: Dissemination & Integration**

| Level | Audience |
|-------|---------|
| Strategic | Management |
| Tactical | SOC Leads |
| Operational | Incident Responders |
| Technical | SOC Analysts |

---

## SOC Relevance
- Structured workflow for threat analysis
- Used in threat hunting, incident response, alert enrichment

**Detection Mapping:**
- Collection → Logs, SIEM data
- Processing → Normalization
- Analysis → Correlation rules
- Dissemination → Alerts, dashboards

---

# THREAT ANALYST ROLES IN CTI

## Responsibilities by Phase

**Collection Phase**
- Threat feeds, internal logs, external reports

**Processing & Exploitation**
- Indexing data, filtering noise, structuring data

**Analysis & Production**
- Analyze threats, define response actions

**Dissemination**
- Deliver intelligence to strategic, tactical, operational, and technical levels

---

# COMMON CTI CHALLENGES

## 1. Information Overload
- Too much data → hard to analyze
- **SOC Impact:** Alert fatigue

## 2. Contextual Interpretation
- Hard to understand relevance
- **SOC Impact:** Misclassification of alerts

## 3. Malware vs CTI Confusion
- CTI is broader than malware
- **SOC Insight:** Focus on attacker behavior, not just malware

## 4. IoC vs CTI Confusion
- IoC = evidence | CTI = full intelligence
- **SOC Mistake:** Relying only on IoCs

## 5. Budget & Skills
- Paid feeds required
- Skilled analysts needed

## 6. Filtering CTI Data
- Not all intelligence is useful
- **SOC Task:** Validate and filter

---

## Investigation Mindset

❌ **Bad Approach:** "IP is malicious → block immediately"

✅ **Good Approach:** Validate → Is it relevant to your environment? → Is it an active threat?

> Avoid blind IoC matching. Focus on **behavior, context, and patterns.**

---

## 🔑 Key Takeaways
- CTI = Actionable intelligence, not raw data
- Based on: Intent · Capability · Opportunity
- Lifecycle = 5 phases
- IoCs ≠ CTI
- SOC uses CTI for Detection, Enrichment, and Response
- **Biggest mistake:** Blindly trusting threat feeds

---

# THREAT INTELLIGENCE USE CASES FOR INCIDENT RESPONSE

## Definition
CTI in Incident Response (IR) integrates threat data into the incident handling process to improve detection, analysis, and response speed.

CTI transforms IR from **reactive → intelligence-driven response.**

CTI enhances IR by answering:
- Who is attacking?
- How are they attacking?
- What campaign or group is involved?
- Where else should we look in the network?

---

## Phases of Escalation in Incident Response

**Phase 1: Pre-Planning**

CTI helps answer:
- Which threat groups (APT, hackers) target the organization?
- What assets are targeted?
- What are attacker capabilities?
- What are possible attack scenarios?

*Used in threat modeling. Helps create detection rules before attack happens.*

---

**Phase 2: Event**
- CTI provides context to alerts generated by SIEM/SOC tools
- Helps determine: Is this alert serious? Should it escalate?

*Example: SIEM alert → outbound connection to suspicious IP → CTI check → IP = known C2 server → Escalate incident*

---

**Phase 3: Incident**

After compromise, CTI helps:
- Understand attacker techniques (TTPs)
- Identify attacker objectives
- Correlate with past incidents

> Use **Threat Triangle** (Intent, Capability, Opportunity)

---

**Phase 4: Breach**

If incident escalates to breach, CTI helps answer:
- What happened?
- Why it happened?
- How to prevent in future?

---

## Detection Perspective

**Data Sources:** SIEM alerts · Threat feeds · EDR telemetry · Firewall logs

**Detection Logic:**
- Correlate: Alerts + IoCs + behavior
- Prioritize: Known attacker infrastructure

**Indicators:** IPs linked to campaigns · Malware hashes · Domains used in phishing · Behavioral patterns (lateral movement)

---

## Investigation Approach
1. Validate alert
2. Enrich with CTI
3. Identify attacker pattern
4. Check lateral movement
5. Decide escalation

---

# ENHANCING INCIDENT RESPONSE USING SOPs

## Definition
SOPs are standardized procedures used by SOC analysts to handle specific types of alerts and incidents consistently.

CTI provides indicators (IoCs) like IP addresses, URLs, domains, file hashes. SOPs define how to investigate each indicator, what tools to use, and what decisions to take.

---

## SOP Design Questions

**IP Addresses**
- Is the IP critical?
- Is traffic coming from/to critical assets?
- Do we have enrichment tools (VirusTotal, etc.)?

**URLs**
- Is URL suspicious?
- Did user interact with it?

**Domain Names**
- WHOIS lookup?
- DNS activity?

**Malware Hashes**
- Present on endpoints?
- Detected by AV?

---

## Example SOP for Malicious IP
1. Check reputation
2. Check internal communication
3. Identify affected host
4. Contain system
5. Escalate

> **SOPs + CTI = efficient SOC operations**

---

# THREAT HUNTING BASED ON OSI MODEL

## Layer-wise Hunting

| Layer | Threat to Detect |
|-------|----------------|
| Application | Web attacks, malicious payloads |
| Presentation | Encoding / obfuscation attacks |
| Session | Unauthorized session activity |
| Transport | Port scanning, reconnaissance |
| Network | IP spoofing, MITM attacks |
| Data Link | ARP spoofing, MAC anomalies |
| Physical | Packet sniffing, physical interception |

## Detection Logs by Layer

| Layer | Log Source |
|-------|-----------|
| Application | Web logs |
| Transport | Netflow |
| Network | Firewall logs |
| Data Link | ARP logs |

---

# THREAT HUNTING vs THREAT INTELLIGENCE vs INCIDENT RESPONSE

| Aspect | Threat Hunting | Threat Intelligence | Incident Response |
|--------|---------------|--------------------|--------------------|
| Approach | Proactive | Analytical | Reactive |
| Focus | Unknown threats | Known threats | Active incidents |
| Goal | Find hidden attacks | Understand threats | Contain & fix |
| Skill | Deep technical | Analytical | Operational |

> All three work together: **CTI → provides data · Hunting → finds threats · IR → responds**

---

# THREAT HUNTING USING THE CYBER KILL CHAIN

## Kill Chain Stages

```
Reconnaissance → Weaponization → Delivery → Exploitation
     → Installation → Command & Control → Actions on Objectives
```

| Stage | Description | Detection |
|-------|-------------|-----------|
| Reconnaissance | Attacker gathers info, scanning | Port scan logs |
| Weaponization | Malware creation | — |
| Delivery | Phishing email, exploit kits | Email logs |
| Exploitation | Vulnerability exploited | EDR alerts |
| Installation | Malware installed | File creation logs |
| Command & Control | Attacker communicates with system | Outbound traffic |
| Actions on Objectives | Data theft, ransomware | DLP, SIEM |

> **Earlier detection = less damage. SOC should aim to stop attacks in early stages.**

---

## 🔑 Final Master Summary

| Concept | Purpose |
|---------|---------|
| CTI | Enhances Incident Response |
| SOPs | Standardize SOC workflows |
| OSI Model | Structured threat hunting |
| Kill Chain | Track attack progression |
| Threat Hunting | Proactive defense |
| Incident Response | Reactive containment |

> A strong SOC analyst uses CTI for context, SOPs for consistency, OSI + Kill Chain for investigation, and **thinks in attacker mindset.**

---

# IMPORTANT WINDOWS EVENT IDs FOR THREAT HUNTING

| Event ID | Event Name | Threat Insight |
|----------|-----------|---------------|
| **4625** | Failed Logins | High volume = brute force; outside hours = suspicious |
| **4771** | Failed Kerberos Pre-Authentication | Password spraying, brute-force attempts |
| **4672** | Special Privileges Assigned | Detect privilege escalation |
| **4698** | Scheduled Task Creation | Used for persistence, malware execution |
| **4702** | Scheduled Task Modification | Used for persistence, malware execution |
| **4794** | DSRM Password Change | Rare event → highly suspicious → attacker persistence |

---

## Detection in Splunk
```splunk
index=wineventlog EventCode=4625 | stats count by user, src_ip
```

**What to Monitor:**
- Repeated failed logins
- Privileged logins
- Scheduled task creation

**Investigation Steps:**
1. Check frequency of events
2. Identify source IP
3. Validate user account
4. Check related logs (4624, 4672)
5. Confirm attack pattern

> Always **correlate multiple events** — never rely on a single Event ID.

---

# IMPORTANT WINDOWS PROCESSES FOR THREAT HUNTING

| Process | Role | Red Flag |
|---------|------|----------|
| **svchost.exe** | Hosts Windows services | Wrong path, high CPU/network usage |
| **services.exe** | Manages services | Event ID 4697 (service install) |
| **lsass.exe** | Handles authentication | Target for Mimikatz credential dumping |
| **wininit.exe** | Starts system processes | Abnormal child processes |
| **winlogon.exe** | Handles login sessions | Shell changes in registry |
| **smss.exe** | Session manager | Abnormal parent/child relationship |
| **system.exe** | Kernel process | Running from non-standard path |

---

## What to Monitor
- Parent-child process relationships
- Process path anomalies
- Misspelled processes (e.g. `lsas.exe` vs `lsass.exe`)

**Indicators:**
- Process running from temp folder
- Abnormal parent process
- Suspicious command-line arguments

---

# THREAT HUNTING WITH POWERSHELL

## Capabilities
- Log analysis
- Network monitoring
- Process monitoring
- Automation

**Monitor:**
- PowerShell execution logs
- Script block logging

**Indicators:**
- Encoded commands
- Suspicious scripts
- Execution from unusual directories

> PowerShell = **powerful but heavily abused tool**

---

## Credential Dumping Hunting

**Detection Techniques:**

**Check for Suspicious Processes**
- Example: `mimikatz.exe`

**PowerShell Logging**
- Enable Script block logging

**Network Connections**
- Outbound suspicious connections

**SAM File Access**
- Monitor attempts to access SAM

**Investigation Steps:**
1. Check PowerShell logs
2. Identify suspicious commands
3. Check LSASS access
4. Verify outbound traffic

**Indicators:**
- Access to LSASS
- Dumping tools
- Suspicious PowerShell commands

---

## Firewall Log Anomaly Hunting

**Detection Use Cases:**

| Anomaly | Possible Threat |
|---------|----------------|
| High traffic from single IP | DDoS, scanning |
| Uncommon ports | Backdoor communication |
| Traffic spikes | Sudden increase in malicious activity |
| Blocked traffic trends | Identify malicious IPs |

**SOC Checklist:**
- Host scanning
- ICMP anomalies
- DNS anomalies
- TOR traffic
- Policy violations

> **Baseline normal traffic first → then detect anomalies**

---

## Differential Analysis

**What to Compare (Baseline vs Current):**
- Services
- Scheduled tasks
- Ports
- Users

*Used to detect persistence and unauthorized changes.*

> **Baseline = VERY IMPORTANT**

---

## PowerShell + AI in Threat Hunting

**Use Cases:**
- Automated alert response
- Threat classification
- Recommendation generation

> Future SOC = **AI-driven**

---

# THREAT HUNTING WITH YARA

## Definition
YARA is a rule-based tool used to detect malware using signatures.

## YARA Rule Structure

| Component | Description |
|-----------|-------------|
| **Meta** | Description, author |
| **Strings** | Patterns to match |
| **Condition** | Logic for detection |

**Types of Detection:**
- File-based
- Hash-based
- String-based
- Network-based

**Indicators:** Known malware patterns · Suspicious strings

---

# THREAT HUNTING WITH SYSMON

## Key Events

| Event ID | Event | Detection Use |
|----------|-------|--------------|
| **1** | Process Creation | Detect suspicious processes |
| **3** | Network Connections | Detect malicious IP communication |
| **11** | File Creation | Detect suspicious files |
| **13** | Registry Changes | Detect persistence |

**Detection Examples:**
- Suspicious parent process
- Malicious IP connection
- Registry persistence

> Sysmon = **advanced visibility into Windows activity**

---

# LINUX: NEW USER ACCOUNT HUNTING

**Detection Methods:**
```bash
grep useradd /var/log/auth.log
```

**Log Files:**
- `/var/log/auth.log`
- `/var/log/secure`

**Indicators:**
- New user creation
- Sudo privileges granted unexpectedly

---

# WEB SHELL HUNTING

## Definition
Web shell = malicious script that gives attacker remote control over a web server.

**Suspicious Functions to Detect:**
- `exec()`
- `system()`
- `shell_exec()`

**Suspicious File Names:**
- `cmd.php`
- `shell.php`

**Detection Tools:**
- LMD
- NeoPI

**Indicators:**
- Unusual files in web directories
- Obfuscated code

---

# IIS MALICIOUS MODULE HUNTING

**Detection:**
- Check `w3wp.exe` process
- Look for abnormal DLLs

**Indicators:**
- Unknown modules loaded
- Suspicious child processes

> Advanced persistence technique used to maintain access through IIS web servers.

---

# THREAT HUNTING WITH SPLUNK QUERIES

## Key Use Cases

**1. Detect Obfuscated PowerShell**
```splunk
index=windows_logs EventCode=4104
| search ScriptBlockText="Invoke-Expression" OR ScriptBlockText="FromBase64String"
```

**2. High Frequency PowerShell Usage**
```splunk
index=windows_logs EventCode=4104
| stats count by user, host
| sort -count
```

**3. Suspicious Cmdlets**
```splunk
ScriptBlockText="Invoke-Mimikatz" OR ScriptBlockText="DownloadString"
```

**4. Encoded Commands**
```splunk
CommandLine="*EncodedCommand*"
```

**5. Bitsadmin Usage (Malware Download)**
```splunk
NewProcessName="bitsadmin.exe"
```

---

## What to Monitor
- PowerShell logs (Event ID 4104)
- Process creation
- Command-line arguments

**Indicators:**
- Encoded scripts
- Mimikatz usage
- Abnormal script frequency

---

# THREAT HUNTING WITH DNS LOGS

## Detection Use Cases

| Indicator | Threat |
|-----------|--------|
| Many random-looking domains | DGA (Domain Generation Algorithm) |
| Suspicious TLDs (.xyz, .tk, .biz) | Malware C2 |
| High NXDOMAIN rate | Failed C2 lookups / scanning |
| Long / high-entropy domains | DNS tunneling |
| Newly registered domains | Phishing / malware |
| Low TTL values | Fast-changing attacker infrastructure |
| Unusual DNS traffic / zone transfers | DNS tunneling |

> DNS logs = **goldmine for detection.** Always analyze patterns.

---

# AUTOMATE THREAT HUNTING USING SOAR

## Definition
SOAR (Security Orchestration, Automation, and Response) automates incident response, threat hunting, and playbook execution.

## Automated Playbook Flow
```
Ingest IoCs → Extract IoCs → Hunt across tools → Update databases → Close playbook
```

**Integrates with:** SIEM · EDR · Threat intelligence feeds

> SOAR = **automation backbone of SOC**

---

# THREAT HUNTING WITH EDR / XDR

| Feature | EDR | XDR |
|---------|-----|-----|
| Scope | Endpoint only | Multi-layer (endpoint + network + cloud) |
| Detection | Process, file, behavior | Cross-source correlation |
| Use Case | Endpoint threats | Broader attack detection |

**Monitor:**
- Process creation
- File changes
- Network connections

---

# TOOLS USED FOR THREAT HUNTING

| Tool Category | Purpose |
|--------------|---------|
| **EDR** | Detect endpoint threats |
| **UEBA** | Detect anomalies in user behavior |
| **NTA** | Detect abnormal traffic |
| **NDR / NBA** | Behavioral analysis of network |
| **TIP** | Threat Intelligence Platforms — provide IoCs |
| **SIEM** | Log collection and analysis |

> No single tool is enough — **layered detection is key.**

---

# THREAT HUNTING PLATFORMS

- CrowdStrike Falcon
- VMware Carbon Black
- Trend Micro XDR
- Exabeam
- Mantix
- Cynet 360
- YARA
- Maltego

---

# THREAT HUNTING BEST PRACTICES

1. **Understand the Environment** — Know assets, users, traffic
2. **Full Visibility** — Logs + endpoints + network
3. **Stay Updated** — Latest threats and TTPs
4. **Use Automation** — SOAR, scripts
5. **Use UEBA** — Detect behavioral anomalies
6. **Perform Scans** — Internal + external
7. **Dark Web Monitoring** — Threat intel gathering
8. **Ethical Hacking** — Find weaknesses proactively
9. **Follow the OODA Loop**

---

## OODA Loop

```
Observe → Orient → Decide → Act
Detect  → Analyze → Plan  → Respond
```

---

## 🔑 Final Master Summary

| Skill | Application |
|-------|-------------|
| Windows Event Log Analysis | Core detection |
| Process Monitoring | Detect injection & credential dumping |
| PowerShell Hunting | Detect malicious scripts |
| Sysmon Analysis | Advanced endpoint visibility |
| YARA Rules | Malware identification |
| Linux Log Analysis | Detect unauthorized access |
| Web Shell Detection | Detect server compromise |

> A strong SOC analyst knows key Event IDs, understands processes deeply, uses PowerShell for automation, and **detects behavior — not just IoCs.**
