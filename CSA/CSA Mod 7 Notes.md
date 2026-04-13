1. FORENSIC INVESTIGATION
Definition
Forensic Investigation is the process of identifying, collecting, preserving, analyzing, and presenting digital evidence from systems affected by cyber incidents in a legally admissible manner.
Explanation
	• Uses structured methodologies + tools 
	• Ensures: 
		○ Evidence integrity 
		○ Chain of custody 
		○ Legal admissibility 
	• Conducted parallel to incident response (IR) 
Key Objectives
	1. Track and prosecute attackers 
	2. Gather admissible evidence 
	3. Determine impact on victims 
	4. Reduce measurable & non-measurable losses 
	5. Prevent future incidents 
Example
	• After a ransomware attack: 
		○ Collect logs (EDR, SIEM, firewall) 
		○ Identify attacker entry point 
		○ Preserve disk images 
		○ Present evidence for legal action 
SOC Relevance
	• SOC = first responder 
	• Forensics = deep investigation 
	• Helps validate: 
		○ True Positive vs False Positive 
		○ Root cause 
Interview Points
	• Difference: Incident Response vs Forensics 
	• What is Chain of Custody? 
	• Why evidence integrity matters? 

2. ROLE OF FORENSICS IN SOC OPERATIONS
2.1 Incident Investigation & Analysis
Explanation
	• Deep analysis of incidents using forensic tools 
	• Identifies: 
		○ Attack vector 
		○ Root cause 
		○ Impact scope 
Example
	• Multiple failed logins → brute force detection 
SOC Detection Perspective
	• Logs: 
		○ auth.log 
		○ Windows Event ID 4625 
	• SIEM Query:

index=auth_logs "Failed password"
IoCs
	• Multiple login failures 
	• Unusual login times 
	• Foreign IP addresses 

2.2 Evidence Preservation
Explanation
	• Maintain: 
		○ Integrity 
		○ Admissibility 
	• Use: 
		○ Hashing (MD5/SHA256) 
		○ Write blockers 
Key Concept: Chain of Custody
	• Tracks: 
		○ Who collected evidence 
		○ When 
		○ Where stored 
SOC Relevance
	• Prevents evidence tampering 
	• Required for compliance & legal cases 

2.3 Enhanced Threat Detection & Response
Explanation
	• Forensics reveals: 
		○ Advanced attack techniques 
		○ Hidden persistence mechanisms 
Example
	• Malware using scheduled tasks 
SOC Value
	• Improves: 
		○ Detection rules 
		○ Playbooks 

2.4 Post-Incident Recovery
Explanation
	• Recover: 
		○ Data 
		○ Systems 
Example
	• Restore from backup after ransomware 
Lessons Learned
	• Update detection rules 
	• Improve defenses 

2.5 Compliance & Legal
Explanation
	• Required for: 
		○ GDPR 
		○ ISO 27001 
		○ HIPAA 
SOC Role
	• Provide logs + evidence for audits 

2.6 Training & Awareness
Explanation
	• Forensics → insights → training 
Example
	• New phishing pattern → SOC training update 

3. ROLE OF SOC ANALYST IN FORENSICS
Responsibilities
1. Initial Detection & Analysis
	• Monitor alerts 
	• Confirm incident 
2. Data Collection
	• Logs: 
		○ SIEM 
		○ Firewall 
		○ EDR 
	• Maintain chain of custody 
3. In-Depth Analysis
	• Identify: 
		○ Techniques 
		○ Scope 
4. Collaboration
	• Work with: 
		○ IR team 
		○ Threat intel 
		○ Law enforcement 
5. Mitigation & Recovery
	• Contain threat 
	• Recommend fixes 
6. Documentation
	• Maintain reports 
	• Support legal cases 

SOC Investigation Flow (Real World)
	1. Alert triggered 
	2. Validate (TP/FP) 
	3. Collect logs 
	4. Correlate events 
	5. Identify attacker behavior 
	6. Contain threat 
	7. Document findings 

4. FORENSIC INVESTIGATION METHODOLOGY
Steps
	1. Obtain Search Warrant 
	2. Evaluate & Secure Scene 
	3. Collect Evidence 
	4. Secure Evidence 
	5. Acquire Data 
	6. Analyze Data 
	7. Assess Evidence 
	8. Prepare Report 
	9. Testify (if required) 

SOC Mapping
Forensic Step	SOC Equivalent
Collect Evidence	Log collection
Analyze Data	SIEM correlation
Report	Incident report

