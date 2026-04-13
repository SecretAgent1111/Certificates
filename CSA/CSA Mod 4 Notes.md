Core Components of SIEM
1. Log Sources (Data Sources)
These are systems that generate logs:
	• Network Devices: Routers, switches, VPN 
	• Security Devices: Firewalls, IDS/IPS, WAF 
	• Servers: OS logs, web servers, application servers 
	• Applications: Business apps, APIs 
Example Logs
	• Firewall: Allowed/Blocked traffic 
	• Windows: Event ID 4625 (failed login) 
	• Web server: HTTP requests 

2. Collectors / Agents / Connectors
	• Collect logs from different sources 
	• Normalize data into a standard format 
	• Forward logs to SIEM 
Key Point:
Some collectors also perform log filtering and preprocessing

3. Central Engine (Core of SIEM)
Responsible for:
	• Correlation 
	• Rule execution 
	• Threat detection 
Functions:
	• Correlation 
	• Alerting 
	• Data mining 
	• Analysis 

4. Database (Storage Layer)
	• Stores logs for a defined retention period 
	• Used for: 
		○ Forensics 
		○ Compliance 
		○ Historical analysis 

SIEM Workflow (Real SOC Flow)
	1. Logs generated → Devices 
	2. Sent to → Collectors 
	3. Processed by → SIEM Engine 
	4. Stored in → Database 
	5. Visualized in → Dashboard / Alerts 

SOC Relevance
	• Central point for monitoring all security events 
	• Enables detection of: 
		○ Brute force 
		○ Malware 
		○ Data exfiltration 
		○ Insider threats 
2. SIEM Detection: Signature-Based vs Anomaly-Based
Signature-Based Detection
Definition
Detection based on predefined patterns (signatures).
Explanation
	• Matches known attack patterns 
	• Example: SQL Injection payload detection 
Examples
	• IDS signatures 
	• WAF rules (OWASP CRS) 

Advantages
	• Fast 
	• Accurate for known attacks 
Limitations
	• Cannot detect new/unknown attacks 

Anomaly-Based Detection
Definition
Detection based on deviation from normal behavior.
Explanation
	• Uses UEBA (User and Entity Behavior Analytics) 
	• Often ML-driven 

Examples
	• User logs in at 3 AM from new country 
	• Sudden spike in traffic 

Advantages
	• Detects unknown threats 
Limitations
	• False positives 
	• Requires tuning 

Comparison Table
Feature	Signature	Anomaly
Detection	Known attacks	Unknown attacks
Method	Pattern matching	Behavior analysis
Driven by	Human rules	Machine learning

SOC Relevance
	• Real SOC uses both together 
	• Signature = detection baseline 
	• Anomaly = advanced threat hunting 

Interview Question
Q: Which is better?
Answer: Both are complementary.

3. Detection Use Cases (CRITICAL FOR SOC L1)

3.1 SQL Injection Detection
Definition
Injection of malicious SQL queries into input fields.

Data Sources
	• IIS / Apache logs 
	• WAF logs 
	• IDS logs 

Detection Logic
Patterns:
	• ' OR 1=1-- 
	• UNION SELECT 
	• exec xp_cmdshell 

Example Detection Rules
	• Error-based: 
		○ SQL errors in logs 
	• Union-based: 
		○ union select 
	• Boolean-based: 
		○ OR 1=1 

IoCs
	• Suspicious query strings 
	• Database errors 
	• Repeated malformed requests 

SOC Investigation
	• Check source IP 
	• Check affected URL 
	• Check DB logs 
	• Correlate with WAF 

Interview Question
Q: How detect SQL injection in SIEM?
Answer:
	• Look for SQL keywords in HTTP requests 
	• Monitor DB errors 
	• Use regex-based alerts 

3.2 Cross-Site Scripting (XSS)
Definition
Injection of malicious JavaScript into web apps.

Detection Patterns
	• <script> 
	• javascript: 
	• alert() 

Types
	• Reflected 
	• Stored 
	• DOM-based 

IoCs
	• Script tags in URL 
	• Suspicious encoding 
	• HTML/JS payloads 

SOC Relevance
	• Leads to session hijacking 

3.3 Directory Traversal
Definition
Accessing restricted files using path manipulation.

Patterns
	• ../ 
	• /etc/passwd 

IoCs
	• Requests for system files 
	• Encoded traversal attempts 

SOC Action
	• Block IP 
	• Check file access logs 

3.4 Account Takeover Detection
Definition
Unauthorized access to user accounts.

Detection Logic
	• Multiple successful logins quickly 
	• Login from multiple locations 

Data Sources
	• Authentication logs 
	• Geo logs 
	• UEBA 

IoCs
	• Impossible travel 
	• Sudden login spike 

3.5 Parameter Tampering
Definition
Manipulation of URL parameters.

Example

/transfer?amount=100 → 10000

IoCs
	• Changing IDs 
	• Repeated parameter modification 

3.6 Brute Force Attack
Definition
Repeated login attempts.

