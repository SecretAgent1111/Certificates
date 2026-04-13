CYBER THREAT INTELLIGENCE (CTI)

1. Definition
Cyber Threat Intelligence (CTI) is the collection, processing, and analysis of information about cyber threats, adversaries, and attack patterns to support informed decision-making for security operations.

2. Detailed Explanation
CTI is not just raw data — it is actionable intelligence.
Core Functions:
	1. Collection 
		○ Gathering data from multiple sources (logs, threat feeds, OSINT) 
	2. Analysis 
		○ Identifying patterns, attacker behavior, trends 
	3. Contextualization 
		○ Turning raw data into meaningful insights 
	4. Decision Support 
		○ Helps organizations: 
			§ Prevent attacks 
			§ Detect threats early 
			§ Respond effectively 

CTI Covers:
	• Cybercrime (financial attacks) 
	• Hacktivism (political motives) 
	• Espionage (APT groups, nation-state attacks) 

Key Concept: Converting Unknown → Known
CTI helps:
	• Convert unknown threats → known threats 
	• Reduce uncertainty 
	• Improve proactive defense 

Intelligence Output:
CTI is often delivered as:
	• Indicators of Compromise (IoCs) 
	• Threat reports 
	• Threat feeds 

Intelligence Analysis Triad:
CTI analysis is based on:
	1. Intent 
		○ Why attacker is targeting (financial, espionage) 
	2. Capability 
		○ Skill level, tools, malware 
	3. Opportunity 
		○ Vulnerabilities, exposure 

3. Examples
Simple Example:
	• Multiple failed login attempts from IP: 192.168.1.10 
	• CTI identifies: 
		○ IP linked to brute-force attacks
→ Action: Block IP 

Real-World Scenario:
	• SOC receives alert: suspicious PowerShell execution 
	• CTI reveals: 
		○ Known malware uses same command pattern 
	• Analyst: 
		○ Confirms threat 
		○ Escalates incident 

4. SOC Relevance
CTI is critical in SOC operations:
	• Improves alert accuracy 
	• Reduces false positives 
	• Enables proactive defense 
	• Helps analysts prioritize threats 

5. Detection Perspective
Where CTI is Used:
	• SIEM (Splunk, Sentinel) 
	• EDR (CrowdStrike, Defender) 
	• Firewalls / IDS / IPS 

Detection Logic Examples:
Example 1: IP Reputation Check

index=firewall src_ip IN (threat_intel_ip_list)
Example 2: Hash Matching

index=edr file_hash IN (known_malware_hashes)

What to Monitor:
	• Known malicious IPs/domains 
	• Suspicious process execution 
	• Abnormal network behavior 
	• Threat feed matches 

6. Indicators (IoCs / Behavior)
Network IoCs:
	• Malicious IPs 
	• Suspicious domains 
	• C2 communication 
Host IoCs:
	• Unknown processes 
	• Registry changes 
	• Suspicious file hashes 
Behavioral Indicators:
	• Lateral movement 
	• Privilege escalation 
	• Data exfiltration 

7. Investigation Approach
SOC Workflow Using CTI:
	1. Alert triggered 
	2. Check IoCs in threat intelligence feeds 
	3. Validate: 
		○ Is IP/domain malicious? 
	4. Analyze behavior: 
		○ Matches known attack pattern? 
	5. Classify: 
		○ True Positive / False Positive 
	6. Respond: 
		○ Block IP 
		○ Isolate host 
		○ Escalate 

8. Interview Points
Common Questions:
Q1: What is CTI?
CTI is the process of collecting and analyzing threat data to provide actionable intelligence for detecting and preventing cyber attacks.

Q2: Difference between Data and Intelligence?
	• Data = Raw logs 
	• Intelligence = Processed, actionable insights 

Q3: What is IoC?
Evidence of compromise such as malicious IP, hash, domain.

Q4: Explain Intent, Capability, Opportunity
	• Intent → attacker goal 
	• Capability → attacker skill/tools 
	• Opportunity → vulnerability exploited 

9. Key Takeaways
	• CTI = Actionable security intelligence 
	• Helps in proactive defense 
	• Converts unknown threats into known threats 
	• Based on Intent, Capability, Opportunity 
	• Core SOC function for detection & response 

OBJECTIVES OF THREAT INTELLIGENCE