5. FORENSIC INVESTIGATION PROCESS
Key Steps
	1. Collect Evidence 
	2. Create Chain of Custody 
	3. Analyze Evidence 
	4. Create Report 
	5. Escalate if needed 
Decision Points
	• Internal investigation vs law enforcement 
	• Third-party involvement 

6. INVESTIGATING NETWORK SECURITY INCIDENTS
Explanation
	• Analyze: 
		○ Network traffic 
		○ Logs from: 
			§ Routers 
			§ Firewalls 
			§ IDS/IPS 
			§ DNS 
Key Activities
	• Detect deviations: 
		○ Unusual traffic patterns 
		○ Unknown protocols 
	• Build attack timeline 
SOC Detection
Logs
	• NetFlow 
	• Firewall logs 
	• DNS logs 
IoCs
	• High traffic spikes → DDoS 
	• Suspicious DNS queries 
	• Lateral movement 

7. DDoS INVESTIGATION
Tools
	• tcpdump 
	• Wireshark 
	• Dshell 
Key Actions
	• Analyze PCAP files 
	• Identify: 
		○ Source IPs 
		○ Traffic patterns 
Example Commands

dshell> decode -r dns.pcap
dshell> followstream file.pcap
SOC Detection
Indicators
	• High requests/sec 
	• Same IP flooding 
	• SYN floods 

8. SESSION RECONSTRUCTION
Tool
	• NetworkMiner 
Purpose
	• Rebuild: 
		○ Sessions 
		○ File transfers 
SOC Value
	• Understand attacker communication 

9. APPLICATION SECURITY INCIDENTS
Investigation Areas
	1. Logs (web, APM) 
	2. Code review 
	3. Network traffic 
	4. Malware analysis 

10. SQL INJECTION (SQLi)
Definition
Injection of malicious SQL queries into application input.
Indicators
	• ' OR 1=1-- 
	• UNION SELECT 
	• Unexpected DB queries 
Logs to Check
	• Web server logs 
	• DB logs 
	• WAF logs 
SOC Detection
Example Log Pattern

SELECT * FROM users WHERE id='1' OR '1'='1'

11. XSS (Cross-Site Scripting)
Definition
Injection of malicious scripts into web pages.
Indicators
	• <script> tags 
	• Encoded payloads: 
		○ %3C → < 
		○ %3E → > 
SOC Detection
	• URL parameters with script tags 

12. COOKIE / SESSION POISONING
Definition
Manipulation of session tokens.
Indicators
	• Modified cookies 
	• Missing security flags: 
		○ HttpOnly 
		○ Secure 

13. CSRF (Cross-Site Request Forgery)
Definition
Unauthorized actions via authenticated user.
Indicators
	• Missing CSRF tokens 
	• Suspicious POST requests 

14. CAPTCHA BYPASS
Indicators
	• Same IP repeated attempts 
	• Automated requests 
	• Unusual user-agent 

15. DIRECTORY TRAVERSAL
Definition
Accessing restricted directories.
Indicators
	• ../ 
	• %2e%2e%2f 
Example

/etc/passwd access attempt

16. FORENSIC TOOL – MANAGEENGINE EVENTLOG ANALYZER
Features
	• Log correlation 
	• Threat detection 
	• SQL injection detection 
	• Real-time alerts 

17. EMAIL SECURITY INCIDENTS
Investigation Areas
1. Email Logs
	• SMTP logs 
2. Email Headers
	• Trace origin 
3. Content Analysis
	• Links 
	• Attachments 
4. Phishing Detection
	• Suspicious URLs 

Email Authentication Tools
	• Email Dossier 
	• Email Address Verifier 
	• MXToolbox 

Email Investigation Example
Steps
	1. Extract sender IP 
	2. Perform IP lookup 
	3. Identify: 
		○ Location 
		○ Organization 

SOC Detection
Indicators
	• Spoofed domains 
	• Suspicious links 
	• Attachments (.exe, .zip)   

18. INVESTIGATING INSIDER INCIDENTS
Definition
An insider incident involves a legitimate user (employee, contractor, partner) misusing authorized access to compromise systems, data, or operations.

Explanation
Insider threats are dangerous because:
	• They bypass perimeter defenses 
	• Already have valid credentials 
	• Often operate slow and stealthy 
Types:
	• Malicious insider (intentional) 
	• Negligent insider (accidental) 
	• Compromised insider (account takeover) 

Investigation Areas
1. User Activity Monitoring (UEBA)
Explanation
	• Detect deviations from normal behavior 
	• Uses baseline + anomaly detection 
Examples
	• User accessing files at 3 AM 
	• Sudden spike in data downloads 