Detection Logic
	• Multiple failed logins 
	• Threshold-based detection 

Key Patterns
	• Same IP → multiple attempts 
	• Multiple users → same password (password spray) 

IoCs
	• Event ID 4625 spikes 
	• Lockouts 

SOC Investigation
	• Check IP reputation 
	• Check success after failures 

3.7 Brute Force on SSH
Detection Indicators
	• Many SSH attempts from single IP 
	• "Failed password" logs 

Logs Example

Failed password for root from 192.168.1.1

3.8 Brute Force on SQL Server
Indicators
	• Multiple DB login failures 
	• High login attempts 

3.9 Brute Force on Web Apps
Indicators
	• High POST requests 
	• Repeated login attempts 

3.10 High Return Codes Monitoring
Important Codes
	• 404 → scanning 
	• 403 → forbidden access 
	• 401 → authentication failure 
	• 500 → server error 
	• 400 → bad request 

SOC Insight
	• High 404 = directory brute force 
	• High 500 = possible exploitation 

3.11 Bad Bot User-Agents
Definition
Malicious automated tools.

Examples
	• sqlmap 
	• nikto 
	• burp 

Detection
	• Suspicious user-agent strings 

IoCs
	• Known scanning tools 
	• High request frequency 

3.12 TRACE / OPTIONS Method Abuse
Definition
Unusual HTTP methods used for reconnaissance.

Detection
	• TRACE requests 
	• OPTIONS requests 

Risk
	• Information disclosure 

3.13 Bad IP Reputation Monitoring
Definition
Monitoring traffic from malicious IPs.

Sources
	• Threat intelligence feeds 

Categories
	• Botnet 
	• Malware 
	• Spam 
	• Scanner 

SOC Workflow
	1. Match IP with TI feed 
	2. Check logs 
	3. Block if malicious 

IoCs
	• Known malicious IPs 
	• Repeated connections 

FINAL SOC WORKFLOW (VERY IMPORTANT)
Detection → Triage → Investigation
1. Alert Triggered
	• SIEM rule fires 
2. Triage
	• True Positive vs False Positive 
3. Investigation
	• Check logs 
	• Correlate events 
	• Identify impact 
4. Response
	• Block IP 
	• Reset password 
	• Escalate 

TOP INTERVIEW QUESTIONS (VERY IMPORTANT)
Q1: How do you detect brute force?
	• Threshold of failed logins 
	• Same IP patterns 

Q2: What logs are used in SIEM?
	• Firewall, IDS, server, application 

Q3: What is correlation?
	• Linking multiple events to detect attack 

Q4: Difference between UEBA and SIEM?
	• UEBA = behavior analytics 
	• SIEM = log management + detection 

Q5: What is false positive?
	• Alert triggered but no real threat
Endpoint & Behavioral Threat Detection (CRITICAL SOC AREA)

4.1 Detect File Infections
Definition
File infection refers to malware (virus, trojan, ransomware) modifying or embedding itself into legitimate files.

Data Sources
	• Antivirus / Anti-malware logs 
	• EDR (Endpoint Detection & Response) 
	• File Integrity Monitoring (FIM) 
	• SIEM logs 

Detection Logic
Behavioral Indicators:
	• Unusual file execution patterns 
	• Unexpected outbound network traffic 
	• High CPU/disk usage (ransomware behavior) 
	• File hash mismatch (integrity violation) 

IoCs (VERY IMPORTANT)
	• Suspicious file hashes (MD5/SHA256) 
	• Unknown executables in temp directories 
	• Files flagged by threat intelligence (VirusTotal) 
	• Unexpected file modifications 

SOC Investigation
	1. Check file hash (VirusTotal) 
	2. Identify parent process 
	3. Check file location (temp, downloads) 
	4. Review network connections made by file 
	5. Isolate endpoint if malicious 

Real-World Scenario
User downloads PDF → actually malware → creates outbound connection → triggers SIEM alert

Interview Question
Q: How detect malware infection?
Answer:
	• AV/EDR alerts 
	• Suspicious process execution 
	• File hash reputation 

4.2 Detect Unusual File Access
Definition
Access to files in a way that deviates from normal behavior.

Detection Logic
	• Frequent access to sensitive files 
	• PowerShell used to access files 
	• Access outside business context 

IoCs
	• Mass file reads 
	• Access to confidential directories 
	• Use of scripting tools (PowerShell, cmd) 

SOC Insight
Often linked to:
	• Insider threats 
	• Data exfiltration 
	• Malware staging 

4.3 Detect Unusual User Activity
Definition
Abnormal user behavior compared to baseline.

Detection Logic
		○ 100 actions in short time
	• Sudden spike in activity 

IoCs
	• Multiple downloads/uploads 
	• Access to multiple systems quickly 
	• Privilege escalation behavior 

SOC Relevance
	• UEBA-driven detection 
	• Early insider threat indicator 

4.4 Detect Unusual Login Times
Definition
Login activity outside normal working hours.

Detection Logic
	• Login at midnight/odd hours 
	• Login outside geographic baseline 