1. Definition
Objectives define why CTI is used in organizations and SOC environments.

2. Detailed Explanation
1. Enhanced & Automated Incident Prevention
	• Block threats before execution 
	• Use threat feeds for auto-blocking 

2. Automation of Security Operations
	• SOAR integration 
	• Automated: 
		○ IP blocking 
		○ Alert triaging 

3. Guidance to Cybersecurity Activities
	• Helps SOC: 
		○ Focus on real threats 
		○ Prioritize alerts 

4. Improved Risk Management
	• Identify high-risk assets 
	• Understand threat landscape 

5. Improved Incident Detection
	• Detect attacks faster using known patterns 

3. SOC Relevance
	• Reduces manual work 
	• Speeds up detection 
	• Improves response time 

4. Interview Points
Q: Why is CTI important?
	• Improves detection, prevention, and response 
	• Helps prioritize threats 
	• Enables automation 

THREAT INTELLIGENCE LIFECYCLE

1. Definition
A structured process used to produce, analyze, and deliver threat intelligence.

2. Detailed Explanation
Phase 1: Planning & Direction
	• Define intelligence goals 
	• Identify requirements 

Phase 2: Collection
Sources:
	• OSINT (Open-source) 
	• HUMINT (Human intelligence) 
	• IMINT (Image intelligence) 
	• MASINT (Measurement intelligence) 

Phase 3: Processing & Exploitation
	• Clean and structure raw data 
	• Convert into usable format 

Phase 4: Analysis & Production
	• Combine data 
	• Generate insights: 
		○ Findings 
		○ Predictions 
	• Must be: 
		○ Accurate 
		○ Timely 
		○ Actionable 

Phase 5: Dissemination & Integration
	• Deliver intelligence to: 
		○ Strategic level 
		○ Tactical level 
		○ Operational level 
		○ Technical level 

3. SOC Relevance
	• Structured workflow for threat analysis 
	• Used in: 
		○ Threat hunting 
		○ Incident response 
		○ Alert enrichment 

4. Detection Perspective
	• Collection: Logs, SIEM data 
	• Processing: Normalization 
	• Analysis: Correlation rules 
	• Dissemination: Alerts, dashboards 

5. Interview Points
Q: Explain CTI lifecycle
Answer all 5 phases clearly (very common question)

THREAT ANALYST ROLES IN CTI

1. Detailed Breakdown
Collection Phase:
	• Threat feeds 
	• Internal logs 
	• External reports 

Processing & Exploitation:
	• Indexing data 
	• Filtering noise 
	• Structuring data 

Analysis & Production:
	• Analyze threats 
	• Define response actions 

Dissemination:
	• Deliver intelligence to: 
		○ Strategic (management) 
		○ Tactical (SOC leads) 
		○ Operational (incident responders) 
		○ Technical (SOC analysts) 

2. SOC Relevance
	• Defines responsibilities of SOC analyst 
	• Helps understand workflow 

3. Interview Points
Q: What does a Threat Analyst do?
	• Collect, analyze, and provide actionable intelligence 
	• Support SOC detection and response 

COMMON CTI CHALLENGES

1. Information Overload
	• Too much data → hard to analyze
SOC Impact: Alert fatigue 

2. Contextual Interpretation
	• Hard to understand relevance
SOC Impact: Misclassification of alerts 

3. Malware vs CTI Confusion
	• CTI is broader than malware
SOC Insight: Focus on attacker behavior, not just malware 

4. IoC vs CTI Confusion
	• IoC = evidence 
	• CTI = full intelligence
SOC Mistake: Relying only on IoCs 

5. Budget & Skills
	• Paid feeds required 
	• Skilled analysts needed 

6. Filtering CTI Data
	• Not all intelligence is useful
SOC Task: Validate and filter 

2. SOC Detection Perspective
	• Avoid blind IoC matching 
	• Focus on: 
		○ Behavior 
		○ Context 
		○ Patterns 

3. Investigation Insight
Bad Approach:
	• “IP is malicious → block immediately” 
Good Approach:
	• Validate: 
		○ Is it relevant to your environment? 
		○ Is it active threat? 

4. Interview Points
Q: Challenges in CTI?
	• Data overload 
	• Lack of context 
	• False positives 
	• Skill gap 

