1. INCIDENT RESPONSE
Definition
Incident Response (IR) is a systematic and structured approach used to handle security incidents with the goals of:
	• Minimizing damage 
	• Reducing recovery time 
	• Lowering operational costs 
Explanation
Incident Response is not just about fixing attacks — it is a full lifecycle process involving:
	• Detection 
	• Analysis 
	• Containment 
	• Eradication 
	• Recovery 
	• Lessons learned 
It includes:
	• Technical actions → containment, eradication, recovery 
	• Non-technical actions → communication, legal handling, policy enforcement 
Example
	• A brute-force attack detected in logs: 
		○ Technical: Block IP, disable account 
		○ Non-technical: Inform management, document incident 
SOC Relevance
SOC analysts are responsible for:
	• Detecting incidents 
	• Investigating alerts 
	• Escalating and documenting incidents 
Detection Perspective
	• SIEM alerts 
	• IDS/IPS logs 
	• EDR alerts 
	• Firewall logs 
IoCs
	• Multiple failed login attempts 
	• Suspicious IP addresses 
	• Unusual network traffic spikes 
Interview Points
	• IR = Process, not a tool 
	• Includes both technical + business response 
	• Goal: minimize impact, not just stop attack 

2. PREPARATION FOR INCIDENT RESPONSE
Definition
Preparation involves establishing the foundation, processes, and resources required before incidents occur.
Explanation
Two scenarios:
	1. IR process already exists 
		○ Evaluate current process 
		○ Identify gaps 
		○ Improve and update 
	2. No IR process 
		○ Define vision and mission 
		○ Get management approval 
		○ Build IR plan and team 
Key Steps
	• Define IR vision & mission 
	• Obtain funding and approvals 
	• Develop IR policies and procedures 
	• Define incident criteria 
	• Build IR team 
	• Evaluate security posture 
	• Harden systems if required 
Example
	• Organization performs a security audit → finds no IR plan → creates one 
SOC Relevance
Preparation defines:
	• Playbooks used by SOC 
	• Escalation paths 
	• Alert handling procedures 
Detection Perspective
	• Baseline normal activity 
	• Define thresholds for alerts 
IoCs
	• Lack of monitoring tools 
	• No defined response workflow 
Interview Points
	• Preparation is the most critical phase 
	• Without preparation → response fails 

3. DEVELOP IR PLAN
Definition
An IR Plan defines the future course of action for handling incidents.
Key Components
	• Mission and vision statements 
	• Goals of IR initiative 
	• Management approval 
	• Strategy and timelines 
	• Performance metrics 
	• Resource utilization 
	• Organizational alignment 
Explanation
It answers:
	• What to do during an incident 
	• Who will do it 
	• How it will be done 
Example
	• Playbook for phishing attack handling 
SOC Relevance
SOC analysts follow:
	• Runbooks/playbooks derived from IR plan 
Detection Perspective
	• Alerts mapped to response procedures 
Interview Points
	• IR plan = high-level strategy 
	• SOP = detailed execution 

4. DEVELOP IR POLICY
Definition
Policy = High-level guidelines to achieve IR goals.
IR Policy Must Contain
	1. Management commitment 
	2. Purpose and objectives 
	3. Scope 
	4. Definition of incidents 
	5. Roles and responsibilities 
	6. Severity prioritization 
	7. Performance metrics 
	8. Reporting guidelines 
	9. Communication guidelines 
Example
	• Policy defines what qualifies as a “security incident” 
SOC Relevance
	• Defines escalation rules 
	• Defines severity classification 
Interview Points
	• Policy = "WHAT" 
	• Procedure = "HOW" 

5. DEVELOP IR PROCEDURES (SOPs)
Definition
Procedures are step-by-step instructions to execute IR plan.
Explanation
Includes:
	• Processes 
	• Techniques 
	• Templates 
	• Forms 
Objective
	• Standardize response 
	• Reduce human errors 
	• Enable automation 
Example
	• SOP for malware containment: 
		1. Isolate system 
		2. Capture memory 
		3. Block IOC 
SOC Relevance
SOC analysts strictly follow SOPs
Detection Perspective
	• Automated playbooks (SOAR tools) 
Interview Points
	• SOP = repeatable tasks 
	• Ensures consistency 

6. BUILD INCIDENT RESPONSE TEAM (IRT)
Steps
	• Design IR plan 
	• Set expectations 
	• Define mission & vision 
	• Communicate plan 
	• Hire/train team 
	• Announce team 
	• Evaluate effectiveness 
Explanation
IRT includes:
	• SOC analysts 
	• Incident handlers 
	• Forensics experts 
	• Management 
	• Legal team 
SOC Relevance
SOC is part of IRT
Interview Points
	• Cross-functional team is required 

7. COMPUTER FORENSICS LAB
Definition
A controlled environment used for digital investigations.
Components
	• Planning & budgeting 
	• Location considerations 
	• Work area setup 
	• Skilled personnel 
	• Physical security 
	• Licensing 
Explanation
Used to:
	• Analyze malware 
	• Investigate breaches 
	• Preserve evidence 
SOC Relevance
	• SOC escalates incidents to forensic team 
Interview Points
	• Evidence integrity is critical (chain of custody) 

8. SECURITY POLICY, PROCEDURES, AND AWARENESS
Security Policy
	• Defines architecture of security environment 
Security Procedures
	• Protect systems from misuse 
Security Awareness
	• Training employees to prevent incidents 
Example
	• Phishing awareness training 
SOC Relevance
	• Reduces false positives 
	• Improves detection accuracy 

9. INCIDENT TRIAGE
Definition
Process of prioritizing incidents based on severity.
Steps
	• Incident analysis & validation 
	• Classification 
	• Check if within scope 
	• Prioritize 
