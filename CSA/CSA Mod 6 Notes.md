INCIDENT RESPONSE (IR)
Definition
Incident Response is a systematic and structured approach to handle security incidents with the goals of minimizing damage, reducing recovery time, and lowering operational costs.

IR is not just about fixing attacks — it is a full lifecycle process.


IR Lifecycle
Preparation → Detection & Analysis → Triage → Containment → Eradication → Recovery → Post-Incident
Includes:

Technical actions → containment, eradication, recovery
Non-technical actions → communication, legal handling, policy enforcement


SOC Relevance

Detecting incidents
Investigating alerts
Escalating and documenting incidents

Detection Sources: SIEM alerts · IDS/IPS logs · EDR alerts · Firewall logs
IoCs: Multiple failed login attempts · Suspicious IPs · Unusual network traffic spikes

IR = Process, not a tool. Goal: minimize impact, not just stop attack.


PREPARATION FOR INCIDENT RESPONSE
Two Scenarios
ScenarioActionsIR process existsEvaluate → Identify gaps → ImproveNo IR processDefine vision → Get approval → Build plan & team
Key Steps

Define IR vision & mission
Obtain funding and approvals
Develop IR policies and procedures
Define incident criteria
Build IR team
Evaluate security posture
Harden systems if required

SOC Relevance: Defines playbooks, escalation paths, and alert handling procedures.

Preparation is the most critical phase. Without it → response fails.


IR PLAN, POLICY & PROCEDURES
The Difference
ComponentWhat It IsAnswersPolicyHigh-level guidelinesWHATPlanFuture course of actionWHO & WHENProcedure (SOP)Step-by-step instructionsHOW

IR Plan — Key Components

Mission and vision statements
Goals of IR initiative
Management approval
Strategy and timelines
Performance metrics
Resource utilization
Organizational alignment


IR Policy — Must Contain

Management commitment
Purpose and objectives
Scope
Definition of incidents
Roles and responsibilities
Severity prioritization
Performance metrics
Reporting guidelines
Communication guidelines


IR Procedures (SOPs)
Includes processes, techniques, templates, and forms.
Objective: Standardize response · Reduce human errors · Enable automation
Example SOP for malware containment:

Isolate system
Capture memory
Block IoC


SOC analysts strictly follow SOPs. Automated via SOAR playbooks.


BUILD INCIDENT RESPONSE TEAM (IRT)
Steps

Design IR plan → Set expectations → Define mission & vision → Communicate plan → Hire/train team → Announce team → Evaluate effectiveness

IRT Composition

SOC analysts
Incident handlers
Forensics experts
Management
Legal team


Cross-functional team is required. SOC is part of IRT.


COMPUTER FORENSICS LAB
Components: Planning & budgeting · Location · Work area setup · Skilled personnel · Physical security · Licensing
Used to: Analyze malware · Investigate breaches · Preserve evidence

Evidence integrity is critical — maintain chain of custody.


INCIDENT TRIAGE
Definition
Process of prioritizing incidents based on severity.
Steps

Incident analysis & validation
Classification
Check if within scope
Prioritize


High priority → immediate response
Low priority → scheduled handling


SOC analysts perform triage daily. Triage = prioritization.


INCIDENT ANALYSIS AND VALIDATION
Definition
Verifying whether an alert is a real incident (True Positive).
Steps

Log analysis
Event correlation
Network/system profiling

Determine:

Attack vector
Affected systems
Impact assessment

Example: Correlate failed logins + successful login → brute force confirmed
IoCs: Suspicious login patterns · Abnormal traffic · Malware signatures

INCIDENT CLASSIFICATION
Categorized By

Severity
Impact
Attack type

Factors: Nature of incident · Criticality of systems · Legal requirements
ExampleSeverityMalwareMediumData breachHigh

SEVERITY ASSESSMENT
Formula
Risk = Likelihood × Impact × Asset Value