IoCs
	• After-hours access 
	• Weekend login anomalies 

SOC Investigation
	• Is user on shift? 
	• Check geolocation 
	• Correlate with VPN logs 

Interview Question
Q: What is “impossible travel”?
Login from two distant locations in short time.

5. Data Exfiltration Detection (VERY IMPORTANT FOR INTERVIEWS)

5.1 Data Exfiltration via USB / CD
Definition
Copying sensitive data to removable media.

Data Source
	• OS logs (Windows Event ID 4663) 

Detection Logic
	• Write operations to USB 
	• Access to removable storage 

IoCs
	• Large file transfers to USB 
	• Unauthorized USB usage 

SOC Action
	• Block USB 
	• Investigate user intent 

5.2 Data Exfiltration via FTP
Definition
Transferring data using FTP protocol.

Detection Logic
	• Large uploads via FTP 
	• Unusual file types 

IoCs
	• High data volume outbound 
	• FTP sessions to unknown IPs 

5.3 Data Exfiltration via DNS
Definition
Using DNS queries to exfiltrate data.

Detection Logic
	• Large DNS queries 
	• Encoded payloads in DNS 

IoCs
	• Long domain names 
	• High frequency DNS requests 

SOC Insight
Common in:
	• Advanced malware (C2 communication) 

5.4 Data Exfiltration via HTTPS
Definition
Using encrypted traffic to exfiltrate data.

Detection Logic
	• Large HTTPS uploads 
	• Unusual domains 

Challenge
Encrypted traffic → hard to inspect

IoCs
	• Traffic spikes 
	• Unknown domains 

5.5 Data Exfiltration via Personal Email
Definition
Sending company data to personal email.

Data Source
	• Web proxy 
	• Email logs 

Detection Logic
	• Large attachments 
	• Use of Gmail, Yahoo, etc. 

IoCs
	• Upload to external email 
	• Data transfer outside policy 

5.6 Data Exfiltration via Cloud Storage
Definition
Uploading data to cloud services (Dropbox, Google Drive).

Detection Logic
	• Upload spikes 
	• Access to cloud storage domains 

IoCs
	• Unauthorized uploads 
	• Unknown accounts used 

SOC Action
	• Block cloud apps (CASB) 
	• Investigate user 

6. Insider Threat & Account Abuse Detection

6.1 Data Deletion Attempt
Definition
Malicious deletion of sensitive data.

Detection Logic
	• High number of delete operations 
	• Admin-level activity 

IoCs
	• Mass file deletions 
	• Critical server access 

Real Risk
	• Rogue administrator 

6.2 Account Compromise Detection
Definition
Unauthorized access to user account.

Detection Logic
	• Password changes by others 
	• Login anomalies 

IoCs
	• Password reset events 
	• New device login 

SOC Action
	• Reset password 
	• Enable MFA 

6.3 Unauthorized Data Access / Modification
Definition
Accessing/modifying data without permission.

IoCs
	• Access to restricted files 
	• Data modification logs 

SOC Insight
	• Strong insider threat indicator 

7. Network & Advanced Detection

7.1 TOR Network Detection
Definition
Use of anonymous network (TOR) to hide activity.

Detection Logic
	• Connection to TOR nodes 
	• TOR IP reputation match 

IoCs
	• Known TOR IPs 
	• Encrypted suspicious traffic 

SOC Insight
	• External TOR → possible attacker 
	• Internal TOR → insider threat 

7.2 Detect Connections to Specific Ports
Definition
Monitoring access to restricted ports.

Examples
	• FTP → Port 21 
	• Telnet → Port 23 

Detection Logic
	• Unauthorized port access 
	• Internal policy violations 

IoCs
	• Connections to blocked ports 
	• Suspicious service usage 

FINAL SOC INVESTIGATION PLAYBOOK (ADVANCED)

Step 1: Alert Trigger
	• Example: High file access / data upload 

Step 2: Validate
	• Check logs 
	• Identify false positive 

Step 3: Correlation
	• User + IP + device + time 

Step 4: Scope Impact
	• What data? 
	• Which systems? 

Step 5: Response
	• Block user/IP 
	• Isolate system 
	• Escalate 

TOP INTERVIEW QUESTIONS (HIGH VALUE)

Q1: How detect data exfiltration?
	• Monitor outbound traffic 
	• Detect anomalies in volume 
	• Use DLP + SIEM correlation 

Q2: What is insider threat?
	• Authorized user misusing access 

Q3: How detect DNS exfiltration?
	• Long queries 
	• High frequency 
	• Encoded domains 

Q4: Why HTTPS exfiltration is hard?
	• Encryption hides payload 

Q5: What logs help detect insider threats?
	• File access logs 
	• Authentication logs 
	• Proxy logs
8. Network Threat Detection & Traffic Analysis

8.1 Monitor Unusual Network Traffic Patterns
Definition
Detection of abnormal network behavior that deviates from baseline traffic patterns.

