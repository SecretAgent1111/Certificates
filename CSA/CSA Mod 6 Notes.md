# INCIDENT RESPONSE (IR)

## Definition
Incident Response is a systematic and structured approach to handle security incidents with the goals of minimizing damage, reducing recovery time, and lowering operational costs.

> IR is not just about fixing attacks — it is a **full lifecycle process.**

---

## IR Lifecycle

```
Preparation → Detection & Analysis → Triage → Containment → Eradication → Recovery → Post-Incident
```

**Includes:**
- Technical actions → containment, eradication, recovery
- Non-technical actions → communication, legal handling, policy enforcement

---

## SOC Relevance
- Detecting incidents
- Investigating alerts
- Escalating and documenting incidents

**Detection Sources:** SIEM alerts · IDS/IPS logs · EDR alerts · Firewall logs

**IoCs:** Multiple failed login attempts · Suspicious IPs · Unusual network traffic spikes

> IR = **Process, not a tool.** Goal: minimize impact, not just stop attack.

---

# PREPARATION FOR INCIDENT RESPONSE

## Two Scenarios

| Scenario | Actions |
|----------|---------|
| IR process exists | Evaluate → Identify gaps → Improve |
| No IR process | Define vision → Get approval → Build plan & team |

## Key Steps
- Define IR vision & mission
- Obtain funding and approvals
- Develop IR policies and procedures
- Define incident criteria
- Build IR team
- Evaluate security posture
- Harden systems if required

**SOC Relevance:** Defines playbooks, escalation paths, and alert handling procedures.

> **Preparation is the most critical phase. Without it → response fails.**

---

# IR PLAN, POLICY & PROCEDURES

## The Difference

| Component | What It Is | Answers |
|-----------|-----------|---------|
| **Policy** | High-level guidelines | WHAT |
| **Plan** | Future course of action | WHO & WHEN |
| **Procedure (SOP)** | Step-by-step instructions | HOW |

---

## IR Plan — Key Components
- Mission and vision statements
- Goals of IR initiative
- Management approval
- Strategy and timelines
- Performance metrics
- Resource utilization
- Organizational alignment

---

## IR Policy — Must Contain
1. Management commitment
2. Purpose and objectives
3. Scope
4. Definition of incidents
5. Roles and responsibilities
6. Severity prioritization
7. Performance metrics
8. Reporting guidelines
9. Communication guidelines

---

## IR Procedures (SOPs)
Includes processes, techniques, templates, and forms.

**Objective:** Standardize response · Reduce human errors · Enable automation

**Example SOP for malware containment:**
1. Isolate system
2. Capture memory
3. Block IoC

> SOC analysts strictly follow SOPs. Automated via SOAR playbooks.

---

# BUILD INCIDENT RESPONSE TEAM (IRT)

## Steps
- Design IR plan → Set expectations → Define mission & vision → Communicate plan → Hire/train team → Announce team → Evaluate effectiveness

## IRT Composition
- SOC analysts
- Incident handlers
- Forensics experts
- Management
- Legal team

> Cross-functional team is required. SOC is part of IRT.

---

# COMPUTER FORENSICS LAB

**Components:** Planning & budgeting · Location · Work area setup · Skilled personnel · Physical security · Licensing

**Used to:** Analyze malware · Investigate breaches · Preserve evidence

> **Evidence integrity is critical — maintain chain of custody.**

---

# INCIDENT TRIAGE

## Definition
Process of prioritizing incidents based on severity.

## Steps
1. Incident analysis & validation
2. Classification
3. Check if within scope
4. Prioritize

- High priority → immediate response
- Low priority → scheduled handling

> SOC analysts perform triage daily. Triage = **prioritization.**

---

# INCIDENT ANALYSIS AND VALIDATION

## Definition
Verifying whether an alert is a real incident (True Positive).

## Steps
- Log analysis
- Event correlation
- Network/system profiling

**Determine:**
- Attack vector
- Affected systems
- Impact assessment

*Example: Correlate failed logins + successful login → brute force confirmed*

**IoCs:** Suspicious login patterns · Abnormal traffic · Malware signatures

---

# INCIDENT CLASSIFICATION

## Categorized By
- Severity
- Impact
- Attack type

**Factors:** Nature of incident · Criticality of systems · Legal requirements

| Example | Severity |
|---------|---------|
| Malware | Medium |
| Data breach | High |

---

# SEVERITY ASSESSMENT

## Formula

```
Risk = Likelihood × Impact × Asset Value
```

- **Likelihood** = probability of attack
- **Impact** = damage caused
- **Asset Value** = importance of affected system