SOC Detection
	• Tools: UEBA, SIEM 
	• Logs: 
		○ Login logs 
		○ File access logs 
IoCs
	• Unusual login times 
	• Access to sensitive data not part of role 

2. Access Control Analysis
Explanation
	• Analyze IAM logs 
	• Track: 
		○ Privilege escalation 
		○ Unauthorized access 
Example
	• Normal user accessing admin panel 
Logs
	• Active Directory logs 
	• IAM logs (AWS/Azure) 

3. Data Exfiltration Analysis
Explanation
	• Identify large data transfers 
Example
	• Upload to Dropbox/Google Drive 
SOC Detection
	• DLP tools 
	• Proxy logs 
IoCs
	• Large outbound traffic 
	• Use of unauthorized cloud apps 

4. Communication Analysis
Explanation
	• Monitor: 
		○ Emails 
		○ Messaging apps 
Purpose
	• Detect collusion 
	• Detect data leaks 

SOC Investigation Workflow
	1. Alert from UEBA/DLP 
	2. Validate anomaly 
	3. Check user activity logs 
	4. Correlate access + data movement 
	5. Identify intent 
	6. Escalate 

Interview Questions
	• What is insider threat? 
	• How does UEBA detect anomalies? 
	• How to detect data exfiltration? 

19. BRUTE FORCE INVESTIGATION (JUMPLISTS)
Definition
Brute force = repeated login attempts to guess credentials.

Key Tool: JumpListsView
Explanation
	• Windows artifact 
	• Tracks recently accessed files 
Use in Forensics
	• Identify: 
		○ Files accessed post-login 
		○ Attacker activity timeline 

SOC Relevance
	• Helps confirm: 
		○ Successful compromise after brute force 

IoCs
	• Multiple failed logins 
	• Sudden successful login 
	• New file access activity 

20. CREDENTIAL THEFT INVESTIGATION
20.1 Metadata Analysis
Definition
Metadata = data about data (timestamps, ownership, etc.)
Types
	• File metadata 
	• Document metadata 
	• Network metadata 
	• Email metadata 

Investigation
What to look for:
	• File creation/modification times 
	• Access history 
	• Hidden data 
Example
	• File modified at unusual time → insider activity 

SOC Detection
	• Logs: 
		○ File integrity monitoring (FIM) 
	• Tools: 
		○ FTK Imager 
		○ EnCase 

20.2 Memory Analysis
Explanation
Memory contains:
	• Running processes 
	• Credentials (in RAM) 
	• Network connections 

Tools
	• Volatility 
	• Magnet RAM Capture 

Key Commands
	• pslist → running processes 
	• pstree → process hierarchy 
	• malfind → hidden processes 

SOC IoCs
	• Suspicious processes 
	• Credential dumping tools (Mimikatz) 
	• Hidden processes 

21. MALWARE ANALYSIS
Definition
Malware analysis is the process of reverse engineering malware to understand:
	• Behavior 
	• Origin 
	• Impact 

Objectives
	• Determine what happened 
	• Identify IoCs 
	• Understand attacker sophistication 
	• Find exploited vulnerabilities 
	• Assess damage 

SOC Relevance
	• Build detection rules 
	• Improve threat hunting 
	• Identify persistence mechanisms 

22. TYPES OF MALWARE ANALYSIS
22.1 Static Analysis
Definition
Analyze malware without execution
Techniques
	• Hash analysis 
	• Strings extraction 
	• Header analysis 
Tools
	• PEview 
	• Strings 

22.2 Dynamic Analysis
Definition
Execute malware in controlled environment
Purpose
	• Observe behavior 

Best Practice
Use both static + dynamic analysis

23. STAGES OF MALWARE ANALYSIS
	1. Static Properties Analysis 
	2. Interactive Behavior Analysis 
	3. Fully Automated Analysis 
	4. Manual Code Reversing 

24. SOC ANALYST APPROACH TO MALWARE
Key Actions
1. Analyze Unknown Programs
	• Check source 
	• Verify signature 
2. Examine Behavior
	• File changes 
	• Network activity 
3. Monitor Legitimate Tools Misuse
	• PowerShell abuse 
	• cmd.exe usage 
4. Memory Forensics
	• Detect in-memory malware 
5. Persistence Detection
	• Startup entries 
	• Scheduled tasks 

IoCs
	• Suspicious processes 
	• Unusual network connections 
	• Registry changes 

25. MALWARE ANALYSIS CHALLENGES
Key Challenges
	• Obfuscation 
	• Encryption 
	• Large data volume 
	• Legal restrictions 
	• Privacy concerns 
	• Anti-analysis techniques 