Likelihood = probability of attack
Impact = damage caused
Asset Value = importance of affected system


Helps SOC prioritize incidents using risk-based decision making.


CONTAINMENT
Definition
Limiting the spread of an incident.
Process

Decide containment strategy
Assign tasks to: Technical team · Management · Legal
Check if contained → If not → update strategy → If yes → proceed to eradication

SOC Actions: Block IP · Disable accounts · Network segmentation
IoCs: Lateral movement attempts · C2 communication

Short-term vs long-term containment — always isolate first, then investigate.


ERADICATION
Definition
Removing the root cause of the incident.
Steps

Identify root cause
Eliminate threat
Check similar systems
Patch vulnerabilities
Harden systems

Actions: Update antivirus · Apply patches · Remove malware · Close attack vectors
IoCs: Malware files · Registry changes · Persistence mechanisms

Malware removal ≠ eradication → must fix root cause.


RECOVERY
Definition
Restoring systems to normal operations.
Steps

Restore data from clean backups
Ensure backup is clean
Restart services
Verify no malware remains
Ensure business continuity


Clean backup validation is critical. Monitor systems post-recovery.


POST-INCIDENT ACTIVITIES
Definition
Actions performed after incident resolution to improve future response and strengthen security posture.
Steps
1. Incident Documentation

Timeline of attack
Actions taken
Tools used
Impact
Maintain evidence for legal/compliance

2. Incident Impact Assessment

Affected systems
Data loss
Financial/business impact

3. Review and Revise Policies

Update detection rules
Update IR playbooks
Update security policies

4. Close the Investigation

No residual threats
All systems stable

5. Incident Disclosure

Notify: Management · Customers (if needed) · Regulatory bodies

SOC Relevance: Create new SIEM rules · Improve detection accuracy · Reduce false positives
IoCs discovered: New attacker IPs/domains · Malware hashes

Lessons Learned phase = critical for continuous improvement.


UNAUTHORIZED ACCESS INCIDENTS
Containment Actions

Isolate Affected Systems — Prevent lateral movement, disconnect compromised hosts
Disable Affected Services — Disable FTP, RDP
Block Attacker Routes — Block IPs, kill sessions
Disable Compromised Accounts — Reset passwords, disable accounts
Enhance Physical Security — Secure server rooms, restrict access

IoCs: Login from unusual geolocation · Multiple sessions from different IPs · Privilege escalation logs

Recovery Steps

Identify attack type (entry point, exploited vulnerability)
Mitigate vulnerabilities — patch and harden
Restore data from clean backups
Bring systems to operational state
Apply OS and application updates
Enable enhanced logging
Update access control policies


Recovery must ensure no persistence remains.


INAPPROPRIATE USAGE INCIDENTS
Containment Actions

Shut down infected systems
Filter ports/protocols
Block malicious emails
Install spam filters
Block malicious URLs
Limit user privileges
Reset passwords
Track user activity

Detection Sources: Web proxy logs · Email logs · DNS logs
IoCs: Access to suspicious domains · Large downloads from unknown sources

Eradication Actions

Deploy firewall & IDS/IPS
Configure email servers (block spam)
Enable URL filtering
Enforce encrypted protocols (HTTPS, SSH, IPSec)
Use VPNs
Monitor user activity logs


Recovery Actions

Inform legal team
Involve HR
Conduct employee training
Educate on safe browsing
Update policies
Update antivirus


Involves HR + legal → non-technical IR aspect.


APPLICATION SECURITY INCIDENTS
Containment Actions

Enable rate limiting (blackhole feature)
Increase server capacity
Define user thresholds
Restrict unauthorized access
Business continuity planning
Alert users during incidents
Deploy traffic filters
Restore systems and fix vulnerabilities

Detection Sources: WAF logs · Traffic spikes · API abuse
Example: DDoS attack → rate limiting + scaling servers