5. Key Takeaways
	• CTI is powerful but complex 
	• Requires filtering and validation 
	• Context is everything in SOC 

FINAL REVISION SUMMARY (VERY IMPORTANT)
	• CTI = Actionable intelligence, not raw data 
	• Based on: 
		○ Intent 
		○ Capability 
		○ Opportunity 
	• Lifecycle = 5 phases 
	• IoCs ≠ CTI 
	• SOC uses CTI for: 
		○ Detection 
		○ Enrichment 
		○ Response 
	• Biggest mistake: Blindly trusting threat feeds

THREAT INTELLIGENCE USE CASES FOR INCIDENT RESPONSE

1. Definition
Threat Intelligence (CTI) in Incident Response (IR) refers to the integration of threat data and insights into the incident handling process to improve detection, analysis, and response speed.

2. Detailed Explanation
CTI enhances IR by answering:
	• Who is attacking? 
	• How are they attacking? 
	• What campaign or group is involved? 
	• Where else should we look in the network? 
It transforms IR from reactive → intelligence-driven response.

3. Phases of Escalation in Incident Response

Phase 1: Pre-Planning
CTI helps answer:
	• Which threat groups (APT, hackers) target the organization? 
	• What assets are targeted? 
	• What are attacker capabilities? 
	• What are possible attack scenarios? 

SOC Relevance:
	• Used in threat modeling 
	• Helps create detection rules before attack happens 

Phase 2: Event
	• CTI provides context to alerts generated by SIEM/SOC tools 
	• Helps determine: 
		○ Is this alert serious? 
		○ Should it escalate? 

SOC Example:
	• SIEM alert: outbound connection to suspicious IP 
	• CTI check: 
		○ IP = known C2 server
→ Escalate incident 

Phase 3: Incident
	• After compromise, CTI helps: 
		○ Understand attacker techniques (TTPs) 
		○ Identify attacker objectives 
		○ Correlate with past incidents 

Key Concept:
Use Threat Triangle (Intent, Capability, Opportunity)

Phase 4: Breach
	• If incident escalates to breach: 
		○ CTI helps answer: 
			§ What happened? 
			§ Why it happened? 
			§ How to prevent in future? 

4. SOC Relevance
	• Improves: 
		○ Alert triage 
		○ Root cause analysis 
		○ Faster response 
	• Enables intelligence-driven SOC 

5. Detection Perspective
Data Sources:
	• SIEM alerts 
	• Threat feeds 
	• EDR telemetry 
	• Firewall logs 

Detection Logic:
	• Correlate: 
		○ Alerts + IoCs + behavior 
	• Prioritize: 
		○ Known attacker infrastructure 

6. Indicators
	• IPs linked to campaigns 
	• Malware hashes 
	• Domains used in phishing 
	• Behavioral patterns (lateral movement) 

7. Investigation Approach
	1. Validate alert 
	2. Enrich with CTI 
	3. Identify attacker pattern 
	4. Check lateral movement 
	5. Decide escalation 

8. Interview Points
Q: How does CTI improve Incident Response?
	• Provides context 
	• Identifies attackers 
	• Speeds up detection and response 

9. Key Takeaways
	• CTI makes IR faster and smarter 
	• Helps move from alert-based → intelligence-based SOC 

ENHANCING INCIDENT RESPONSE USING SOPs (STANDARD OPERATING PROCEDURES)

1. Definition
SOPs are standardized procedures used by SOC analysts to handle specific types of alerts and incidents consistently.

2. Detailed Explanation
CTI provides indicators (IoCs) like:
	• IP addresses 
	• URLs 
	• Domains 
	• File hashes 
SOPs define:
	• How to investigate each indicator 
	• What tools to use 
	• What decisions to take 

3. SOP Design Questions

IP Addresses:
	• Is the IP critical? 
	• Is traffic coming from/to critical assets? 
	• Do we have enrichment tools (VirusTotal, etc.)? 

URLs:
	• Is URL suspicious? 
	• Did user interact with it? 

Domain Names:
	• WHOIS lookup? 
	• DNS activity? 

Malware Hashes:
	• Present on endpoints? 
	• Detected by AV? 

4. SOC Relevance
	• Ensures consistent investigation 
	• Reduces analyst confusion 
	• Improves response speed 

5. Detection Perspective
	• Use CTI feeds to: 
		○ Auto-enrich alerts 
		○ Trigger playbooks (SOAR) 