Data Sources
	• Network logs (NetFlow, Zeek) 
	• IDS/IPS logs 
	• Packet capture tools (Wireshark) 
	• Proxy logs 

Detection Logic
Key Indicators:
	• High data volume from a client to a specific domain 
	• Sudden spike in outbound traffic 
	• Repeated communication with same destination 

IoCs
	• Large outbound data transfers 
	• Repeated connections to unknown domains 
	• Traffic outside normal business hours 

SOC Investigation
	1. Identify source IP 
	2. Check destination domain/IP 
	3. Analyze volume (bytes sent) 
	4. Correlate with user + process 
	5. Check if domain is malicious 

Real-World Scenario
Employee system sending large data to unknown domain → possible data exfiltration or malware C2

Interview Question
Q: How detect unusual traffic?
Answer:
	• Baseline normal traffic 
	• Detect deviations (volume, frequency, destination) 

8.2 Monitor Use of Insecure Protocols and Services
Definition
Detection of legacy or insecure protocols that can expose the network.

Examples of Insecure Protocols
	• Telnet (Port 23) 
	• FTP (Port 21) 
	• HTTP (Port 80) 
	• SMBv1 

Detection Logic
	• Identify open insecure ports 
	• Detect services running on endpoints 

IoCs
	• Plaintext authentication 
	• Use of deprecated protocols 
	• Unauthorized services running 

SOC Relevance
	• Prevents future attacks (credential theft, MITM) 

Interview Insight
Q: Why is Telnet insecure?
Because it transmits credentials in plaintext.

8.3 Monitor for Reconnaissance Activity
Definition
Detection of initial attacker probing/scanning before exploitation.

Data Sources
	• IDS/IPS logs 
	• Firewall logs 

Detection Logic
	• High number of GET requests to different URIs 
	• Scanning patterns across endpoints 

IoCs
	• Sequential URL access 
	• High request rate 
	• Access to admin panels, hidden paths 

SOC Insight
Recon = Stage 1 of cyber kill chain

Example Attacks
	• Directory brute force 
	• Web scanning 
	• Vulnerability scanning 

8.4 Detect Man-in-the-Middle (MITM) Attack
Definition
An attacker intercepts communication between two parties.

Data Sources
	• IDS logs 
	• DNS logs 
	• SSL certificate logs 

Detection Logic
	• Same domain accessed repeatedly 
	• Certificate anomalies 
	• Suspicious DNS responses 

IoCs
	• Certificate mismatch 
	• Frequent DNS queries 
	• ARP spoofing indicators 

SOC Investigation
	• Verify SSL certificates 
	• Check DNS logs 
	• Identify rogue devices 

Real Risk
	• Credential theft 
	• Session hijacking 

8.5 Monitor Command and Control (C2) Traffic
Definition
Communication between compromised system and attacker server.

Data Sources
	• DNS logs 
	• Proxy logs 
	• Firewall logs 
	• Endpoint logs 

Detection Logic
	• Repeated communication with external IP/domain 
	• Domain not in private IP range 
	• Beaconing patterns 

IoCs (VERY IMPORTANT)
	• Periodic traffic (beaconing) 
	• Known malicious domains 
	• DNS tunneling patterns 

SOC Investigation
	1. Identify infected host 
	2. Check destination domain reputation 
	3. Analyze traffic frequency 
	4. Isolate endpoint 

Real-World Example
Malware checks in every 5 minutes → C2 beacon

Interview Question
Q: What is beaconing?
Regular interval communication to attacker server.

8.6 Monitor Malicious Traffic from Specific IP
Definition
Tracking suspicious activity from a known IP.

Detection Logic
	• IP accessing multiple domains repeatedly 
	• High number of connections 

IoCs
	• Repeated hits from same IP 
	• Known bad IP (threat intel) 

SOC Action
	• Block IP 
	• Investigate activity 

8.7 Detect Services Running on Non-Standard Ports
Definition
Legitimate services running on unusual ports.

Example
	• HTTP on port 8081 instead of 80 
	• SSH on port 2222 instead of 22 

Detection Logic
	• Compare service vs port 
	• Identify mismatches 

IoCs
	• Unexpected port usage 
	• Hidden services 

SOC Insight
Attackers use this for:
	• Evasion 
	• C2 communication 

8.8 Detect Non-Standard Use of Standard Ports
Definition
Using standard ports for malicious traffic.

Example
	• Non-HTTP traffic on port 80 
	• Non-DNS traffic on port 53 

Detection Logic
	• Protocol mismatch detection 

IoCs
	• Encrypted traffic on unusual protocol 
	• Data tunneling 

SOC Relevance
	• Detects covert channels 

8.9 Important Ports to Monitor (VERY IMPORTANT)
Common Critical Ports
Port	Protocol	Risk
21	FTP	Cleartext credentials
22	SSH	Brute force target
23	Telnet	Insecure
25	SMTP	Spam abuse
53	DNS	Tunneling
80	HTTP	Web attacks
443	HTTPS	Hidden traffic
445	SMB	Lateral movement
3389	RDP	Brute force