Eradication — Web Application Controls
ControlPurposeInput ValidationPrevent injection attacksWAF / IDSFilter malicious trafficSecure CodingAvoid hardcoded credentials, minimize privilegesDatabase SecurityUse parameterized queriesLogging & TestingDynamic testing, code analysisSystem HardeningDisable unnecessary services, patch systemsOutput HandlingSanitize outputs

Eradicating Specific Attack Types
SQL Injection

Use parameterized queries
WAF protection
Disable dangerous DB features

Command Injection

Validate inputs
Escape characters
Use safe APIs

File Injection

Disable risky PHP settings
Validate file paths

LDAP Injection

Validate inputs
Limit query results

IoCs: ' OR 1=1 · Suspicious command execution · Unexpected DB queries

Input validation is the key defense.


Broken Authentication Controls

Use SSL/TLS · Hash passwords · Avoid session in URLs · Use MFA · Enforce password policies · Limit login attempts · Secure session IDs · Implement session timeout

IoCs: Brute-force attempts · Session hijacking

Sensitive Data Exposure Controls

Encrypt sensitive data · Avoid weak crypto · Proper key management · Use strong algorithms · Enable HSTS · Disable caching for sensitive data

IoCs: Plaintext credentials · Unencrypted traffic

Broken Access Control

Enforce access checks · Avoid predictable IDs · Session timeout · Limit permissions · Remove session tokens after logout


Security Misconfiguration

Disable unused services · Remove default accounts · Apply patches · Enforce HTTPS · Secure cookies · Validate certificates · Encrypt backend communication

IoCs: Default credentials · Open ports/services

XSS Attacks

Validate all inputs · Encode outputs · Use CSP · Filter scripts · Convert special characters

IoCs: <script> tags in input · Suspicious JavaScript execution

Insecure Deserialization

Validate serialized data · Avoid untrusted deserialization · Restrict classes · Filter serialized inputs

IoCs: Unexpected object execution · Application crashes

Insufficient Logging & Monitoring

Define logging scope · Set logging baseline · Include user context · Log for proactive detection · Prevent log injection


"If it's not logged, it's not detectable."


INSIDER THREATS
Definition
Malicious or negligent actions by trusted individuals — employees, contractors, vendors.
Objectives: Prevent further damage · Preserve evidence · Limit access and data exposure

Containment Actions

Isolate Affected Systems — Disconnect compromised endpoints
Block All Access — Disable email, application access, physical access (ID cards), VPN credentials
Seize Devices — Collect laptops, mobile devices; preserve for forensics
Inform Stakeholders — Notify impacted departments, assess business impact
Continuous Monitoring — Track suspect activity, await legal/management decision
Forensic Investigation — Analyze portable devices and account activity logs
Legal Action — File complaint as per jurisdiction
Restrict Physical Entry — Prevent suspect from entering premises
Protect Information Flow — Limit insider knowledge exposure
Organization-wide Password Reset — Prevent further compromise

IoCs: Large data transfers · Access outside working hours · Access to unauthorized systems

Insider threats require technical + HR + legal coordination.


Eradication Controls
A. Access Control

Least privilege principle
Role-based access control (RBAC)

B. Data Encryption

Encrypt data at rest, in transit, and in use
Use strong encryption (≥256-bit keys)

C. Isolate Storage

Avoid storing sensitive data on network-accessible systems

D. Password Policies

Enforce strong password rules
Regular password changes

E. Data-Centric Protection (DCAP)

Monitor user access and data movement
Detect privilege misuse


Least privilege is the strongest defense. Use UBA/UEBA for behavioral monitoring.


Human Resources Controls

Define strict employee behavior policies
Conduct employee behavior analysis
Monitor financial stress indicators
Manage workplace conflicts
Provide security awareness training
Perform background checks
Monitor third-party vendors


Insider threats are often behavioral, not just technical.


Network Security Controls

Configure firewalls
Monitor outbound traffic
Restrict file transfers
Disable unauthorized sharing tools
Scan emails for sensitive data
Enforce MFA
Implement account management policies