> Helps SOC prioritize incidents using **risk-based decision making.**

---

# CONTAINMENT

## Definition
Limiting the spread of an incident.

## Process
- Decide containment strategy
- Assign tasks to: Technical team · Management · Legal
- Check if contained → If not → update strategy → If yes → proceed to eradication

**SOC Actions:** Block IP · Disable accounts · Network segmentation

**IoCs:** Lateral movement attempts · C2 communication

> **Short-term vs long-term containment** — always isolate first, then investigate.

---

# ERADICATION

## Definition
Removing the root cause of the incident.

## Steps
1. Identify root cause
2. Eliminate threat
3. Check similar systems
4. Patch vulnerabilities
5. Harden systems

**Actions:** Update antivirus · Apply patches · Remove malware · Close attack vectors

**IoCs:** Malware files · Registry changes · Persistence mechanisms

> Malware removal ≠ eradication → **must fix root cause.**

---

# RECOVERY

## Definition
Restoring systems to normal operations.

## Steps
1. Restore data from clean backups
2. Ensure backup is clean
3. Restart services
4. Verify no malware remains
5. Ensure business continuity

> **Clean backup validation is critical.** Monitor systems post-recovery.

---

# POST-INCIDENT ACTIVITIES

## Definition
Actions performed after incident resolution to improve future response and strengthen security posture.

## Steps

**1. Incident Documentation**
- Timeline of attack
- Actions taken
- Tools used
- Impact
- Maintain evidence for legal/compliance

**2. Incident Impact Assessment**
- Affected systems
- Data loss
- Financial/business impact

**3. Review and Revise Policies**
- Update detection rules
- Update IR playbooks
- Update security policies

**4. Close the Investigation**
- No residual threats
- All systems stable

**5. Incident Disclosure**
- Notify: Management · Customers (if needed) · Regulatory bodies

**SOC Relevance:** Create new SIEM rules · Improve detection accuracy · Reduce false positives

**IoCs discovered:** New attacker IPs/domains · Malware hashes

> **Lessons Learned phase = critical for continuous improvement.**

---

# UNAUTHORIZED ACCESS INCIDENTS

## Containment Actions

1. **Isolate Affected Systems** — Prevent lateral movement, disconnect compromised hosts
2. **Disable Affected Services** — Disable FTP, RDP
3. **Block Attacker Routes** — Block IPs, kill sessions
4. **Disable Compromised Accounts** — Reset passwords, disable accounts
5. **Enhance Physical Security** — Secure server rooms, restrict access

**IoCs:** Login from unusual geolocation · Multiple sessions from different IPs · Privilege escalation logs

---

## Recovery Steps
1. Identify attack type (entry point, exploited vulnerability)
2. Mitigate vulnerabilities — patch and harden
3. Restore data from clean backups
4. Bring systems to operational state
5. Apply OS and application updates
6. Enable enhanced logging
7. Update access control policies

> Recovery must ensure **no persistence remains.**

---

# INAPPROPRIATE USAGE INCIDENTS

## Containment Actions
- Shut down infected systems
- Filter ports/protocols
- Block malicious emails
- Install spam filters
- Block malicious URLs
- Limit user privileges
- Reset passwords
- Track user activity

**Detection Sources:** Web proxy logs · Email logs · DNS logs

**IoCs:** Access to suspicious domains · Large downloads from unknown sources

---

## Eradication Actions
- Deploy firewall & IDS/IPS
- Configure email servers (block spam)
- Enable URL filtering
- Enforce encrypted protocols (HTTPS, SSH, IPSec)
- Use VPNs
- Monitor user activity logs

---

## Recovery Actions
- Inform legal team
- Involve HR
- Conduct employee training
- Educate on safe browsing
- Update policies
- Update antivirus

> Involves HR + legal → **non-technical IR aspect.**

---

# APPLICATION SECURITY INCIDENTS

## Containment Actions
1. Enable rate limiting (blackhole feature)
2. Increase server capacity
3. Define user thresholds
4. Restrict unauthorized access
5. Business continuity planning
6. Alert users during incidents
7. Deploy traffic filters
8. Restore systems and fix vulnerabilities

**Detection Sources:** WAF logs · Traffic spikes · API abuse

*Example: DDoS attack → rate limiting + scaling servers*

---

## Eradication — Web Application Controls

| Control | Purpose |
|---------|---------|
| Input Validation | Prevent injection attacks |
| WAF / IDS | Filter malicious traffic |
| Secure Coding | Avoid hardcoded credentials, minimize privileges |
| Database Security | Use parameterized queries |
| Logging & Testing | Dynamic testing, code analysis |
| System Hardening | Disable unnecessary services, patch systems |
| Output Handling | Sanitize outputs |