SOC Insight
	• Always monitor: 
		○ Authentication ports 
		○ Remote access ports 
		○ File transfer ports 

8.10 Detect Network Scanning Attempts
Definition
Attackers scanning network before attack.

Detection Logic
	• Multiple ports scanned 
	• Multiple IPs targeted 

IoCs
	• SYN scan patterns 
	• High connection attempts 
	• Sequential port scanning 

Tools Used by Attackers
	• Nmap 
	• Masscan 

SOC Action
	• Block scanning IP 
	• Investigate intent 

8.11 Detect Port Scan Attempts
Definition
Specific scanning of ports on a host.

Detection Logic
	• Same IP hitting multiple ports 
	• Rapid connection attempts 

IoCs
	• SYN packets 
	• Short-lived connections 

SOC Investigation
	• Identify source IP 
	• Check scan type 
	• Block or monitor 

FINAL SOC MINDSET (VERY IMPORTANT)

You Should Now Understand:
1. Network Visibility
	• Who is talking to whom 
	• What protocol 
	• How much data 

2. Detection Patterns
	• Volume anomalies 
	• Frequency anomalies 
	• Behavior anomalies 

3. Attack Stages Mapping
Stage	Detection
Recon	Scanning, GET floods
Initial Access	Brute force
C2	Beaconing
Exfiltration	Data transfer

TOP INTERVIEW QUESTIONS (ADVANCED)

Q1: How detect C2 traffic?
	• Look for beaconing 
	• Repeated connections 
	• Suspicious domains 

Q2: Difference between port scan and vulnerability scan?
	• Port scan = open ports 
	• Vulnerability scan = weaknesses 

Q3: What is DNS tunneling?
	• Data exfiltration via DNS queries 

Q4: Why monitor non-standard ports?
	• Attackers hide services 

Q5: How detect reconnaissance?
	• High number of requests 
	• Pattern-based scanning 
Advanced Detection & SOC Correlation Use Cases

9.1 Detect Excessive Firewall Denies
Definition
Large number of blocked connections from a single source within a short time.

Data Source
	• Firewall logs 

Detection Logic
	• Multiple deny logs from same IP within time window 
	• Spike in blocked outbound/inbound connections 

IoCs
	• Repeated denied connections 
	• Sequential port attempts 
	• High connection rate 

What It Indicates
	• Port scanning 
	• Malware beaconing 
	• Misconfigured application 
	• Reconnaissance activity 

SOC Investigation
	1. Identify source IP 
	2. Check destination ports 
	3. Correlate with IDS alerts 
	4. Check if internal or external 

Interview Insight
Q: Is firewall deny always malicious?
No — but high volume patterns are suspicious.

9.2 Detect Access to Disabled Accounts
Definition
Attempts to authenticate using disabled or deprovisioned accounts.

Data Sources
	• Windows Security Logs 
	• Linux authentication logs 

Detection Logic
	• Login attempts to disabled users 

IoCs
	• Repeated login failures for disabled account 
	• Attempts from multiple IPs 

SOC Relevance
	• Possible attacker using old credentials 
	• Insider misuse 

Critical Event IDs (Windows)
	• 4625 (failed login) 
	• Account disabled status check 

9.3 Detect Account Creation, Usage, and Deletion
Definition
Suspicious lifecycle of accounts used for malicious activity.

Detection Logic
	• Account created → used → deleted quickly 

IoCs
	• Short-lived accounts 
	• Privilege escalation 
	• Temporary admin accounts 

SOC Insight
Common in:
	• Insider attacks 
	• Persistence techniques 

9.4 Detect Ransomware Activity
Definition
Malware encrypting files and demanding ransom.

Data Sources
	• Sysmon 
	• File monitoring logs 
	• Endpoint logs 

Detection Logic
Key Behaviors:
	• Large number of file creations 
	• Rapid file renaming 
	• Known ransomware extensions 

Common Extensions (IMPORTANT)
	• .locky, .encrypted, .crypt, .cerber, .wncry 

IoCs
	• Spike in file changes 
	• Mass file renames 
	• High disk activity 

SOC Action
	• Isolate endpoint immediately 
	• Kill process 
	• Block network 

Interview Question
Q: Early sign of ransomware?
Mass file rename activity.

9.5 Detect Rogue DNS Servers (DNS Spoofing / Hijacking)
Definition
Use of unauthorized DNS servers to redirect traffic.

Detection Logic
	• DNS queries not going to known DNS servers 
	• Unknown DNS IPs 

IoCs
	• DNS responses from unknown server 
	• Changed DNS settings 

SOC Risk
	• Phishing 
	• Credential theft 

9.6 Detect DNS Tunneling
Definition
Using DNS protocol to transfer hidden data.

Detection Logic
	• Large DNS request volume 
	• Long domain names 

IoCs (VERY IMPORTANT)
	• Base64 encoded domains 
	• High frequency queries 
	• Large DNS payloads 

SOC Insight
Used by:
	• Malware 
	• APT groups 