6. Investigation Approach
Example SOP for malicious IP:
	1. Check reputation 
	2. Check internal communication 
	3. Identify affected host 
	4. Contain system 
	5. Escalate 

7. Interview Points
Q: What are SOPs in SOC?
	• Predefined steps to handle alerts consistently 

8. Key Takeaways
	• SOPs + CTI = efficient SOC operations 
	• Reduces human error 

THREAT HUNTING BASED ON OSI MODEL

1. Definition
Threat hunting using OSI model involves analyzing each network layer systematically to detect hidden threats.

2. Detailed Explanation (Layer-wise Hunting)

1. Application Layer
	• Detect: 
		○ Web attacks 
		○ Malicious payloads 

2. Presentation Layer
	• Detect: 
		○ Encoding/obfuscation attacks 

3. Session Layer
	• Detect: 
		○ Unauthorized session activity 

4. Transport Layer
	• Detect: 
		○ Port scanning 
		○ Reconnaissance 

5. Network Layer
	• Detect: 
		○ IP spoofing 
		○ MITM attacks 

6. Data Link Layer
	• Detect: 
		○ ARP spoofing 
		○ MAC anomalies 

7. Physical Layer
	• Detect: 
		○ Packet sniffing 
		○ Physical interception 

3. SOC Relevance
	• Helps analysts: 
		○ Break down attacks layer by layer 
		○ Perform structured hunting 

4. Detection Perspective
Layer	Logs
Application	Web logs
Transport	Netflow
Network	Firewall logs
Data Link	ARP logs

5. Interview Points
Q: How do you use OSI in threat hunting?
	• Analyze activity layer by layer to identify anomalies 

6. Key Takeaways
	• OSI model = structured hunting approach 
	• Helps detect hidden attacks 

THREAT HUNTING vs THREAT INTELLIGENCE vs INCIDENT RESPONSE

1. Definitions
Threat Hunting
	• Proactively searching threats 
Threat Intelligence
	• Data-driven insights about threats 
Incident Response
	• Responding to detected incidents 

2. Detailed Comparison
Aspect	Threat Hunting	Threat Intelligence	Incident Response
Approach	Proactive	Analytical	Reactive
Focus	Unknown threats	Known threats	Active incidents
Goal	Find hidden attacks	Understand threats	Contain & fix
Skill	Deep technical	Analytical	Operational

3. SOC Relevance
	• All three work together: 
		○ CTI → provides data 
		○ Hunting → finds threats 
		○ IR → responds 

4. Interview Points
Q: Difference between hunting and IR?
	• Hunting = proactive 
	• IR = reactive 

5. Key Takeaways
	• CTI feeds both hunting and IR 
	• Hunting reduces dwell time 

THREAT HUNTING USING THE CYBER KILL CHAIN

1. Definition
The Cyber Kill Chain is a framework that describes stages of a cyber attack from start to finish.

2. Kill Chain Stages
	1. Reconnaissance 
	2. Weaponization 
	3. Delivery 
	4. Exploitation 
	5. Installation 
	6. Command & Control (C2) 
	7. Actions on Objectives 

3. Detailed Explanation
Reconnaissance
	• Attacker gathers information 
	• Example: scanning 

Weaponization
	• Malware creation 

Delivery
	• Phishing email, exploit kits 

Exploitation
	• Vulnerability exploited 

Installation
	• Malware installed 

Command & Control
	• Attacker communicates with system 

Actions on Objectives
	• Data theft, ransomware 

4. SOC Relevance
	• Helps detect attacks at early stages 
	• Reduces damage 

5. Detection Perspective
Stage	Detection
Recon	Port scan logs
Delivery	Email logs
Exploit	EDR alerts
C2	Outbound traffic

6. Investigation Approach
	• Map alert to kill chain stage 
	• Identify: 
		○ How far attacker progressed 
	• Take action accordingly 

7. Interview Points
Q: What is Kill Chain?
	• A model describing stages of cyber attack used to detect and stop attacks 

8. Key Takeaways
	• Earlier detection = less damage 
	• SOC should aim to stop attacks in early stages 

FINAL MASTER SUMMARY (IMPORTANT)