---

## Eradicating Specific Attack Types

**SQL Injection**
- Use parameterized queries
- WAF protection
- Disable dangerous DB features

**Command Injection**
- Validate inputs
- Escape characters
- Use safe APIs

**File Injection**
- Disable risky PHP settings
- Validate file paths

**LDAP Injection**
- Validate inputs
- Limit query results

**IoCs:** `' OR 1=1` · Suspicious command execution · Unexpected DB queries

> **Input validation is the key defense.**

---

**Broken Authentication Controls**
- Use SSL/TLS · Hash passwords · Avoid session in URLs · Use MFA · Enforce password policies · Limit login attempts · Secure session IDs · Implement session timeout

**IoCs:** Brute-force attempts · Session hijacking

---

**Sensitive Data Exposure Controls**
- Encrypt sensitive data · Avoid weak crypto · Proper key management · Use strong algorithms · Enable HSTS · Disable caching for sensitive data

**IoCs:** Plaintext credentials · Unencrypted traffic

---

**Broken Access Control**
- Enforce access checks · Avoid predictable IDs · Session timeout · Limit permissions · Remove session tokens after logout

---

**Security Misconfiguration**
- Disable unused services · Remove default accounts · Apply patches · Enforce HTTPS · Secure cookies · Validate certificates · Encrypt backend communication

**IoCs:** Default credentials · Open ports/services

---

**XSS Attacks**
- Validate all inputs · Encode outputs · Use CSP · Filter scripts · Convert special characters

**IoCs:** `<script>` tags in input · Suspicious JavaScript execution

---

**Insecure Deserialization**
- Validate serialized data · Avoid untrusted deserialization · Restrict classes · Filter serialized inputs

**IoCs:** Unexpected object execution · Application crashes

---

**Insufficient Logging & Monitoring**
- Define logging scope · Set logging baseline · Include user context · Log for proactive detection · Prevent log injection

> **"If it's not logged, it's not detectable."**

---

# INSIDER THREATS

## Definition
Malicious or negligent actions by trusted individuals — employees, contractors, vendors.

**Objectives:** Prevent further damage · Preserve evidence · Limit access and data exposure

---

## Containment Actions

1. **Isolate Affected Systems** — Disconnect compromised endpoints
2. **Block All Access** — Disable email, application access, physical access (ID cards), VPN credentials
3. **Seize Devices** — Collect laptops, mobile devices; preserve for forensics
4. **Inform Stakeholders** — Notify impacted departments, assess business impact
5. **Continuous Monitoring** — Track suspect activity, await legal/management decision
6. **Forensic Investigation** — Analyze portable devices and account activity logs
7. **Legal Action** — File complaint as per jurisdiction
8. **Restrict Physical Entry** — Prevent suspect from entering premises
9. **Protect Information Flow** — Limit insider knowledge exposure
10. **Organization-wide Password Reset** — Prevent further compromise

**IoCs:** Large data transfers · Access outside working hours · Access to unauthorized systems

> Insider threats require **technical + HR + legal coordination.**

---

## Eradication Controls

**A. Access Control**
- Least privilege principle
- Role-based access control (RBAC)

**B. Data Encryption**
- Encrypt data at rest, in transit, and in use
- Use strong encryption (≥256-bit keys)

**C. Isolate Storage**
- Avoid storing sensitive data on network-accessible systems

**D. Password Policies**
- Enforce strong password rules
- Regular password changes

**E. Data-Centric Protection (DCAP)**
- Monitor user access and data movement
- Detect privilege misuse

> **Least privilege is the strongest defense.** Use UBA/UEBA for behavioral monitoring.

---

## Human Resources Controls
1. Define strict employee behavior policies
2. Conduct employee behavior analysis
3. Monitor financial stress indicators
4. Manage workplace conflicts
5. Provide security awareness training
6. Perform background checks
7. Monitor third-party vendors

> Insider threats are often **behavioral, not just technical.**

---

## Network Security Controls
1. Configure firewalls
2. Monitor outbound traffic
3. Restrict file transfers
4. Disable unauthorized sharing tools
5. Scan emails for sensitive data
6. Enforce MFA
7. Implement account management policies

**IoCs:** Upload to cloud storage · Use of unauthorized tools

---

## Access Controls
1. Grant access based on job role
2. Restrict software installation and log modification
3. Enable admin alerts for changes
4. Regular access audits
5. Strict sensitive data access policies
6. Supervisor approval for access
7. Data owner permission required
8. Remove access after termination