Explanation
	• High priority → immediate response 
	• Low priority → scheduled handling 
SOC Relevance
SOC analysts perform triage daily
Detection Perspective
	• Alert severity levels in SIEM 
Interview Points
	• Triage = prioritization 

10. INCIDENT ANALYSIS AND VALIDATION
Definition
Process of verifying whether an alert is a real incident (True Positive).
Steps
	• Log analysis 
	• Event correlation 
	• Network/system profiling 
Explanation
	• Identify attack vector 
	• Determine affected systems 
	• Assess impact 
Example
	• Correlate failed logins + successful login → brute force success 
SOC Relevance
Core responsibility of SOC analyst
Detection Perspective
	• SIEM correlation rules 
IoCs
	• Suspicious login patterns 
	• Abnormal traffic 
	• Malware signatures 
Interview Points
	• FP vs TP determination 

11. INCIDENT CLASSIFICATION
Definition
Categorizing incidents based on:
	• Severity 
	• Impact 
	• Attack type 
Factors
	• Nature of incident 
	• Criticality of systems 
	• Legal requirements 
Example
	• Malware → Medium 
	• Data breach → High 
SOC Relevance
Determines escalation path

12. SEVERITY ASSESSMENT
Definition
Evaluating impact using risk calculation.
Formula
Risk = Likelihood × Impact × Asset Value
Explanation
	• Likelihood = probability of attack 
	• Impact = damage caused 
	• Asset value = importance 
SOC Relevance
Helps prioritize incidents
Interview Points
	• Risk-based decision making 

13. CONTAINMENT
Definition
Limiting the spread of an incident.
Explanation
	• Decide strategy 
	• Assign tasks: 
		○ Technical team 
		○ Management 
		○ Legal 
Process
	• Check if contained 
	• If not → update strategy 
	• If yes → escalate to next phase 
Example
	• Isolate infected host 
SOC Detection Perspective
	• Block IP 
	• Disable accounts 
	• Network segmentation 
IoCs
	• Lateral movement attempts 
	• C2 communication 
Interview Points
	• Short-term vs long-term containment 

14. ERADICATION
Definition
Removing the root cause of the incident.
Steps
	• Identify cause 
	• Eliminate threat 
	• Check similar systems 
	• Patch vulnerabilities 
	• Harden systems 
Actions
	• Update antivirus 
	• Apply patches 
	• Remove malware 
	• Close attack vectors 
Example
	• Remove backdoor + patch vulnerability 
SOC Relevance
	• Ensure no persistence remains 
IoCs
	• Malware files 
	• Registry changes 
	• Persistence mechanisms 
Interview Points
	• Root cause removal is critical 

15. RECOVERY
Definition
Restoring systems to normal operations.
Steps
	• Restore data from backups 
	• Ensure backup is clean 
	• Restart services 
Explanation
	• Verify no malware remains 
	• Ensure business continuity 
Example
	• Restore compromised server from backup 
SOC Relevance
	• Monitor systems post-recovery 
Interview Points
	• Clean backup validation is critical 

16. POST-INCIDENT ACTIVITIES
Definition
Activities performed after incident resolution.
Steps
	• Documentation 
	• Impact assessment 
	• Policy review 
	• Close investigation 
	• Disclosure (if required) 
Explanation
	• Improve future response 
	• Identify gaps 
Example
	• Update SIEM rules after attack 
SOC Relevance
	• Create better detection rules 
Detection Perspective
	• Add new correlation rules 
Interview Points
	• Lessons learned phase is essential 

FINAL REAL-WORLD FLOW (IMPORTANT FOR INTERVIEW)
	1. Preparation 
	2. Detection & Analysis 
	3. Triage & Classification 
	4. Containment 
	5. Eradication 
	6. Recovery 
	7. Lessons Learned 

COMMON INTERVIEW QUESTIONS
Q1: What is Incident Response?
Structured approach to detect, respond, and recover from incidents.
Q2: Difference between IR Plan, Policy, Procedure?
	• Policy = Guidelines 
	• Plan = Strategy 
	• Procedure = Steps 
Q3: What is containment?
Limiting spread of attack.
Q4: What is eradication?
Removing root cause.
Q5: What is triage?
Prioritizing incidents.
Q6: What is a true positive?
Real security incident.


POST-INCIDENT ACTIVITIES
Definition
Post-Incident Activities are actions performed after incident resolution to:
	• Improve future response 
	• Identify weaknesses 
	• Strengthen security posture 
Key Objectives
	• Improve response capability 
	• Evaluate effectiveness of IR process 
	• Identify gaps in security controls 
	• Prevent recurrence 
Steps Involved
1. Incident Documentation
	• Record: 
		○ Timeline of attack 
		○ Actions taken 
		○ Tools used 
		○ Impact 
	• Maintain evidence for legal/compliance 
2. Incident Impact Assessment
	• Determine: 
		○ Affected systems 
		○ Data loss 
		○ Financial/business impact 
3. Review and Revise Policies
	• Update: 
		○ Detection rules 
		○ IR playbooks 
		○ Security policies 
4. Close the Investigation
	• Ensure: 
		○ No residual threats 
		○ All systems stable 
5. Incident Disclosure
	• Inform: 
		○ Management 
		○ Customers (if needed) 
		○ Regulatory bodies 
SOC Relevance
	• Create new SIEM rules 
	• Improve detection accuracy 
	• Reduce false positives 
Detection Perspective
	• Add new correlation rules based on attack patterns 
IoCs
	• Newly discovered attacker IPs/domains 
	• Malware hashes 
Interview Points
	• “Lessons Learned” phase 
	• Critical for continuous improvement 