SOC Reality
	• Malware often: 
		○ Detects sandbox 
		○ Changes behavior 

26. MALWARE ANALYSIS TOOLS
Hardware
	• Write blockers 
	• Storage devices 
	• Sandbox environment 

Software Tools
Static Analysis
	• PEview 
	• IDA Pro 
Dynamic Analysis
	• Wireshark 
	• tcpdump 
Memory Analysis
	• Volatility 
Debugging
	• OllyDbg 
String Analysis
	• BinText 

27. DYNAMIC MALWARE ANALYSIS
Definition
Execute malware in sandbox to observe behavior

Requirements
	• Virtual Machine 
	• Isolated environment 

Two Stages
1. System Baselining
Explanation
	• Take system snapshot before execution 

2. Host Integrity Monitoring
Explanation
	• Observe changes after execution 

28. SYSTEM BASELINING
Steps
	1. Take baseline snapshot 
	2. Run malware 
	3. Take second snapshot 
	4. Compare differences 

Tool
	• WhatChanged Portable 

SOC Value
	• Detect: 
		○ Registry changes 
		○ File changes 

29. HOST INTEGRITY MONITORING
System Behavior Analysis
Monitor:
	• Registry changes 
	• Processes 
	• Services 
	• API calls 
	• Drivers 
	• Files 

Network Behavior Analysis
Monitor:
	• IP connections 
	• Ports 
	• DNS queries 
	• Browsing activity 

IoCs
	• New registry keys 
	• Suspicious outbound traffic 
	• New services 

30. MALWARE ANALYSIS USING ANY.RUN
Definition
Cloud-based sandbox

Features
	• Real-time interaction 
	• Behavior analysis 
	• Detailed reports 

SOC Use
	• Quick malware triage 

31. MALWARE ANALYSIS USING AUTORUNS
Purpose
	• Detect persistence 

What it shows
	• Startup programs 
	• Registry autoruns 

IoCs
	• Unknown startup entries 

32. MALWARE ANALYSIS USING PROCESS HACKER
Purpose
	• Monitor processes 

Detection
	• Suspicious parent-child processes 

Example
	• PowerShell spawning cmd.exe 

33. MALWARE ANALYSIS USING REDLINE
Features
	• Memory analysis 
	• Process analysis 

Use
	• Analyze RAM dumps 

34. MALWARE ANALYSIS USING VOLATILITY
Definition
Memory forensics framework

Key Functions
1. System Info
	• Identify OS, processes 
2. Process Analysis
	• pslist → processes 
	• pstree → hierarchy 
3. Hidden Process Detection
	• malfind 

SOC Use Case
	• Detect: 
		○ Rootkits 
		○ In-memory malware 

STATIC MALWARE ANALYSIS
Definition
Static Malware Analysis is the process of analyzing a malware file without executing it to determine:
	• Malicious intent 
	• Capabilities 
	• Indicators of compromise (IoCs) 

Explanation
	• No execution → safe analysis 
	• Focus on: 
		○ File structure 
		○ Code patterns 
		○ Embedded data 
Key Advantage
	• No risk of infection 
Limitation
	• Cannot observe runtime behavior 

SOC Relevance
	• Used in: 
		○ Email attachment analysis 
		○ Malware triage 
		○ Threat intelligence enrichment 

Real-World Example
SOC receives suspicious .exe:
	• Compute hash 
	• Check VirusTotal 
	• Extract strings 
	• Identify suspicious domains 

36. STATIC MALWARE ANALYSIS TECHNIQUES
1. File Fingerprinting
2. Local & Online Malware Scanning
3. Strings Analysis
4. PE Analysis
5. File Dependency Analysis
6. Disassembly / Reverse Engineering
7. Packing / Obfuscation Detection

37. FILE FINGERPRINTING (HASH ANALYSIS)
Definition
Creating a unique hash value (MD5, SHA1, SHA256) for a file to identify it.

Explanation
	• Every file → unique fingerprint 
	• Even 1-byte change → different hash 

Process
	1. Generate hash 
	2. Compare with threat databases 
	3. Track changes during analysis 

Tools
	• HashMyFiles 
	• HashCalc 
	• VirusTotal 

SOC Detection Perspective
Use Cases
	• Detect known malware 
	• IOC matching 
SIEM Example

file_hash="e99a18c428cb38d5f260853678922e03"

IoCs
	• Known malicious hash 
	• Hash mismatch after modification 

Interview Points
	• Difference: MD5 vs SHA256 
	• Why hashing is important? 