Core Understanding:
	• CTI enhances Incident Response 
	• SOPs standardize SOC workflows 
	• OSI model helps in structured threat hunting 
	• Kill Chain helps track attack progression 
	• Threat Hunting = proactive 
	• Incident Response = reactive 

Real SOC Insight:
A strong SOC analyst:
	• Uses CTI for context 
	• Uses SOPs for consistency 
	• Uses OSI + Kill Chain for investigation 
	• Thinks in attacker mindset 
IMPORTANT WINDOWS EVENT IDs FOR THREAT HUNTING

1. Definition
Windows Event IDs are specific log identifiers in Windows Security Logs that indicate particular system activities. These are heavily used in threat hunting and detection.

2. Detailed Explanation

Event ID 4771 – Failed Kerberos Pre-Authentication
Explanation:
	• Occurs when Kerberos authentication fails before ticket generation 
Threat Insight:
	• Indicates: 
		○ Password spraying 
		○ Brute-force attempts 

Event ID 4625 – Failed Logins
Explanation:
	• Failed login attempts 
Threat Insight:
	• High volume = brute force attack 
	• Outside business hours = suspicious 

Event ID 4794 – DSRM Password Change
Explanation:
	• Change in Directory Services Restore Mode password 
Threat Insight:
	• Rare event → HIGHLY suspicious 
	• Could indicate attacker persistence 

Event ID 4698 & 4702 – Scheduled Task Creation/Modification
Explanation:
	• Creation/modification of scheduled tasks 
Threat Insight:
	• Used for: 
		○ Persistence 
		○ Malware execution 

Event ID 4672 – Special Privileges Assigned
Explanation:
	• Admin-level privileges assigned during login 
Threat Insight:
	• Detect privilege escalation 

3. SOC Relevance
	• Core logs in: 
		○ Splunk 
		○ Sentinel 
		○ QRadar 
	• Used daily for: 
		○ Brute force detection 
		○ Privilege abuse 
		○ Persistence detection 

4. Detection Perspective
Splunk Example:

index=wineventlog EventCode=4625 | stats count by user, src_ip

What to Monitor:
	• Repeated failed logins 
	• Privileged logins 
	• Scheduled task creation 

5. Indicators (IoCs)
	• Multiple failed logins from same IP 
	• Privilege escalation events 
	• Suspicious scheduled tasks 

6. Investigation Approach
	1. Check frequency of events 
	2. Identify source IP 
	3. Validate user account 
	4. Check related logs (4624, 4672) 
	5. Confirm attack pattern 

7. Interview Points
Q: Most important Windows Event IDs?
	• 4625 (failed login) 
	• 4624 (successful login) 
	• 4672 (admin privileges) 
	• 4698 (scheduled task) 

8. Key Takeaways
	• Event IDs = foundation of Windows threat hunting 
	• Always correlate multiple events 

IMPORTANT WINDOWS PROCESSES FOR THREAT HUNTING

1. Definition
Critical Windows processes must behave normally. Any deviation may indicate malware or attacker activity.

2. Key Processes & Threat Insights

Svchost.exe
	• Hosts Windows services 
	• Suspicious if: 
		○ Wrong path 
		○ High CPU/network usage 

Services.exe
	• Manages services 
	• Monitor: 
		○ Event ID 4697 (service install) 

Lsass.exe
	• Handles authentication 
	• Target for credential dumping 
Red Flag:
	• Tools like Mimikatz 

Wininit.exe
	• Starts system processes 

Winlogon.exe
	• Handles login sessions 
Red Flag:
	• Shell changes (registry) 

Smss.exe
	• Session manager 

System.exe
	• Kernel process 

3. SOC Relevance
	• Used in: 
		○ EDR alerts 
		○ Process monitoring 
	• Detect: 
		○ Malware injection 
		○ Credential dumping 

4. Detection Perspective
What to Monitor:
	• Parent-child process relationships 
	• Process path anomalies 
	• Misspelled processes (lsass.exe vs lsas.exe) 

5. Indicators
	• Process running from temp folder 
	• Abnormal parent process 
	• Suspicious command-line arguments 

6. Interview Points
Q: Why is lsass.exe important?
	• Stores credentials → target for attackers 

7. Key Takeaways
	• Process monitoring = critical for SOC 
	• Parent-child analysis is key 

THREAT HUNTING WITH POWERSHELL

1. Definition
Using PowerShell scripts to analyze logs, detect anomalies, and identify IoCs.