18. CONTAINMENT OF UNAUTHORIZED ACCESS INCIDENTS
Definition
Containment actions to stop attackers who gained unauthorized access.
Key Actions
1. Isolate Affected Systems
	• Prevent lateral movement 
	• Disconnect compromised hosts 
2. Disable Affected Services
	• Example: Disable FTP, RDP 
3. Block Attacker Routes
	• Block IPs 
	• Kill sessions 
4. Disable Compromised Accounts
	• Reset passwords 
	• Disable accounts 
5. Enhance Physical Security
	• Secure server rooms 
	• Restrict access 
Example
	• Attacker logs in via stolen credentials → isolate system + disable account 
SOC Detection Perspective
	• Detect abnormal login patterns 
	• Monitor account misuse 
IoCs
	• Login from unusual geolocation 
	• Multiple sessions from different IPs 
	• Privilege escalation logs 
Interview Points
	• Always isolate first, then investigate 

19. RECOVERY AFTER UNAUTHORIZED ACCESS INCIDENTS
Steps
1. Identify Attack Type
	• Determine: 
		○ Entry point 
		○ Exploited vulnerability 
2. Mitigate Vulnerabilities
	• Patch systems 
	• Harden configurations 
3. Restore Data
	• Use clean backups 
4. Restore Systems
	• Bring systems to operational state 
5. Apply Updates
	• Patch OS and applications 
6. Monitoring
	• Enable enhanced logging 
7. Update Policies
	• Improve access controls 
SOC Relevance
	• Monitor for re-entry attempts 
Interview Points
	• Recovery must ensure no persistence remains 

20. CONTAINMENT OF INAPPROPRIATE USAGE INCIDENTS
Definition
Handling misuse of systems (e.g., downloading malicious content, policy violations)
Actions
	• Shut down infected systems 
	• Filter ports/protocols 
	• Block malicious emails 
	• Install spam filters 
	• Block malicious URLs 
	• Limit user privileges 
	• Reset passwords 
	• Track user activity 
Example
	• Employee downloading malware → block access + restrict privileges 
SOC Detection Perspective
	• Web proxy logs 
	• Email logs 
	• DNS logs 
IoCs
	• Access to suspicious domains 
	• Large downloads from unknown sources 

21. ERADICATION OF INAPPROPRIATE USAGE INCIDENTS
Actions
	• Deploy firewall & IDS/IPS 
	• Configure email servers (block spam) 
	• Enable URL filtering 
	• Enforce encrypted protocols (HTTPS, SSH, IPSec) 
	• Use VPNs 
	• Monitor user activity logs 
SOC Relevance
	• Policy enforcement 
	• Continuous monitoring 

22. RECOVERY AFTER INAPPROPRIATE USAGE INCIDENTS
Actions
	• Inform legal team 
	• Involve HR 
	• Conduct employee training 
	• Educate on safe browsing 
	• Update policies 
	• Update antivirus 
Interview Points
	• Involves HR + legal → non-technical IR aspect 

23. CONTAINMENT OF APPLICATION SECURITY INCIDENTS
Actions
	1. Enable rate limiting (blackhole feature) 
	2. Increase server capacity 
	3. Define user thresholds 
	4. Restrict unauthorized access 
	5. Business continuity planning 
	6. Alert users during incidents 
	7. Deploy traffic filters 
	8. Restore systems and fix vulnerabilities 
Example
	• DDoS attack → rate limiting + scaling servers 
SOC Detection Perspective
	• WAF logs 
	• Traffic spikes 
	• API abuse 

24. HOW TO ERADICATE WEB APPLICATION SECURITY INCIDENTS
Key Controls
Input Validation
	• Prevent injection attacks 
WAF / IDS
	• Filter malicious traffic 
Secure Coding
	• Avoid hardcoded credentials 
	• Minimize privileges 
Database Security
	• Use parameterized queries 
Logging & Testing
	• Dynamic testing 
	• Code analysis 
System Hardening
	• Disable unnecessary services 
	• Patch systems 
Output Handling
	• Sanitize outputs 
SOC Relevance
	• Monitor: 
		○ WAF logs 
		○ Application logs 

25. ERADICATING INJECTION ATTACKS
Types Covered
SQL Injection
	• Use parameterized queries 
	• WAF protection 
	• Disable dangerous DB features 
Command Injection
	• Validate inputs 
	• Escape characters 
	• Use safe APIs 
File Injection
	• Disable risky PHP settings 
	• Validate file paths 
LDAP Injection
	• Validate inputs 
	• Limit query results 
IoCs
	• ' OR 1=1 
	• Suspicious command execution 
	• Unexpected DB queries 
Interview Points
	• Input validation is key defense 

26. ERADICATING BROKEN AUTHENTICATION
Controls
	• Use SSL/TLS 
	• Hash passwords 
	• Avoid session in URLs 
	• Use MFA 
	• Enforce password policies 
	• Limit login attempts 
	• Secure session IDs 
	• Implement session timeout 
IoCs
	• Brute-force attempts 
	• Session hijacking 

27. ERADICATING SENSITIVE DATA EXPOSURE
Controls
	• Encrypt sensitive data 
	• Avoid weak crypto 
	• Proper key management 
	• Use strong algorithms 
	• Enable HSTS 
	• Disable caching for sensitive data 
IoCs
	• Plaintext credentials 
	• Unencrypted traffic 

28. ERADICATING BROKEN ACCESS CONTROL
Controls
	• Enforce access checks 
	• Avoid predictable IDs 
	• Session timeout 
	• Limit permissions 
	• Remove session tokens after logout 
Example
	• IDOR attack prevention 