38. LOCAL & ONLINE MALWARE SCANNING
Definition
Scanning malware using antivirus engines locally or online.

Explanation
Local Scan
	• Use AV engine 
	• Detect known signatures 
Online Scan
	• Upload file to multi-engine platforms 

Example: VirusTotal
	• Checks file against 70+ AV engines 

SOC Relevance
	• Quick malware classification 
	• Confidence building 

IoCs
	• Detection by multiple AV engines 
	• Known malware family tags 

Limitation
	• Cannot detect: 
		○ Zero-day malware 
		○ Obfuscated malware 

39. STRINGS ANALYSIS
Definition
Extract readable text (strings) from binary files.

Why Important
Malware often contains:
	• URLs 
	• IP addresses 
	• File paths 
	• Commands 

Tools
	• strings (Linux) 
	• BinText 
	• FLOSS 

Example Command

strings malware.exe

What to Look For
	• Suspicious domains 
	• Hardcoded credentials 
	• Registry keys 
	• File paths 

SOC Detection
IoCs
	• C2 server domains 
	• Suspicious URLs 
Example

http://malicious-domain.com/c2

Interview Points
	• Why strings analysis is useful? 
	• What indicators can be extracted? 

40. STRINGS COMMAND UTILITY
Explanation
Used to:
	• Extract readable content 
	• Identify malware behavior 

SOC Usage
	• Generate detection rules 
	• Identify: 
		○ C2 communication 
		○ Payload delivery URLs 

41. PORTABLE EXECUTABLE (PE) ANALYSIS
Definition
Analyzing Windows executable file structure.

PE Structure Includes
	• Headers 
	• Sections (.text, .data) 
	• Imports/Exports 
	• Metadata 

Key Information Extracted
	• Compilation time 
	• Imported libraries 
	• Embedded strings 
	• Version info 

Tools
	• PE Explorer 
	• pestudio 

SOC Relevance
	• Identify: 
		○ Suspicious imports (e.g., CreateRemoteThread) 
		○ Packed binaries 

IoCs
	• Suspicious DLL imports 
	• Unusual compile time 

42. FILE DEPENDENCY ANALYSIS
Definition
Analyzing external libraries used by malware.

Explanation
Programs rely on:
	• System DLLs 
	• External libraries 

Tools
	• Dependency Walker 
	• Dependency-Check 
	• Snyk 

What to Look For
	• Suspicious APIs 
	• Network-related functions 

Example APIs
	• WinExec 
	• LoadLibrary 
	• CreateProcess 

SOC Relevance
	• Helps identify: 
		○ Malware capabilities 
		○ Persistence mechanisms 

43. PESTUDIO ANALYSIS
Definition
Tool for static analysis of PE files.

Features
	• Analyze: 
		○ Imports/exports 
		○ Strings 
		○ Indicators 

SOC Value
	• Risk scoring of malware 
	• Identify suspicious behavior quickly 

44. MALWARE DISASSEMBLY
Definition
Converting machine code into assembly code.

Purpose
	• Understand: 
		○ Logic 
		○ Behavior 
		○ Exploitation techniques 

Tools
	• IDA Pro 
	• Ghidra 
	• WinDbg 

Explanation
	• Reverse engineer malware 
	• Identify: 
		○ Encryption routines 
		○ Exploits 

SOC Relevance
	• Mostly used by: 
		○ Malware analysts (L2/L3) 
	• Not daily L1 task, but important knowledge 

45. PACKING & OBFUSCATION DETECTION
Definition
Techniques used to hide malware code.

Indicators
	• High entropy 
	• No readable strings 
	• Suspicious section names 

SOC Relevance
	• Packed malware → evade detection 

46. FULL STATIC ANALYSIS WORKFLOW (SOC)
Step-by-Step
	1. Receive suspicious file 
	2. Compute hash 
	3. Check VirusTotal 
	4. Extract strings 
	5. Analyze PE structure 
	6. Check dependencies 
	7. Identify IoCs 
	8. Create detection rule 

47. REAL-WORLD SOC SCENARIO
Scenario: Suspicious Email Attachment
Steps:
	1. Download attachment 
	2. Generate SHA256 hash 
	3. Upload to VirusTotal 
	4. Extract strings 
	5. Identify: 
		○ C2 domain 
		○ File path 
	6. Create SIEM alert 

48. IOC SUMMARY (STATIC ANALYSIS)
File-Based IoCs
	• Hash values 
	• File name patterns 
Network IoCs
	• IPs 
	• Domains 
Host-Based IoCs
	• Registry keys 
	• File paths