2. Capabilities
	• Log analysis 
	• Network monitoring 
	• Process monitoring 
	• Automation 

3. SOC Relevance
	• Widely used in: 
		○ Windows environments 
		○ Automation scripts 
	• Can: 
		○ Reduce manual work 
		○ Speed up investigations 

4. Detection Perspective
	• Monitor: 
		○ PowerShell execution logs 
		○ Script block logging 

5. Indicators
	• Encoded commands 
	• Suspicious scripts 
	• Execution from unusual directories 

6. Key Takeaways
	• PowerShell = powerful but abused tool 

POWERSHELL: CREDENTIAL DUMPING HUNTING

1. Definition
Credential dumping = extracting passwords/hashes from system memory.

2. Detection Techniques

Check for Suspicious Processes
	• Example: 
		○ mimikatz.exe 

PowerShell Logging
	• Enable: 
		○ Script block logging 

Network Connections
	• Outbound suspicious connections 

SAM File Access
	• Monitor attempts to access SAM 

3. SOC Relevance
	• Critical attack technique 
	• Used in: 
		○ Lateral movement 
		○ Privilege escalation 

4. Investigation Steps
	1. Check PowerShell logs 
	2. Identify suspicious commands 
	3. Check LSASS access 
	4. Verify outbound traffic 

5. Indicators
	• Access to LSASS 
	• Dumping tools 
	• Suspicious PowerShell commands 

POWERSHELL: FIREWALL LOG ANOMALY HUNTING

1. Definition
Analyzing firewall logs to detect abnormal traffic patterns.

2. Detection Use Cases

High Traffic from Single IP
	• Possible: 
		○ DDoS 
		○ Scanning 

Uncommon Ports
	• Indicates: 
		○ Backdoor communication 

Traffic Spikes
	• Sudden increase in traffic 

Blocked Traffic Trends
	• Identify malicious IPs 

3. SOC Checklist
	• Host scanning 
	• ICMP anomalies 
	• DNS anomalies 
	• TOR traffic 
	• Policy violations 

4. Key Takeaways
	• Baseline normal traffic first 
	• Then detect anomalies 

POWERSHELL: DIFFERENTIAL ANALYSIS

1. Definition
Comparing baseline vs current system state to detect anomalies.

2. What to Compare
	• Services 
	• Scheduled tasks 
	• Ports 
	• Users 

3. SOC Relevance
	• Detect: 
		○ Persistence 
		○ Unauthorized changes 

4. Key Takeaways
	• Baseline = VERY IMPORTANT 

POWERSHELL + AI IN THREAT HUNTING

1. Definition
Using AI modules in PowerShell for:
	• NLP 
	• Analysis 
	• Automation 

2. SOC Use Cases
	• Automated alert response 
	• Threat classification 
	• Recommendation generation 

3. Key Takeaways
	• Future SOC = AI-driven 

THREAT HUNTING WITH YARA

1. Definition
YARA is a tool used to detect malware using rule-based signatures.

2. YARA Rule Structure

Components:
	1. Meta 
		○ Description, author 
	2. Strings 
		○ Patterns to match 
	3. Condition 
		○ Logic for detection 

3. Types of Detection
	• File-based 
	• Hash-based 
	• String-based 
	• Network-based 

4. SOC Relevance
	• Used in: 
		○ Malware analysis 
		○ Threat hunting 

5. Indicators
	• Known malware patterns 
	• Suspicious strings 

6. Interview Points
Q: What is YARA?
	• Tool for identifying malware using rules 

THREAT HUNTING WITH SYSMON

1. Definition
Sysmon is a Windows tool that provides detailed system activity logs.

2. Key Events

Event ID 1 – Process Creation
	• Detect suspicious processes 

Event ID 3 – Network Connections
	• Detect malicious IP communication 

Event ID 13 – Registry Changes
	• Detect persistence 

Event ID 11 – File Creation
	• Detect suspicious files 

3. Detection Examples
	• Suspicious parent process 
	• Malicious IP connection 
	• Registry persistence 

4. SOC Relevance
	• Highly used in: 
		○ Threat hunting 
		○ EDR 

5. Key Takeaways
	• Sysmon = advanced visibility 

LINUX: NEW USER ACCOUNT HUNTING

1. Definition
Detect unauthorized user creation in Linux systems.