> **Access should be revoked immediately after exit.**

---

## Privileged User Controls
1. Non-repudiation logging
2. Disable default admin accounts
3. Use unique admin accounts
4. Encrypt sensitive backups
5. Monitor admin activities

**IoCs:** Admin activity at unusual times · Unauthorized config changes

---

## Log Monitoring Controls
1. Enforce logging policies
2. Perform regular audits
3. Enable audit trails
4. Monitor changes to critical systems
5. Protect logs from tampering
6. Use IDS & file integrity monitoring

> **Logs must be centralized and immutable.**

---

## Physical Security Controls
- Auto-lock systems
- Secure data centers
- Block portable media
- Use biometric authentication
- Lock storage devices
- CCTV surveillance
- Soundproof meeting rooms
- Secure disposal (shredding)
- Wipe storage devices
- Enforce vendor policies

> Many breaches happen via **USB devices.**

---

## Recovery from Insider Attacks
1. Collect legal evidence
2. Reset passwords
3. Remove malware
4. Restore systems from backups
5. Implement backup strategy
6. Secure backup storage
7. Separate duties (backup roles)
8. Enforce backup security policies
9. Maintain chain-of-custody
10. Improve backup planning

---

# MALWARE INCIDENTS

## Containment Steps
1. Isolate infected host
2. Analyze network logs
3. Cut network services (if widespread)
4. Use VLAN isolation
5. Allow only safe communication (VPN)
6. Identify malware patterns/signatures
7. Disable vulnerable services

**IoCs:** Suspicious processes · C2 traffic · Unknown binaries

---

## Eradication Actions
- Patch vulnerabilities
- Share malware intelligence
- Implement application whitelisting
- Block malicious websites
- Prevent auto-downloads
- Restrict BIOS/system access (virtualization)
- Secure browser settings: Block pop-ups · Disable auto-downloads

> Malware removal ≠ eradication → **must fix root cause.**

---

## Recovery Steps
1. Wipe disks if required
2. Reimage systems
3. Restore clean backups
4. Scan systems with updated AV
5. Restore email services
6. Enable attachment scanning
7. Disable file sharing temporarily
8. Restore cloud data safely
9. Reinstall applications
10. Restore system configurations

**IoCs post-recovery:** Reinfection attempts · Residual malware artifacts

---

# ENDPOINT DETECTION AND RESPONSE (EDR)

## Definition
EDR is a security solution that monitors endpoint activities, detects threats using behavioral analysis, and investigates and responds to incidents in real time.

## Core Functions
- Continuous monitoring of endpoints
- Detection of IoCs and behavioral anomalies
- Threat investigation
- Automated response actions

---

## How EDR Works

**Data Collection**
- Process execution logs
- File activity
- Registry changes
- Network connections

**Analysis**
- Behavioral analytics (not just signatures)
- Detects fileless malware and living-off-the-land attacks

**Response**
- Alert SOC team
- Trigger automated actions

---

## IR Using EDR

| Capability | Description |
|-----------|-------------|
| Alert Generation | Affected endpoint, attack type, timeline |
| Data Collection | Detailed telemetry for investigation |
| Automated Response | Endpoint isolation, network blocking, process termination |

**Example Workflow:**
1. Alert triggered (malware detected)
2. Analyst reviews process tree and file hashes
3. Kill process → Isolate system
4. Remediation applied

**IoCs:** Suspicious processes · Unknown executables · Privilege escalation attempts

> EDR = **Detection + Response + Forensics.** Detects behavior, not just signatures. Critical for fileless malware.

---

## Detecting Ransomware Using EDR

**Data Collected:** Process execution · File changes · Registry activity · Network connections

**Investigation Steps:**
1. **Memory Analysis** — Capture RAM for fileless malware
2. **Timeline Creation** — Identify attack sequence
3. **File Analysis** — Detect mass file encryption, file renaming patterns
4. **Network Analysis** — Detect C2 communication, data exfiltration
5. **Persistence Check** — Registry keys, scheduled tasks

**SOC IoCs:**
- Rapid file encryption
- Unknown processes modifying files
- Suspicious extensions (`.locked`, `.encrypted`)
- High CPU/disk usage

*Example: `powershell.exe` → downloads payload → encrypts files*

> Ransomware detection relies on **behavior patterns.**

---

## Notable EDR Tools

**Cybereason EDR**
- Detects ransomware & fileless attacks
- Uses threat intelligence + behavioral analytics
- Lightweight agent, centralized dashboard, automated investigation, cross-endpoint visibility