9.7 Detect DNS Exfiltration
Definition
Stealing data through DNS queries.

Detection Indicators
	• Long subdomains (>40 characters) 
	• Hex or encoded strings 
	• Repeated queries 

Advanced IoCs
	• TXT record usage 
	• Beaconing intervals 
	• Dynamic DNS usage 

SOC Investigation
	• Decode domain 
	• Check frequency 
	• Identify source system 

9.8 Detect Rogue DHCP Servers
Definition
Unauthorized DHCP server assigning IPs.

Detection Logic
	• DHCP traffic from unknown IP 
	• Multiple DHCP offers 

IoCs
	• UDP port 67 activity 
	• Unknown DHCP responses 

SOC Risk
	• MITM attacks 
	• Traffic redirection 

9.9 Detect Slow DoS Attack
Definition
Attack that keeps connections open to exhaust server resources.

Detection Logic
	• Partial HTTP requests 
	• Delayed header completion 

IoCs
	• Long connection duration 
	• Incomplete HTTP headers 

SOC Insight
Hard to detect — low traffic but high impact

9.10 Detect Zero-Day Attacks
Definition
Exploitation of unknown vulnerabilities.

Detection Approach (VERY IMPORTANT)
Since no signature exists:
	• Use anomaly detection 
	• Behavior monitoring 

Indicators
	• C2 traffic 
	• Lateral movement 
	• Unusual authentication 

SOC Strategy
	• Correlation-based detection 
	• Threat hunting 

9.11 Detect Covering Tracks
Definition
Attacker tries to erase evidence.

Detection Logic
	• Log deletion 
	• Audit disabling 

IoCs
	• Event log cleared 
	• Missing logs 
	• Disabled logging 

Critical Windows Event ID
	• 1102 → Event log cleared 

SOC Action
	• Escalate immediately 
	• Investigate insider or attacker 

9.12 Detect Suspicious VPN Connections
Definition
VPN connections from unusual countries.

Detection Logic
	• Non-whitelisted country access 
	• Geo-location anomalies 

IoCs
	• Login from unexpected country 
	• VPN access outside policy 

SOC Insight
	• Strong indicator of account compromise 

FINAL MASTER SOC DETECTION MINDSET

1. Always Think in Patterns
Pattern Type	Example
Volume	Too many requests
Frequency	Repeated behavior
Behavior	Abnormal user activity
Location	Unusual geolocation

2. Always Correlate
Never trust single log:
	• Combine: 
		○ Authentication logs 
		○ Network logs 
		○ Endpoint logs 

3. Map to Attack Lifecycle
Stage	Detection
Recon	Scanning
Initial Access	Brute force
Execution	Malware
Persistence	Account creation
C2	Beaconing
Exfiltration	Data transfer
Cover Tracks	Log deletion

TOP INTERVIEW QUESTIONS (FINAL LEVEL)

Q1: How detect ransomware early?
	• File rename spikes 
	• Extension changes 

Q2: What is DNS tunneling?
	• Data hidden in DNS queries 

Q3: How detect insider threat?
	• Unusual file access 
	• Data exfiltration 

Q4: What is zero-day detection strategy?
	• Behavior-based detection 

Q5: Why monitor firewall denies?
	• Detect scanning or misbehavior


VPN & Identity-Based Threat Detection

10.1 Detect VPN Connections from Non-Organizational Countries
Definition
Detection of VPN logins from countries where the organization does not operate.

Data Sources
	• Firewall logs 
	• VPN logs 
	• Network flow data 

Detection Logic
	• Compare login country vs allowed country list (whitelist) 

IoCs
	• Login from unexpected geography 
	• Multiple country logins in short time 

SOC Investigation
	1. Verify user travel status 
	2. Check IP reputation 
	3. Correlate with login behavior 

SOC Insight
	• Strong indicator of account compromise 

SIEM Rule Example
	• Alert if: 
		○ Country NOT IN whitelist 

Interview Question
Q: How detect suspicious VPN login?
Answer:
	• Geo-location mismatch + behavior correlation 

10.2 Detect Concurrent VPN Connections
Definition
Multiple VPN sessions for same user from different IPs simultaneously.

Detection Logic
	• Same user → multiple IP addresses at same time 

IoCs
	• Concurrent sessions 
	• Different geolocations 

SOC Insight
	• Indicates: 
		○ Credential theft 
		○ Account sharing 

Investigation
	• Check IP locations 
	• Terminate sessions 
	• Force password reset 

11. Windows-Based SOC Monitoring (VERY IMPORTANT)

11.1 Monitor Suspicious / Administrative Process Creation
Definition
Detection of suspicious processes or admin tools execution.

Data Source
	• Windows Event Logs 

Critical Event ID
	• 4688 → Process Creation 

Suspicious Tools
	• cmd.exe 
	• powershell.exe 
	• netstat.exe 
	• whoami.exe 
	• ipconfig.exe 

Detection Logic
	• Monitor command-line arguments 
	• Detect execution by non-admin users 

IoCs
	• PowerShell bypass commands 
	• Encoded commands 
	• Privileged processes 