29. ERADICATING SECURITY MISCONFIGURATION
Controls
	• Disable unused services 
	• Remove default accounts 
	• Apply patches 
	• Enforce HTTPS 
	• Secure cookies 
	• Validate certificates 
	• Encrypt backend communication 
IoCs
	• Default credentials 
	• Open ports/services 

30. ERADICATING XSS ATTACKS
Controls
	• Validate all inputs 
	• Encode outputs 
	• Use CSP 
	• Filter scripts 
	• Convert special characters 
	• Avoid trusting HTTPS alone 
IoCs
	• <script> tags in input 
	• Suspicious JavaScript execution 

31. ERADICATING INSECURE DESERIALIZATION
Controls
	• Validate serialized data 
	• Avoid untrusted deserialization 
	• Restrict classes 
	• Re-architect applications 
	• Filter serialized inputs 
IoCs
	• Unexpected object execution 
	• Application crashes 

32. ERADICATING INSUFFICIENT LOGGING & MONITORING
Controls
	• Define logging scope 
	• Set logging baseline 
	• Include user context 
	• Log for proactive detection 
	• Prevent log injection 
SOC Relevance
	• Core of detection capability 
Interview Points
	• “If it’s not logged, it’s not detectable” 

FINAL INTERVIEW SUMMARY (IMPORTANT)
Incident Response Phases
	1. Preparation 
	2. Detection & Analysis 
	3. Containment 
	4. Eradication 
	5. Recovery 
	6. Post-Incident 
Key Concepts Recruiters Ask
	• Difference: Policy vs Plan vs Procedure 
	• True Positive vs False Positive 
	• Containment vs Eradication 
	• Risk calculation 
	• SOC role in IR lifecycle
45. CONTAINMENT OF INSIDER THREATS
Definition
Insider Threats involve malicious or negligent actions by trusted individuals (employees, contractors, vendors).
Objectives
	• Prevent further damage 
	• Preserve evidence 
	• Limit access and data exposure 
Key Actions
1. Isolate Affected Systems
	• Disconnect compromised endpoints 
	• Prevent further misuse 
2. Block All Access
	• Disable: 
		○ Email accounts 
		○ Application access 
		○ Physical access (ID cards) 
		○ VPN credentials 
3. Seize Devices
	• Collect: 
		○ Laptops 
		○ Mobile devices 
	• Preserve evidence (forensics) 
4. Inform Stakeholders
	• Notify departments impacted 
	• Assess business impact 
5. Continuous Monitoring
	• Track suspect activity 
	• Wait for management/legal decision 
6. Forensic Investigation
	• Analyze: 
		○ Portable devices 
		○ Account activity logs 
7. Legal Action
	• File complaint as per jurisdiction 
8. Restrict Physical Entry
	• Prevent suspect from entering premises 
9. Protect Information Flow
	• Limit insider knowledge exposure 
10. Organization-wide Password Reset
	• Prevent further compromise 
SOC Detection Perspective
	• Monitor: 
		○ Privilege abuse 
		○ Data exfiltration 
		○ Unusual access patterns 
IoCs
	• Large data transfers 
	• Access outside working hours 
	• Access to unauthorized systems 
Interview Points
	• Insider threats are harder than external attacks 
	• Require technical + HR + legal coordination 

46. ERADICATING INSIDER THREATS
A. Access Control
Controls
	• Least privilege principle 
	• Role-based access control (RBAC) 

B. Data Encryption
Controls
	• Encrypt data: 
		○ At rest 
		○ In transit 
		○ In use 
	• Use strong encryption (≥256-bit keys) 

C. Isolate Storage
	• Avoid storing sensitive data on network-accessible systems 

D. Password Policies
	• Enforce strong password rules 
	• Regular password changes 

E. Data-Centric Protection (DCAP)
	• Monitor: 
		○ User access 
		○ Data movement 
	• Detect privilege misuse 

SOC Relevance
	• User Behavior Analytics (UBA/UEBA) 
Interview Points
	• Least privilege is the strongest defense 

47. INSIDER THREATS – HUMAN RESOURCES CONTROLS
Controls
	1. Define strict employee behavior policies 
	2. Conduct employee behavior analysis 
	3. Monitor financial stress indicators 
	4. Manage workplace conflicts 
	5. Provide security awareness training 
	6. Perform background checks 
	7. Monitor third-party vendors 
SOC Relevance
	• HR signals often indicate insider risk 
Interview Points
	• Insider threats are often behavioral, not just technical 

48. INSIDER THREATS – NETWORK SECURITY
Controls
	1. Configure firewalls 
	2. Monitor outbound traffic 
	3. Restrict file transfers 
	4. Disable unauthorized sharing tools 
	5. Scan emails for sensitive data 
	6. Enforce MFA 
	7. Implement account management policies 
SOC Detection Perspective
	• Detect: 
		○ Data exfiltration 
		○ Suspicious outbound traffic 
IoCs
	• Upload to cloud storage 
	• Use of unauthorized tools 

49. INSIDER THREATS – ACCESS CONTROLS
Controls
	1. Grant access based on job role 
	2. Restrict: 
		○ Software installation 
		○ Log modification 
	3. Enable admin alerts for changes 
	4. Regular access audits 
	5. Strict sensitive data access policies 
	6. Supervisor approval for access 
	7. Data owner permission 
	8. Remove access after termination 
Interview Points
	• “Access should be revoked immediately after exit” 

50. INSIDER THREATS – PRIVILEGED USERS
Controls
	1. Non-repudiation logging 
	2. Disable default admin accounts 
	3. Use unique admin accounts 
	4. Encrypt sensitive backups 
	5. Monitor admin activities 
SOC Relevance
	• Privileged accounts are high-risk 