**RSA NetWitness EDR**
- Endpoint + network visibility
- Prioritized alerts
- Deep investigation with attack reconstruction (timeline)

---

# EXTENDED DETECTION AND RESPONSE (XDR)

## Definition
XDR extends EDR by integrating multiple security layers — Endpoint · Network · Cloud · Email · Applications

```
XDR = EDR + NDR + SIEM-like correlation + AI
```

## Why XDR is Needed
- EDR limitation → only endpoint visibility
- XDR solves → cross-platform visibility

## XDR Features
- Unified visibility
- AI/ML-based detection
- Automated response
- Threat correlation across layers

---

## XDR Architecture

```
Ingest → Detection → Response
(Email, Firewall, Network, Endpoint, Cloud) → (Alert prioritization, Correlation) → (Automated workflows, Threat hunting)
```

*Example: Phishing email → user clicks → endpoint infected → XDR correlates email + endpoint + network logs → detects full attack chain*

---

## EDR vs XDR

| Feature | EDR | XDR |
|---------|-----|-----|
| Scope | Endpoint only | Multiple layers |
| Detection | Local | Correlated |
| Visibility | Limited | Unified |
| Response | Endpoint actions | Cross-system |

---

# SECURITY ORCHESTRATION, AUTOMATION, AND RESPONSE (SOAR)

## Definition
SOAR integrates security tools, processes, and people to automate and orchestrate incident response workflows.

## Core Purpose
- Automate repetitive security tasks
- Improve incident response speed
- Reduce manual workload
- Enhance threat visibility and coordination

---

## Key Functions

**Orchestration** — Connects multiple security tools (SIEM, EDR, Firewalls, TIP)

**Automation** — Executes predefined actions: Block IP · Isolate endpoint · Send alerts

**Response** — Enables faster and consistent incident handling

---

## SOAR Capabilities
- Aggregates security data from multiple sources
- Automates data collection, alert triage, initial investigation
- Integrates threat intelligence feeds
- Provides centralized dashboards
- Generates reports for compliance and auditing

---

## Without SOAR vs With SOAR

| Without SOAR | With SOAR |
|-------------|----------|
| Analyst receives alert | Alert triggered |
| Manually checks logs | SOAR auto-enriches data (IP reputation) |
| Blocks IP manually | Auto-blocks IP |
| Sends email to team | Auto-notifies team + creates ticket |

---

## SOAR Playbook

A predefined workflow that automates incident response actions.

**Playbook Components:**
- Playbook Version & Date
- Owner/Reviewer
- Metrics & Reporting
- Execution Platform
- Incident Documentation
- Communication Plan
- Resolution Steps

**Types of Actions:**

| Type | Examples |
|------|---------|
| Automated | Block IP, quarantine file, disable account |
| Manual | Analyst investigation, decision-making |

**Example: Phishing Playbook**
1. Extract email indicators
2. Check URL reputation
3. If malicious → Block domain → Quarantine email → Notify users
4. Create incident report

> Playbooks = **SOPs implemented in automation.** Used daily in SOC operations.

---

## Integrating SOAR with SIEM

```
SIEM detects → SOAR responds
```

**Workflow:**
1. SIEM generates alert
2. SOAR triggers playbook
3. Automated response executed
4. Analyst reviews outcome

**Use Cases:**

| Scenario | SIEM | SOAR |
|----------|------|------|
| Phishing | Detects phishing email | Quarantines email, blocks sender, notifies user |
| Malware | Detects suspicious activity | Isolates endpoint, triggers scan, updates threat intel |
| Data Breach | Detects exfiltration | Blocks access, starts containment, alerts SOC |

---

## SIEM vs SOAR

| Feature | SIEM | SOAR |
|---------|------|------|
| Function | Detection | Response |
| Role | Alerting | Automation |
| Focus | Logs & correlation | Actions & workflows |

---

## SOAR Tools (Industry)
- ServiceNow Security Incident Response
- IBM QRadar SOAR
- Swimlane SOAR
- D3 Security
- Heimdal Threat Hunting Platform
- **Splunk SOAR** — centralized visibility, playbook creation, third-party integration, automated account monitoring

---

# FINAL MASTER SUMMARY

## Modern SOC Stack

| Tool | Role |
|------|------|
| **SIEM** | Detects threats via log correlation |
| **EDR** | Endpoint visibility & response |
| **XDR** | Cross-platform detection & correlation |
| **SOAR** | Automation & orchestration |

## Real SOC Workflow

```
SIEM detects → EDR provides endpoint data → XDR correlates → SOAR automates response
```