SOC Insight
	• Common in: 
		○ Post-exploitation 
		○ Lateral movement 

11.2 Monitor Logon Success & Failure
Event IDs (CRITICAL)
	• 4624 → Successful login 
	• 4625 → Failed login 

Detection Logic
	• Multiple failures → brute force 
	• Success after failures → compromise 

IoCs
	• Login spikes 
	• Multiple IP attempts 

11.3 Monitor File Shares
Event ID
	• 5140 → Network share accessed 

Detection Logic
	• Access to admin shares (C$, ADMIN$) 

IoCs
	• Unauthorized file share access 
	• Lateral movement via SMB 

11.4 Monitor Service Changes
Event ID
	• 7045 → New service installed 

Detection Logic
	• New service creation 
	• Service modification 

IoCs
	• Unknown services 
	• Suspicious service names 

SOC Insight
	• Persistence technique 

11.5 Monitor Windows Registry
Definition
Monitoring changes in Windows Registry.

Detection Logic
	• Registry key creation/modification 

IoCs
	• Autorun entries 
	• Persistence keys 

Example Paths
	• HKLM\Software\Microsoft\Windows\CurrentVersion\Run 

11.6 Detect Privilege Escalation
Event ID
	• 4672 → Special privileges assigned 

Detection Logic
	• Admin privileges granted 

IoCs
	• Unexpected admin access 
	• Privilege escalation chain 

SOC Action
	• Validate user role 
	• Investigate escalation path 

11.7 Detect Malicious PowerShell Activity
Event ID
	• 4104 → Script block logging 

Detection Logic
	• Encoded commands 
	• Execution policy bypass 

IoCs
	• Base64 encoded commands 
	• Suspicious scripts 

SOC Insight
	• Common attack vector 

11.8 Detect Malware via Windows Logs
Detection Logic
	• Changes to executable files 
	• Audit log modifications 

IoCs
	• .exe, .dll modifications 
	• Suspicious file changes 

11.9 Detect Lateral Movement (NetBIOS)
Definition
Movement across systems using SMB/NetBIOS.

Detection Logic
	• Increase in NetBIOS traffic 
	• Failed authentication attempts 

IoCs
	• Multiple host connections 
	• SMB authentication failures 


12. Windows Security Event IDs (VERY IMPORTANT)

MUST KNOW EVENTS
Event ID	Meaning
4624	Successful login
4625	Failed login
4688	Process creation
4672	Privilege escalation
5140	File share access
7045	Service creation
1102	Log cleared

Interview Tip
If you remember these → you will impress recruiters immediately

13. Linux-Based SOC Monitoring

13.1 Monitor Logon Success & Failure
Log Files
	• /var/log/auth.log 
	• /var/log/secure 

Detection Logic
	• Accepted password → success 
	• Failed password → failure 

IoCs
	• Repeated failed SSH logins 
	• Login from unknown IP 

13.2 Detect Privilege Escalation (Linux)
Detection Logic
	• Failed attempts for root login 

IoCs
	• sudo misuse 
	• Root login attempts 

SOC Insight
	• Common brute force or escalation attempt 

14. Advanced Threat Detection

14.1 Detect Covering Tracks
Definition
Attacker removes logs or disables auditing.

IoCs
	• Log deletion 
	• Audit disabled 

Critical Event
	• 1102 → Logs cleared 

14.2 Detect Zero-Day Attack (Advanced)
Detection Strategy
	• Behavioral anomalies 
	• Correlation 

Indicators
	• Unknown process 
	• New network behavior 
	• Lateral movement 

FINAL SOC DETECTION FRAMEWORK (MASTER LEVEL)

Think Like This Always:
1. Identity
	• Who logged in? 
	• From where? 

2. Endpoint
	• What process executed? 
	• What file changed? 

3. Network
	• Where is traffic going? 
	• How much data? 

4. Behavior
	• Is it normal? 

ATTACK CHAIN MAPPING (FINAL REVISION)
Stage	Detection
Recon	Scanning
Access	VPN anomaly
Execution	Process creation
Persistence	Registry/service
Priv Esc	Event 4672
Lateral	File shares
C2	Beaconing
Exfiltration	Data transfer
Cover Tracks	Log deletion

FINAL INTERVIEW QUESTIONS (TOP LEVEL)

Q1: What Windows logs are most important?
	• 4624, 4625, 4688, 4672 

Q2: How detect lateral movement?
	• File shares + NetBIOS + authentication logs 

Q3: How detect privilege escalation?
	• Event ID 4672 

Q4: What is most abused tool in attacks?
	• PowerShell 

Q5: How detect compromised account?
	• Unusual login + behavior anomalies 

15. Alert Triage: Was This an Actual Attack?

Definition
Alert triage is the process of analyzing alerts generated by SIEM/security tools to determine whether they represent a real threat.

Key Concept
Not all alerts = attacks
SOC analyst must decide:
	• Is it malicious? 
	• Is it normal behavior? 
	• Does it need escalation? 