IoCs
	• Admin activity at unusual times 
	• Unauthorized config changes 

51. INSIDER THREATS – LOG MONITORING
Controls
	1. Enforce logging policies 
	2. Perform regular audits 
	3. Enable audit trails 
	4. Monitor changes to critical systems 
	5. Protect logs from tampering 
	6. Use IDS & file integrity monitoring 
SOC Relevance
	• Logging = core of insider detection 
Interview Points
	• Logs must be centralized and immutable 

52. INSIDER THREATS – PHYSICAL SECURITY
Controls
	• Auto-lock systems 
	• Secure data centers 
	• Block portable media 
	• Use biometric authentication 
	• Lock storage devices 
	• CCTV surveillance 
	• Soundproof meeting rooms 
	• Secure disposal (shredding) 
	• Wipe storage devices 
	• Enforce vendor policies 
Real-World Insight
	• Many breaches happen via USB devices 

53. RECOVERY FROM INSIDER ATTACKS
Steps
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
SOC Relevance
	• Ensure attacker has no persistence 

54. CONTAINMENT OF MALWARE INCIDENTS
Definition
Prevent malware from spreading across network.
Steps
	1. Isolate infected host 
	2. Analyze network logs 
	3. Cut network services (if widespread) 
	4. Use VLAN isolation 
	5. Allow only safe communication (VPN) 
	6. Identify malware patterns/signatures 
	7. Disable vulnerable services 
SOC Detection Perspective
	• EDR alerts 
	• Lateral movement detection 
IoCs
	• Suspicious processes 
	• C2 traffic 
	• Unknown binaries 

55. ERADICATION OF MALWARE INCIDENTS
Actions
	• Patch vulnerabilities 
	• Share malware intelligence 
	• Implement application whitelisting 
	• Block malicious websites 
	• Prevent auto-downloads 
	• Restrict BIOS/system access (virtualization) 
	• Secure browser settings: 
		○ Block pop-ups 
		○ Disable auto-downloads 
Interview Points
	• Malware removal ≠ eradication → must fix root cause 

56. RECOVERY AFTER MALWARE INCIDENTS
Steps
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
SOC Relevance
	• Continuous monitoring post-recovery 