IoCs: Upload to cloud storage · Use of unauthorized tools

Access Controls

Grant access based on job role
Restrict software installation and log modification
Enable admin alerts for changes
Regular access audits
Strict sensitive data access policies
Supervisor approval for access
Data owner permission required
Remove access after termination


Access should be revoked immediately after exit.


Privileged User Controls

Non-repudiation logging
Disable default admin accounts
Use unique admin accounts
Encrypt sensitive backups
Monitor admin activities

IoCs: Admin activity at unusual times · Unauthorized config changes

Log Monitoring Controls

Enforce logging policies
Perform regular audits
Enable audit trails
Monitor changes to critical systems
Protect logs from tampering
Use IDS & file integrity monitoring


Logs must be centralized and immutable.


Physical Security Controls

Auto-lock systems
Secure data centers
Block portable media
Use biometric authentication
Lock storage devices
CCTV surveillance
Soundproof meeting rooms
Secure disposal (shredding)
Wipe storage devices
Enforce vendor policies


Many breaches happen via USB devices.


Recovery from Insider Attacks

Collect legal evidence
Reset passwords
Remove malware
Restore systems from backups
Implement backup strategy
Secure backup storage
Separate duties (backup roles)
Enforce backup security policies
Maintain chain-of-custody
Improve backup planning


MALWARE INCIDENTS
Containment Steps

Isolate infected host
Analyze network logs
Cut network services (if widespread)
Use VLAN isolation
Allow only safe communication (VPN)
Identify malware patterns/signatures
Disable vulnerable services

IoCs: Suspicious processes · C2 traffic · Unknown binaries

Eradication Actions

Patch vulnerabilities
Share malware intelligence
Implement application whitelisting
Block malicious websites
Prevent auto-downloads
Restrict BIOS/system access (virtualization)
Secure browser settings: Block pop-ups · Disable auto-downloads


Malware removal ≠ eradication → must fix root cause.


Recovery Steps

Wipe disks if required
Reimage systems
Restore clean backups
Scan systems with updated AV
Restore email services
Enable attachment scanning
Disable file sharing temporarily
Restore cloud data safely
Reinstall applications
Restore system configurations

IoCs post-recovery: Reinfection attempts · Residual malware artifacts

ENDPOINT DETECTION AND RESPONSE (EDR)
Definition
EDR is a security solution that monitors endpoint activities, detects threats using behavioral analysis, and investigates and responds to incidents in real time.
Core Functions

Continuous monitoring of endpoints
Detection of IoCs and behavioral anomalies
Threat investigation
Automated response actions


How EDR Works
Data Collection

Process execution logs
File activity
Registry changes
Network connections

Analysis

Behavioral analytics (not just signatures)
Detects fileless malware and living-off-the-land attacks

Response

Alert SOC team
Trigger automated actions


IR Using EDR
Key Capabilities:
CapabilityDescriptionAlert GenerationAffected endpoint, attack type, timelineData CollectionDetailed telemetry for investigationAutomated ResponseEndpoint isolation, network blocking, process termination
Example Workflow:

Alert triggered (malware detected)
Analyst reviews process tree and file hashes
Kill process → Isolate system
Remediation applied

IoCs: Suspicious processes · Unknown executables · Privilege escalation attempts

EDR = Detection + Response + Forensics. Detects behavior, not just signatures. Critical for fileless malware.


Detecting Ransomware Using EDR
Data Collected: Process execution · File changes · Registry activity · Network connections
Investigation Steps:

Memory Analysis — Capture RAM for fileless malware
Timeline Creation — Identify attack sequence
File Analysis — Detect mass file encryption, file renaming patterns
Network Analysis — Detect C2 communication, data exfiltration
Persistence Check — Registry keys, scheduled tasks

SOC IoCs:

Rapid file encryption
Unknown processes modifying files
Suspicious extensions (.locked, .encrypted)
High CPU/disk usage