2. Detection Methods
	• Check logs: 
		○ /var/log/auth.log 
		○ /var/log/secure 
	• Commands: 

grep useradd /var/log/auth.log

3. Indicators
	• New user creation 
	• Sudo privileges 

4. SOC Relevance
	• Detect persistence 

WEB SHELL HUNTING

1. Definition
Web shell = malicious script that gives attacker remote control.

2. Detection

Suspicious Functions:
	• exec() 
	• system() 
	• shell_exec() 

File Names:
	• cmd.php 
	• shell.php 

Tools:
	• LMD 
	• NeoPI 

3. SOC Relevance
	• Common in web attacks 

4. Indicators
	• Unusual files 
	• Obfuscated code 

IIS MALICIOUS MODULE HUNTING

1. Definition
Malicious IIS modules allow attackers to persist in web servers.

2. Detection
	• Check: 
		○ w3wp.exe process 
	• Look for: 
		○ abnormal DLLs 

3. SOC Relevance
	• Advanced persistence technique 

4. Indicators
	• Unknown modules 
	• Suspicious child processes 

FINAL MASTER SUMMARY (VERY IMPORTANT)

High-Impact SOC Skills from This Topic:
	• Windows Event Log Analysis 
	• Process Monitoring 
	• PowerShell Hunting 
	• Sysmon Analysis 
	• YARA Rules 
	• Linux Log Analysis 
	• Web Shell Detection 

Real SOC Insight
A strong SOC analyst:
	• Knows key Event IDs 
	• Understands processes deeply 
	• Uses PowerShell for automation 
	• Detects behavior, not just IoCs 
THREAT HUNTING WITH SPLUNK QUERIES

1. Definition
Threat hunting with Splunk involves using SPL (Search Processing Language) to analyze logs and identify:
	• Indicators of Compromise (IoCs) 
	• Suspicious behavior 
	• Anomalies 

2. Detailed Explanation
Splunk allows analysts to:
	• Search large datasets quickly 
	• Correlate events 
	• Detect hidden threats 

Key Use Cases from Slide:

1. Detect Obfuscated PowerShell

index=windows_logs EventCode=4104 
| search ScriptBlockText="Invoke-Expression" OR ScriptBlockText="FromBase64String"
Explanation:
	• Detects encoded or obfuscated scripts 

2. High Frequency PowerShell Usage

index=windows_logs EventCode=4104 
| stats count by user, host 
| sort -count
Explanation:
	• Detects automation or malicious scripting 

3. Suspicious Cmdlets

ScriptBlockText="Invoke-Mimikatz" OR ScriptBlockText="DownloadString"
Explanation:
	• Detects credential dumping or downloads 

4. Encoded Commands

CommandLine="*EncodedCommand*"

5. Bitsadmin Usage

NewProcessName="bitsadmin.exe"
Explanation:
	• Used to download malware 

3. SOC Relevance
	• Daily tool for: 
		○ Detection 
		○ Threat hunting 
		○ Investigation 

4. Detection Perspective
Monitor:
	• PowerShell logs (Event ID 4104) 
	• Process creation 
	• Command-line arguments 

5. Indicators
	• Encoded scripts 
	• Mimikatz usage 
	• Abnormal script frequency 

6. Interview Points
Q: How do you detect malicious PowerShell in Splunk?
	• Search EventCode 4104 
	• Look for encoded/obfuscated commands 

7. Key Takeaways
	• Splunk = core SOC tool 
	• Focus on behavior, not just IoCs 

THREAT HUNTING WITH DNS LOGS

1. Definition
Analyzing DNS logs to detect:
	• Malicious domains 
	• Data exfiltration 
	• Command & Control (C2) 

2. Detailed Explanation

1. Detect DGA (Domain Generation Algorithm)
	• Many random-looking domains 

2. Suspicious TLDs
	• .xyz, .tk, .biz 

3. NXDOMAIN Activity
	• Many failed DNS queries 

4. Long / Random Domains
	• High entropy domains 

5. Newly Registered Domains
	• Used in phishing/malware 

6. Low TTL
	• Indicates fast-changing infrastructure 

7. Unusual DNS Traffic
	• DNS tunneling 
	• Zone transfers 

3. SOC Relevance
	• DNS = goldmine for detection 
	• Detect: 
		○ Malware 
		○ Data exfiltration 
		○ C2 communication 