IoCs
	• Reinfection attempts 
	• Residual malware artifacts 
	45. CONTAINMENT OF INSIDER THREATS
	Definition
	Insider Threats involve malicious or negligent actions by trusted individuals (employees, contractors, vendors).
	Objectives
		• Prevent further damage 
		• Preserve evidence 
		• Limit access and data exposure 
	Key Actions
	1. Isolate Affected Systems
		• Disconnect compromised endpoints 
		• Prevent further misuse 
	2. Block All Access
		• Disable: 
			○ Email accounts 
			○ Application access 
			○ Physical access (ID cards) 
			○ VPN credentials 
	3. Seize Devices
		• Collect: 
			○ Laptops 
			○ Mobile devices 
		• Preserve evidence (forensics) 
	4. Inform Stakeholders
		• Notify departments impacted 
		• Assess business impact 
	5. Continuous Monitoring
		• Track suspect activity 
		• Wait for management/legal decision 
	6. Forensic Investigation
		• Analyze: 
			○ Portable devices 
			○ Account activity logs 
	7. Legal Action
		• File complaint as per jurisdiction 
	8. Restrict Physical Entry
		• Prevent suspect from entering premises 
	9. Protect Information Flow
		• Limit insider knowledge exposure 
	10. Organization-wide Password Reset
		• Prevent further compromise 
	SOC Detection Perspective
		• Monitor: 
			○ Privilege abuse 
			○ Data exfiltration 
			○ Unusual access patterns 
	IoCs
		• Large data transfers 
		• Access outside working hours 
		• Access to unauthorized systems 
	Interview Points
		• Insider threats are harder than external attacks 
		• Require technical + HR + legal coordination 
	
	46. ERADICATING INSIDER THREATS
	A. Access Control
	Controls
		• Least privilege principle 
		• Role-based access control (RBAC) 
	
	B. Data Encryption
	Controls
		• Encrypt data: 
			○ At rest 
			○ In transit 
			○ In use 
		• Use strong encryption (≥256-bit keys) 
	
	C. Isolate Storage
		• Avoid storing sensitive data on network-accessible systems 
	
	D. Password Policies
		• Enforce strong password rules 
		• Regular password changes 
	
	E. Data-Centric Protection (DCAP)
		• Monitor: 
			○ User access 
			○ Data movement 
		• Detect privilege misuse 
	
	SOC Relevance
		• User Behavior Analytics (UBA/UEBA) 
	Interview Points
		• Least privilege is the strongest defense 
	
	47. INSIDER THREATS – HUMAN RESOURCES CONTROLS
	Controls
		1. Define strict employee behavior policies 
		2. Conduct employee behavior analysis 
		3. Monitor financial stress indicators 
		4. Manage workplace conflicts 
		5. Provide security awareness training 
		6. Perform background checks 
		7. Monitor third-party vendors 
	SOC Relevance
		• HR signals often indicate insider risk 
	Interview Points
		• Insider threats are often behavioral, not just technical 
	
	48. INSIDER THREATS – NETWORK SECURITY
	Controls
		1. Configure firewalls 
		2. Monitor outbound traffic 
		3. Restrict file transfers 
		4. Disable unauthorized sharing tools 
		5. Scan emails for sensitive data 
		6. Enforce MFA 
		7. Implement account management policies 
	SOC Detection Perspective
		• Detect: 
			○ Data exfiltration 
			○ Suspicious outbound traffic 
	IoCs
		• Upload to cloud storage 
		• Use of unauthorized tools 
	
	49. INSIDER THREATS – ACCESS CONTROLS
	Controls
		1. Grant access based on job role 
		2. Restrict: 
			○ Software installation 
			○ Log modification 
		3. Enable admin alerts for changes 
		4. Regular access audits 
		5. Strict sensitive data access policies 
		6. Supervisor approval for access 
		7. Data owner permission 
		8. Remove access after termination 
	Interview Points
		• “Access should be revoked immediately after exit” 
	
	50. INSIDER THREATS – PRIVILEGED USERS
	Controls
		1. Non-repudiation logging 
		2. Disable default admin accounts 
		3. Use unique admin accounts 
		4. Encrypt sensitive backups 
		5. Monitor admin activities 
	SOC Relevance
		• Privileged accounts are high-risk 
	IoCs
		• Admin activity at unusual times 
		• Unauthorized config changes 
	
	51. INSIDER THREATS – LOG MONITORING
	Controls
		1. Enforce logging policies 
		2. Perform regular audits 
		3. Enable audit trails 
		4. Monitor changes to critical systems 
		5. Protect logs from tampering 
		6. Use IDS & file integrity monitoring 
	SOC Relevance
		• Logging = core of insider detection 
	Interview Points
		• Logs must be centralized and immutable 
	
	52. INSIDER THREATS – PHYSICAL SECURITY
	Controls
		• Auto-lock systems 
		• Secure data centers 
		• Block portable media 
		• Use biometric authentication 
		• Lock storage devices 
		• CCTV surveillance 
		• Soundproof meeting rooms 
		• Secure disposal (shredding) 
		• Wipe storage devices 
		• Enforce vendor policies 
	Real-World Insight
		• Many breaches happen via USB devices 
	
	53. RECOVERY FROM INSIDER ATTACKS
	Steps
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
	SOC Relevance
		• Ensure attacker has no persistence 
	
	54. CONTAINMENT OF MALWARE INCIDENTS
	Definition
	Prevent malware from spreading across network.
	Steps
		1. Isolate infected host 
		2. Analyze network logs 
		3. Cut network services (if widespread) 
		4. Use VLAN isolation 
		5. Allow only safe communication (VPN) 
		6. Identify malware patterns/signatures 
		7. Disable vulnerable services 
	SOC Detection Perspective
		• EDR alerts 
		• Lateral movement detection 
	IoCs
		• Suspicious processes 
		• C2 traffic 
		• Unknown binaries 
	
	55. ERADICATION OF MALWARE INCIDENTS
	Actions
		• Patch vulnerabilities 
		• Share malware intelligence 
		• Implement application whitelisting 
		• Block malicious websites 
		• Prevent auto-downloads 
		• Restrict BIOS/system access (virtualization) 
		• Secure browser settings: 
			○ Block pop-ups 
			○ Disable auto-downloads 
	Interview Points
		• Malware removal ≠ eradication → must fix root cause 
	
	56. RECOVERY AFTER MALWARE INCIDENTS
	Steps
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
	SOC Relevance
		• Continuous monitoring post-recovery 
	IoCs
		• Reinfection attempts 
		• Residual malware artifacts 
	
	FINAL MASTER SUMMARY (CRITICAL FOR INTERVIEW)
	Full Incident Response Lifecycle
		1. Preparation 
		2. Detection & Analysis 
		3. Triage 
		4. Containment 
		5. Eradication 
		6. Recovery 
		7. Post-Incident 
	
	TOP REAL-WORLD SOC TAKEAWAYS
		• Insider threats = hardest to detect 
		• Email + Malware = most common attack vectors 
		• Logging + Monitoring = backbone of SOC 
		• Least privilege = strongest control 
		• Detection depends on visibility 
	
	HIGH-IMPACT INTERVIEW QUESTIONS
	Q1: How do you detect insider threats?
		• UEBA, logs, abnormal behavior, data exfiltration 
	Q2: Difference between containment and eradication?
		• Containment = stop spread 
		• Eradication = remove root cause 
	Q3: What is malware containment?
		• Isolate host, block communication, analyze logs 
	Q4: How to prevent insider threats?
		• Least privilege, monitoring, HR controls 
	Q5: What is most important for SOC detection?
		• Logging + visibility 
	
	ENDPOINT DETECTION AND RESPONSE (EDR)
	Definition
	Endpoint Detection and Response (EDR) is a security solution that:
		• Monitors endpoint activities (workstations, servers, laptops) 
		• Detects threats using behavioral analysis 
		• Investigates and responds to incidents in real time 
	Core Functions
		• Continuous monitoring of endpoints 
		• Detection of: 
			○ Indicators of Compromise (IoCs) 
			○ Behavioral anomalies 
		• Threat investigation 
		• Automated response actions 
	
	How EDR Works
	Data Collection
		• Process execution logs 
		• File activity 
		• Registry changes 
		• Network connections 
	Analysis
		• Behavioral analytics (not just signatures) 
		• Detect: 
			○ Fileless malware 
			○ Living-off-the-land attacks 
	Response
		• Alert SOC team 
		• Trigger automated actions 
	
	Example
		• Suspicious PowerShell execution detected: 
			○ EDR flags anomaly 
			○ SOC investigates 
			○ Endpoint isolated 
	
	SOC Detection Perspective
	Logs Collected
		• Process creation (e.g., cmd.exe, powershell.exe) 
		• File modifications 
		• Network connections 
		• Registry changes 
	Common IoCs
		• Suspicious processes 
		• Unknown executables 
		• Privilege escalation attempts 
	
	Interview Points
		• EDR focuses on endpoint visibility 
		• Detects behavior, not just signatures 
		• Critical for modern attacks (fileless malware) 
	
	67. INCIDENT RESPONSE USING EDR
	Key Capabilities
	1. Alert Generation
		• Provides: 
			○ Affected endpoint 
			○ Attack type 
			○ Timeline of events 
	2. Data Collection
		• Detailed telemetry for investigation 
	3. Automated Response
		• Endpoint isolation 
		• Network blocking 
		• Process termination 
	
	Example Workflow
		1. Alert triggered (malware detected) 
		2. Analyst reviews: 
			○ Process tree 
			○ File hashes 
		3. Action: 
			○ Kill process 
			○ Isolate system 
		4. Remediation applied 
	
	SOC Relevance
		• Reduces response time 
		• Enables automated containment 
	
	Interview Points
		• EDR = Detection + Response + Forensics 
	
	68. AUTOMATED INCIDENT RESPONSE (CYBEREASON EDR)
	Overview
	Cyberreason EDR:
		• Detects ransomware & fileless attacks 
		• Uses: 
			○ Threat intelligence 
			○ Behavioral analytics 
		• Provides automated remediation 
	
	Key Features
		• Lightweight agent 
		• Centralized dashboard 
		• Automated investigation 
		• Cross-endpoint visibility 
	
	SOC Benefit
		• Faster investigation 
		• Reduced manual workload 
	
	Interview Insight
		“Modern SOC relies heavily on automation through EDR tools.”
	
	69. RSA NETWITNESS EDR
	Definition
	RSA NetWitness provides:
		• Endpoint + Network visibility 
		• Prioritized alerts 
		• Deep investigation capabilities 
	
	Features
		• Full visibility across endpoints 
		• Threat prioritization 
		• Attack reconstruction (timeline) 
	
	SOC Relevance
		• Combines: 
			○ Endpoint telemetry 
			○ Network analysis 
	
	Interview Points
		• NetWitness = strong in forensics + visibility 
	
	70. DETECTING RANSOMWARE USING EDR
	Definition
	Ransomware is malware that encrypts files and demands payment.
	
	Data Collected by EDR
		• Process execution 
		• File changes 
		• Registry activity 
		• Network connections 
	
	Investigation Steps
	1. Memory Analysis
		• Capture RAM for fileless malware 
	2. Timeline Creation
		• Identify attack sequence 
	3. File Analysis
		• Detect: 
			○ Mass file encryption 
			○ File renaming patterns 
	4. Network Analysis
		• Detect: 
			○ C2 communication 
			○ Data exfiltration 
	5. Persistence Check
		• Registry keys 
		• Scheduled tasks 
	
	SOC IoCs (VERY IMPORTANT)
		• Rapid file encryption 
		• Unknown processes modifying files 
		• Suspicious extensions (e.g., .locked, .encrypted) 
		• High CPU/disk usage 
	
	Example
		• powershell.exe → downloads payload → encrypts files 
	
	Interview Points
		• Ransomware detection relies on behavior patterns 
	
	71. EXTENDED DETECTION AND RESPONSE (XDR)
	Definition
	XDR extends EDR by integrating multiple security layers:
		• Endpoint 
		• Network 
		• Cloud 
		• Email 
		• Applications 
	
	Core Concept
		XDR = EDR + NDR + SIEM-like correlation + AI
	
	Why XDR is Needed
	EDR limitation:
		• Only endpoint visibility 
	XDR solves:
		• Cross-platform visibility 
	
	XDR Features
		• Unified visibility 
		• AI/ML-based detection 
		• Automated response 
		• Threat correlation across layers 
	
	Architecture
	1. Ingest
		• Data from: 
			○ Email 
			○ Firewall 
			○ Network 
			○ Endpoint 
			○ Cloud 
	2. Detection
		• Alert prioritization 
		• Correlation analysis 
	3. Response
		• Automated workflows 
		• Threat hunting 
		• Incident investigation 
	
	Example
		• Phishing email → user clicks link → endpoint infected