Example: powershell.exe → downloads payload → encrypts files

Ransomware detection relies on behavior patterns.


Notable EDR Tools
Cybereason EDR

Detects ransomware & fileless attacks
Uses threat intelligence + behavioral analytics
Lightweight agent, centralized dashboard, automated investigation, cross-endpoint visibility

RSA NetWitness EDR

Endpoint + network visibility
Prioritized alerts
Deep investigation with attack reconstruction (timeline)


EXTENDED DETECTION AND RESPONSE (XDR)
Definition
XDR extends EDR by integrating multiple security layers — Endpoint · Network · Cloud · Email · Applications
XDR = EDR + NDR + SIEM-like correlation + AI
Why XDR is Needed

EDR limitation → only endpoint visibility
XDR solves → cross-platform visibility

XDR Features

Unified visibility
AI/ML-based detection
Automated response
Threat correlation across layers


XDR Architecture
Ingest → Detection → Response
(Email, Firewall, Network, Endpoint, Cloud) → (Alert prioritization, Correlation) → (Automated workflows, Threat hunting)
Example: Phishing email → user clicks → endpoint infected → XDR correlates email + endpoint + network logs → detects full attack chain

EDR vs XDR
FeatureEDRXDRScopeEndpoint onlyMultiple layersDetectionLocalCorrelatedVisibilityLimitedUnifiedResponseEndpoint actionsCross-system

SECURITY ORCHESTRATION, AUTOMATION, AND RESPONSE (SOAR)
Definition
SOAR integrates security tools, processes, and people to automate and orchestrate incident response workflows.
Core Purpose

Automate repetitive security tasks
Improve incident response speed
Reduce manual workload
Enhance threat visibility and coordination


Key Functions
Orchestration — Connects multiple security tools (SIEM, EDR, Firewalls, TIP)
Automation — Executes predefined actions: Block IP · Isolate endpoint · Send alerts
Response — Enables faster and consistent incident handling

SOAR Capabilities

Aggregates security data from multiple sources
Automates data collection, alert triage, initial investigation
Integrates threat intelligence feeds
Provides centralized dashboards
Generates reports for compliance and auditing


Without SOAR vs With SOAR
Without SOARWith SOARAnalyst receives alertAlert triggeredManually checks logsSOAR auto-enriches data (IP reputation)Blocks IP manuallyAuto-blocks IPSends email to teamAuto-notifies team + creates ticket

SOAR Playbook
A predefined workflow that automates incident response actions.
Playbook Components:

Playbook Version & Date
Owner/Reviewer
Metrics & Reporting
Execution Platform
Incident Documentation
Communication Plan
Resolution Steps

Types of Actions:
TypeExamplesAutomatedBlock IP, quarantine file, disable accountManualAnalyst investigation, decision-making
Example: Phishing Playbook

Extract email indicators
Check URL reputation
If malicious → Block domain → Quarantine email → Notify users
Create incident report


Playbooks = SOPs implemented in automation. Used daily in SOC operations.


Integrating SOAR with SIEM
SIEM detects → SOAR responds
Workflow:

SIEM generates alert
SOAR triggers playbook
Automated response executed
Analyst reviews outcome

Use Cases:
ScenarioSIEMSOARPhishingDetects phishing emailQuarantines email, blocks sender, notifies userMalwareDetects suspicious activityIsolates endpoint, triggers scan, updates threat intelData BreachDetects exfiltrationBlocks access, starts containment, alerts SOC

SIEM vs SOAR
FeatureSIEMSOARFunctionDetectionResponseRoleAlertingAutomationFocusLogs & correlationActions & workflows

SOAR Tools (Industry)

ServiceNow Security Incident Response
IBM QRadar SOAR
Swimlane SOAR
D3 Security
Heimdal Threat Hunting Platform
Splunk SOAR — centralized visibility, playbook creation, third-party integration, automated account monitoring