4. Detection Perspective
Logs:
	• DNS server logs 
	• Firewall DNS logs 

Detection Logic:
	• High NXDOMAIN rate 
	• Repeated domain queries 

5. Indicators
	• Random domains 
	• Frequent DNS queries 
	• Low TTL domains 

6. Interview Points
Q: How to detect DGA domains?
	• Look for random names + high NXDOMAIN 

7. Key Takeaways
	• DNS logs = critical for SOC 
	• Always analyze patterns 

AUTOMATE THREAT HUNTING USING SOAR

1. Definition
SOAR (Security Orchestration, Automation, and Response) automates:
	• Incident response 
	• Threat hunting 
	• Playbooks 

2. Detailed Explanation

Automated Playbook Flow:
	1. Ingest IoCs 
	2. Extract IoCs 
	3. Hunt across tools 
	4. Update databases 
	5. Close playbook 

3. SOC Relevance
	• Reduces manual workload 
	• Improves response time 

4. Detection Perspective
	• Integrates with: 
		○ SIEM 
		○ EDR 
		○ Threat intelligence feeds 

5. Indicators
	• Repeated alerts 
	• Known IoCs 

6. Interview Points
Q: What is SOAR?
	• Tool to automate SOC workflows 

7. Key Takeaways
	• SOAR = automation backbone of SOC 

THREAT HUNTING WITH EDR / XDR

1. Definition
	• EDR (Endpoint Detection & Response): Monitors endpoints 
	• XDR (Extended Detection & Response): Combines multiple sources 

2. Detailed Explanation
	• Detect: 
		○ Process activity 
		○ Network connections 
		○ Behavioral anomalies 

3. SOC Relevance
	• Real-time detection 
	• Endpoint visibility 

4. Detection Perspective
	• Monitor: 
		○ Process creation 
		○ File changes 
		○ Network connections 

5. Indicators
	• Suspicious processes 
	• Unauthorized connections 

6. Interview Points
Q: Difference between EDR and XDR?
	• EDR = endpoint only 
	• XDR = multi-layer detection 

7. Key Takeaways
	• EDR/XDR = core detection tools 

TOOLS USED FOR THREAT HUNTING

1. Categories & Explanation

1. Endpoint Detection & Response (EDR)
	• Detect endpoint threats 

2. UEBA (User and Entity Behavior Analytics)
	• Detect anomalies in user behavior 

3. Network Traffic Analysis (NTA)
	• Detect abnormal traffic 

4. NDR / NBA
	• Behavioral analysis of network 

5. Threat Intelligence Platforms (TIP)
	• Provide IoCs 

6. SIEM
	• Log collection and analysis 

2. SOC Relevance
	• Each tool plays role in: 
		○ Detection 
		○ Analysis 
		○ Response 

3. Key Takeaways
	• No single tool is enough 

THREAT HUNTING PLATFORMS

1. Popular Platforms
	• CrowdStrike Falcon 
	• VMware Carbon Black 
	• Trend Micro XDR 
	• Exabeam 
	• Mantix 
	• Cynet 360 
	• YARA 
	• Maltego 

2. SOC Relevance
	• Widely used in real jobs 

3. Interview Tip
Mention:
	• 2–3 tools + use cases 

THREAT HUNTING BEST PRACTICES

1. Key Practices

1. Understand Environment
	• Know assets, users, traffic 

2. Full Visibility
	• Logs + endpoints + network 

3. Stay Updated
	• Latest threats 

4. Use Automation
	• SOAR, scripts 

5. Use UEBA
	• Detect anomalies 

6. Perform Scans
	• Internal + external 

7. Dark Web Monitoring
	• Threat intel gathering 

8. Ethical Hacking
	• Find weaknesses 

9. Follow OODA Loop

2. OODA Loop Explained
	• Observe → Detect 
	• Orient → Analyze 
	• Decide → Plan 
	• Act → Respond 

3. SOC Relevance
	• Makes hunting structured 
	• Improves efficiency 

4. Interview Points
Q: Best practices in threat hunting?
	• Visibility 
	• Automation 
	• Continuous monitoring 

5. Key Takeaways
	• Threat hunting is continuous 
	• Requires: 
		○ Skill 
		○ Tools 
		○ Intelligence