XDR: 
		• Correlates email + endpoint + network logs 
		• Detects full attack chain 
	
	SOC Detection Perspective
	Logs Used
		• EDR logs 
		• Firewall logs 
		• Email logs 
		• Cloud logs 
	
	IoCs
		• Multi-stage attack patterns 
		• Cross-system anomalies 
	
	Interview Points
	Key Differences
	Feature	EDR	XDR
	Scope	Endpoint only	Multiple layers
	Detection	Local	Correlated
	Visibility	Limited	Unified
	Response	Endpoint actions	Cross-system
	
	FINAL REAL-WORLD SOC UNDERSTANDING
	What Recruiters Expect You to Know
	1. EDR
		• Endpoint monitoring 
		• Behavioral detection 
		• Automated response 
	2. XDR
		• Multi-layer visibility 
		• Threat correlation 
		• Advanced detection 
	3. Ransomware Detection
		• File behavior 
		• Process activity 
		• Timeline analysis 
	
	FINAL INTERVIEW GOLDEN ANSWERS
	Q1: What is EDR?
	A solution that monitors endpoint activity, detects threats using behavioral analysis, and provides response capabilities.
	Q2: Difference between EDR and XDR?
		• EDR = Endpoint only 
		• XDR = Multiple security layers integrated 
	Q3: How does EDR detect ransomware?
		• File encryption behavior 
		• Suspicious processes 
		• Registry persistence 
	Q4: What is advantage of XDR?
		• Correlates data across systems → better detection
	72. SECURITY ORCHESTRATION, AUTOMATION, AND RESPONSE (SOAR)
	Definition
	SOAR is a security solution that integrates:
		• Security tools 
		• Processes 
		• People 
	to automate and orchestrate incident response workflows.
	
	Core Purpose
		• Automate repetitive security tasks 
		• Improve incident response speed 
		• Reduce manual workload 
		• Enhance threat visibility and coordination 
	
	Key Functions of SOAR
	1. Orchestration
		• Connects multiple security tools: 
			○ SIEM 
			○ EDR 
			○ Firewalls 
			○ Threat intelligence platforms 
	2. Automation
		• Executes predefined actions: 
			○ Block IP 
			○ Isolate endpoint 
			○ Send alerts 
	3. Response
		• Enables faster and consistent incident handling 
	
	Capabilities
		• Aggregates security data from multiple sources 
		• Automates tasks such as: 
			○ Data collection 
			○ Alert triage 
			○ Initial investigation 
		• Integrates threat intelligence feeds 
		• Provides centralized dashboards 
		• Generates reports for compliance and auditing 
	
	Example
	Without SOAR
		1. Analyst receives alert 
		2. Manually checks logs 
		3. Blocks IP manually 
		4. Sends email to team 
	With SOAR
		1. Alert triggered 
		2. SOAR automatically: 
			○ Enriches data (IP reputation) 
			○ Blocks IP 
			○ Notifies team 
			○ Creates ticket 
	
	SOC Relevance
		• Reduces analyst fatigue 
		• Enables handling of high alert volume 
		• Standardizes response actions 
	
	Detection Perspective
		• Works with SIEM alerts 
		• Uses IoCs from threat intelligence 
	
	Interview Points
		• SOAR = automation + orchestration + response 
		• Works on top of SIEM and EDR 
	
	73. SPLUNK SOAR
	Definition
	Splunk SOAR is a platform that:
		• Provides a single pane of glass for security operations 
		• Automates workflows across multiple tools 
	
	Key Benefits
		• Centralized visibility 
		• Faster incident response 
		• Reduced manual effort 
		• Seamless integration with SIEM 
	
	Features
		• Manual event creation 
		• Playbook creation 
		• Automated actions 
		• Third-party tool integration 
		• Automated account monitoring 
	
	Example
		• Phishing email detected: 
			○ Splunk SOAR: 
				§ Extracts URLs 
				§ Checks reputation 
				§ Blocks malicious links 
				§ Notifies users 
	
	SOC Relevance
		• Widely used in enterprise SOCs 
		• Strong integration with Splunk SIEM 
	
	Interview Points
		• Splunk SOAR = automation layer over SIEM 
	
	74. SOAR TOOLS (INDUSTRY)
	Common Tools
		• ServiceNow Security Incident Response 
		• IBM QRadar SOAR 
		• Swimlane SOAR 
		• D3 Security 
		• Heimdal Threat Hunting Platform 
	
	SOC Insight
		• Tools differ, but concept remains same:
Automation + Integration + Response 
	
	75. SOAR PLAYBOOK
	Definition
	A SOAR Playbook is a predefined workflow that automates incident response actions.
	
	Key Characteristics
		• Contains: 
			○ Automated steps 
			○ Manual steps 
		• Standardizes incident response 
		• Reduces response time 
		• Ensures consistency 
	
	Playbook Components (VERY IMPORTANT)
	Core Fields
		• Playbook Version & Date 
		• Owner/Reviewer 
		• Metrics & Reporting 
		• Execution Platform 
		• Incident Documentation 
		• Communication Plan 
		• Resolution Steps 
	
	Types of Actions
	Automated Actions
		• Block IP 
		• Quarantine file 
		• Disable account 
	Manual Actions
		• Analyst investigation 
		• Decision-making 
	
	Example: Phishing Playbook
		1. Extract email indicators 
		2. Check URL reputation 
		3. If malicious: 
			○ Block domain 
			○ Quarantine email 
			○ Notify users 
		4. Create incident report 
	
	SOC Relevance
		• Used daily in SOC operations 
		• Helps junior analysts perform consistently 
	
	Interview Points
		• Playbooks = SOPs implemented in automation 
	
	76. INTEGRATING SOAR WITH SIEM
	Concept
		• SIEM detects 
		• SOAR responds 
	
	Workflow
		1. SIEM generates alert 
		2. SOAR triggers playbook 
		3. Automated response executed 
		4. Analyst reviews outcome 
	
	Key Benefits
		• Reduced response time 
		• Automated threat handling 
		• Improved accuracy 
		• Continuous improvement 
	
	Use Cases
	1. Phishing Attack
		• SIEM detects phishing email 
		• SOAR: 
			○ Quarantines email 
			○ Blocks sender 
			○ Notifies user 
	
	2. Malware Infection
		• SIEM detects suspicious activity 
		• SOAR: 
			○ Isolates endpoint 
			○ Triggers scan 
			○ Updates threat intel 
	
	3. Data Breach
		• SIEM detects exfiltration 
		• SOAR: 
			○ Blocks access 
			○ Starts containment 
			○ Alerts SOC team 
	
	SOC Detection Perspective
	Data Sources
		• SIEM alerts 
		• EDR logs 
		• Firewall logs 
		• Threat intelligence 
	
	Interview Points (CRITICAL)
	Q: Difference between SIEM and SOAR?
	Feature	SIEM	SOAR
	Function	Detection	Response
	Role	Alerting	Automation
	Focus	Logs & correlation	Actions & workflows
	
	FINAL MASTER SUMMARY (EDR + XDR + SOAR)
	Full Modern SOC Stack
		• SIEM → Detects threats 
		• EDR → Endpoint visibility & response 
		• XDR → Cross-platform detection 
		• SOAR → Automation & orchestration 
	
	Real SOC Workflow
		1. SIEM detects alert 
		2. EDR provides endpoint data 
		3. XDR correlates across systems 
		4. SOAR automates response 