Types of Alerts (CRITICAL – MUST MEMORIZE)

1. False Positive (FP)
Definition
Alert triggered without any real threat
Example
	• Employee fails login multiple times → forgot password 
SOC Action
	• Close alert 
	• Tune rule if frequent 

2. True Positive (TP)
Definition
Alert correctly identifies a real attack
Example
	• Brute force → success login detected 
SOC Action
	• Escalate 
	• Contain incident 

3. False Negative (FN)
Definition
Attack occurs but no alert generated
Example
	• Malware bypasses detection 
Risk
	• MOST DANGEROUS 

4. True Negative (TN)
Definition
No alert and no attack (normal behavior)

SOC Workflow
Step-by-Step
	1. Alert generated 
	2. L1 Analyst triages 
	3. If suspicious → escalate to L2 
	4. L2 confirms incident 
	5. Incident responder takes action 

SOC Relevance
This is daily work of SOC L1 analysts

Interview Question
Q: Difference between FP and FN?
	• FP = alert but no attack 
	• FN = attack but no alert 

16. Eliminating False Positives (VERY IMPORTANT)

Why Important?
Too many false positives =
	• Alert fatigue 
	• Miss real attacks 

9 Key Techniques

1. Define Alert Criticality
	• Not all alerts are urgent 
	• Classify: 
		○ Low / Medium / High 

2. Remove Unnecessary Rules
	• Disable noisy SIEM rules 
	• Avoid default rule overload 

3. Tune Thresholds
	• Example: 
		○ Failed logins threshold = 5 → increase to 10 

4. Understand Policies
	• Acceptable use policy 
	• Business behavior 

5. Know Network Baseline
	• What is normal traffic? 
	• Identify deviations 

6. Use Contextual Data
	• Add: 
		○ User role 
		○ Geo-location 
		○ Asset criticality 

7. Trust Security Controls
	• Example: 
		○ Firewall blocked traffic → already mitigated 

8. Ignore Low-Level Alerts
	• Informational alerts can be filtered 

9. Periodic Rule Tuning
	• Continuous improvement 

SOC Insight (VERY IMPORTANT)
Good SOC analyst =
Not the one who sees alerts
But the one who reduces noise and finds real threats

Interview Question
Q: How reduce false positives?
Answer:
	• Baseline + tuning + context enrichment 

17. What is a SOC Report?

Definition
A SOC report is a structured document that summarizes:
	• Security events 
	• Incidents 
	• Threat landscape 
	• SOC activities 

Purpose
	• Provide visibility to management 
	• Support decision-making 
	• Improve security posture 

Types of SOC Reports

1. Real-Time Monitoring Reports
	• Live dashboards 
	• Immediate threat visibility 

2. Incident Reports
	• Detailed incident analysis 
	• Timeline + impact 

3. Threat Analysis Reports
	• Trends over time 
	• Strategic insights 

SOC Relevance
	• Used by: 
		○ SOC team 
		○ Management 
		○ Auditors 

18. Components of a SOC Report Template

1. Key Findings (Executive Summary)
	• High-level overview 
	• Non-technical 

2. Monitoring Summary
	• Systems monitored 
	• Coverage gaps 

3. Incident Summary
	• Number of incidents 
	• Severity levels 
	• MTTD (Mean Time to Detect) 
	• MTTR (Mean Time to Respond) 

4. Threat Summary
	• Top threats observed 
	• Trends 
	• Future risks 

SOC Insight
Good report =
	• Clear 
	• Actionable 
	• Business-focused 

19. SOC Report Generation with Splunk

What Splunk Provides
	• Dashboards 
	• Visualizations 
	• Automated reporting 

Features
	• Scheduled reports 
	• Alert-based reports 
	• Export (PDF, CSV) 

Workflow
	1. Create search query 
	2. Save as report 
	3. Add visualization 
	4. Schedule report 

SOC Use Case
	• Daily SOC report 
	• Weekly threat summary 
	• Executive dashboard 

Interview Question
Q: How create report in SIEM?
Answer:
	• Query → visualize → schedule 

FINAL SOC L1 REALITY (VERY IMPORTANT)

Your Daily Work Will Be:
1. Monitor Alerts
	• SIEM dashboards 

2. Triage Alerts
	• TP vs FP 

3. Investigate
	• Logs 
	• Correlation 

4. Escalate
	• If confirmed incident 

5. Report
	• Document findings 

COMPLETE SOC MINDSET (FINAL REVISION)

Always Ask:
WHO
	• User / IP 
WHAT
	• Activity 
WHEN
	• Time 
WHERE
	• Location 
WHY
	• Intent 

FINAL INTERVIEW QUESTIONS (IMPORTANT)

Q1: What is alert triage?
	• Process of validating alerts 

Q2: What is most dangerous?
	• False Negative 

Q3: How reduce alert fatigue?
	• Tune rules 

Q4: What is MTTD / MTTR?
	• Detect time / Response time 

Q5: What does SOC report include?
	• Incidents + threats + metrics 
