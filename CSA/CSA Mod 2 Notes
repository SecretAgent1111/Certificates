1. Cyber Threats
Definition
A Cyber Threat is an act where an adversary attempts to:
	• Gain unauthorized access 
	• Exploit communication paths 
	• Compromise systems or data 

Key Objectives of Cyber Threats
	• Data theft 
		○ Personal information 
		○ Financial data 
		○ Login credentials 
	• System compromise 
	• Espionage 
	• Disruption of services 

Core Elements Behind Every Threat
Every cyber threat is based on three fundamental components:
1. Intent
	• The motivation of the attacker 
	• Examples: 
		○ Financial gain 
		○ Political motives 
		○ Espionage 
		○ Revenge 

2. Capability
	• The attacker’s skills, tools, and techniques 
	• Includes: 
		○ Malware 
		○ Exploit kits 
		○ Social engineering 
		○ Advanced TTPs 

3. Opportunity
	• A weakness or vulnerability that allows attack 
	• Example: 
		○ Unpatched system 
		○ Misconfigured firewall 

2. Tactics, Techniques, and Procedures (TTPs)
Definition
TTPs describe:
	• Patterns of attacker behavior 
	• Methods used to carry out attacks 

Why TTPs Are Important (SOC Perspective)
	• Helps in: 
		○ Threat detection 
		○ Threat hunting 
		○ Incident investigation 
	• Used in: 
		○ MITRE ATT&CK framework 

Components of TTPs

1. Tactics
Definition
High-level goals or objectives of an attacker during an attack.
Examples:
	• Initial access 
	• Privilege escalation 
	• Lateral movement 
	• Persistence 

2. Techniques
Definition
Specific methods used to achieve tactics
Examples:
	• Phishing emails 
	• Credential dumping 
	• Command and Control (C2) setup 
	• Data exfiltration 

3. Procedures
Definition
Step-by-step implementation details of techniques
Examples:
	• Sending phishing mail → collecting credentials 
	• Scanning network → identifying weak systems 

Simple Understanding
	• Tactic = What attacker wants 
	• Technique = How attacker does it 
	• Procedure = Exact steps used 

3. Vulnerability, Weakness, Opportunity
Definition
A Vulnerability is:
	• A weakness in design, implementation, or configuration 
	• Can lead to security compromise 

Examples of Vulnerabilities

1. TCP/IP Protocol Vulnerabilities
	• Protocols inherently insecure: 
		○ HTTP 
		○ FTP 
		○ ICMP 
		○ SNMP 
		○ SMTP 
Reason:
	• Lack encryption/authentication 

2. Operating System Vulnerabilities
	• Causes: 
		○ Unpatched systems 
		○ Outdated software 
		○ Misconfigurations 

3. Network Device Vulnerabilities
	• Devices: 
		○ Routers 
		○ Firewalls 
		○ Switches 
Common issues:
	• Weak passwords 
	• No authentication 
	• Insecure routing protocols 
	• Firewall misconfigurations 

4. Reconnaissance Attacks
Definition
Reconnaissance is the initial phase of an attack where attackers:
	• Gather information about the target 

Objective
	• Identify: 
		○ Systems 
		○ Network structure 
		○ Entry points 

Techniques Used
	• Social Engineering 
	• Port Scanning 
	• DNS Footprinting 
	• Ping Sweeping 

Information Collected
	• Domain names 
	• Internal DNS 
	• Network blocks 
	• IP addresses 
	• Public/private systems 
	• TCP/UDP services 
	• ACLs 
	• Routing protocols 
	• VPNs 
	• IDS systems
	• Authentication mechanisms 

5. DNS Footprinting
Definition
DNS Footprinting is used to:
	• Gather DNS information about a target 

Purpose
	• Identify: 
		○ Hosts 
		○ IP addresses 
		○ Mail servers 
		○ DNS servers 

DNS Record Types
Record	Description
A	Maps hostname → IP
MX	Mail server mapping
NS	Name server
CNAME	Alias
SOA	Domain authority info
SRV	Service records
PTR	Reverse lookup
RP	Responsible person
HINFO	Host info (CPU, OS)
TXT	Additional text info

Importance
	• Used in: 
		○ Recon phase 
		○ Social engineering 
		○ Attack planning 

6. Network Sniffing
Definition
Network sniffing is:
	• Capturing and analyzing network packets 

Why Attackers Use Sniffing
	• Monitor traffic 
	• Extract sensitive data 

Conditions That Enable Sniffing
	• Open switch ports 
	• Same network access 
	• Lack of encryption 

Sensitive Data Captured
	1. Syslog traffic 
	2. Telnet passwords 
	3. Router configurations 
	4. FTP passwords 
	5. DNS traffic 
	6. Email traffic 
	7. Web traffic 
	8. Chat sessions 

Key Risk
	• Plaintext protocols = HIGH RISK 

7. Password Attack Techniques

1. Dictionary Attack
	• Uses: 
		○ Predefined wordlist 
	• Fast but limited 

2. Brute Force Attack
	• Tries: 
		○ All combinations 
	• Very slow but effective 

3. Hybrid Attack
	• Combines: 
		○ Dictionary + variations 
	• Example: 
		○ password → Password123 

3.1 Password Spraying Attack- Low and Slow, 1 password many accounts.

4. Birthday Attack
	• Based on: 
		○ Hash collision probability 
	• Targets: 
		○ Cryptographic hashes 

5. Rainbow Table Attack
	• Uses: 
		○ Precomputed hash tables 
	• Faster than brute force 

8. Privilege Escalation
Definition
Privilege escalation is:
	• Gaining higher access rights in a system 

Why Attackers Do It
	• Access sensitive data 
	• Control system 
	• Deploy malware 

Methods Used
	• Exploiting vulnerabilities 
	• Misconfigurations 
	• Weak permissions 

Types of Privilege Escalation

1. Vertical Privilege Escalation
	• User → Admin 
	• Gains higher privileges 
Example:
	• Exploiting kernel vulnerability 

2. Horizontal Privilege Escalation
	• User → Another user 
	• Same privilege level 
Example:
	• Accessing another user’s account 

9. DNS Poisoning
Definition
DNS Poisoning is:
	• Manipulating DNS responses to redirect users 

How It Works
	• Attacker: 
		○ Alters DNS mapping 
	• Result: 
		○ Legit domain → malicious IP 

Example
	• User enters: 
		○ google.com 
	• Redirected to: 
		○ Fake malicious website 

Impact
	• Phishing 
	• Data theft 
	• Malware delivery 

10. DNS Cache Poisoning
Definition
DNS Cache Poisoning involves:
	• Injecting fake DNS records into DNS cache 

How It Works (Step-by-Step)
	1. User sends DNS query 
	2. DNS resolver forwards request 
	3. Attacker sends fake response 
	4. Resolver accepts fake record 
	5. Cache stores malicious mapping 
	6. Future users redirected to attacker site 

Key Difference
	• DNS Poisoning → General manipulation 
	• DNS Cache Poisoning → Stored manipulation in cache 

Impact
	• Large-scale redirection 
	• Persistent attacks 


1. Advanced Persistent Threats (APTs)
Definition
An Advanced Persistent Threat (APT) is:
	• A targeted cyberattack 
	• Where an attacker gains unauthorized access 
	• Remains undetected for a long period 
	• Focuses on data theft rather than disruption 

Key Characteristics
	• Advanced 
		○ Uses sophisticated tools and techniques 
	• Persistent 
		○ Long-term access maintained 
	• Threat 
		○ Highly skilled and organized attackers 

Primary Objective
	• Steal sensitive information, such as: 
		○ Classified documents 
		○ Credentials 
		○ Financial data 
		○ Business strategies 

Information Targeted in APT Attacks
	• User credentials 
	• Personal employee/customer data 
	• Network architecture details 
	• Transaction and credit card information 
	• Organizational strategies 
	• Control system access (critical infrastructure) 

APT Attack Lifecycle (Important)
	1. Initial Access (phishing, exploit) 
	2. Establish Foothold 
	3. Privilege Escalation 
	4. Lateral Movement 
	5. Data Exfiltration 
	6. Maintain Persistence 

SOC Perspective
	• Hard to detect due to: 
		○ Low and slow attacks 
		○ Legitimate-looking traffic 
	• Requires: 
		○ Behavioral analysis 
		○ Threat intelligence 

2. Malware Attacks
Definition
Malware is:
	• Software designed to: 
		○ Disrupt systems 
		○ Steal data 
		○ Gain unauthorized access 
	• Installed without user knowledge 

Common Malware Types

1. Virus
	• Self-replicating 
	• Attaches to files/programs 
	• Spreads when file is executed 

2. Trojan
	• Disguised as legitimate software 
	• Contains malicious payload 
	• Does NOT self-replicate 

3. Spyware
	• Secretly collects user information 
	• Examples: 
		○ Keyloggers 
		○ Tracking tools 

4. Adware
	• Displays unwanted ads 
	• Tracks browsing behavior 

5. Rootkit
	• Hides malicious activities 
	• Provides stealth access 
	• Hard to detect 

6. Backdoor
	• Bypasses authentication 
	• Allows remote access without credentials 

Impact of Malware
	• Data theft 
	• System compromise 
	• Network spread 
	• Persistence 

3. Distributed Denial-of-Service (DDoS)
Definition
DDoS is:
	• An attack using multiple systems 
	• To flood a target 
	• Causing service unavailability 

Key Concept
	• Uses: 
		○ Botnets (infected machines) 
	• Goal: 
		○ Exhaust resources 

DDoS Attack Flow
	1. Attacker controls handler servers 
	2. Handlers control zombie machines 
	3. Zombies send massive traffic 
	4. Target server becomes unavailable 

Types of DDoS

1. Network-Centric Attacks
	• Target: 
		○ Bandwidth 
	• Example: 
		○ UDP flooding 

2. Application-Centric Attacks
	• Target: 
		○ Application layer 
	• Example: 
		○ HTTP flood 

SOC Detection Indicators
	• Sudden traffic spike 
	• High bandwidth usage 
	• Service downtime 

4. Network-based Denial of Service (DoS)
Definition
DoS attack:
	• Single system floods target 
	• Overloads resources 

Common Techniques

1. TCP SYN Flooding
	• Exploits TCP handshake 
	• Leaves connections half-open 

2. UDP Flooding
	• Sends large UDP packets 
	• Overwhelms system 

3. ICMP Smurf Attack
	• Uses broadcast IP 
	• Amplifies traffic 

4. Intermittent Flooding
	• Random bursts of traffic 
	• Harder to detect 

5. MAC Spoofing / Duplicating
Definition
MAC Spoofing is:
	• Changing MAC address to impersonate another device 

How It Works
	1. Attacker scans network for MAC addresses 
	2. Spoofs a legitimate MAC address 
	3. Receives traffic intended for that user 

Impact
	• Unauthorized access 
	• Data interception 
	• Identity impersonation 

6. Switch Port Stealing
Definition
A man-in-the-middle attack:
	• Where attacker floods switch MAC table 

How It Works
	1. Attacker sends forged packets 
	2. Switch associates attacker's MAC with victim’s MAC 
	3. Traffic redirected to attacker 

Impact
	• Traffic interception 
	• Data theft 
	• Network disruption 

7. DHCP Spoofing Attack
Definition
DHCP Spoofing:
	• Attacker introduces a rogue DHCP server 

How It Works
	1. Client requests IP 
	2. Rogue server responds faster 
	3. Assigns: 
		○ Fake IP 
		○ Malicious gateway 

Impact
	• Traffic redirection 
	• Man-in-the-middle attack 
	• Data interception 

8. DHCP Starvation Attack
Definition
DHCP Starvation:
	• Exhausts DHCP IP pool 

How It Works
	1. Attacker sends multiple DHCP requests 
	2. Uses fake MAC addresses 
	3. All IPs get allocated 
	4. Legit users cannot get IP 

Result
	• Denial of service 
	• Network access failure 

9. ARP Poisoning
Definition
ARP Poisoning:
	• Sending fake ARP messages 
	• To map attacker MAC with victim IP 

How It Works
	1. Attacker sends fake ARP replies 
	2. Victim updates ARP table 
	3. Traffic redirected to attacker 

Impact
	• Man-in-the-middle attack 
	• Data interception 
	• Session hijacking 

Final Comparison (Important)
Attack Type	Goal	Method
DoS	Disrupt service	Single source
DDoS	Disrupt service	Multiple sources
APT	Stealth data theft	Long-term attack
Malware	System compromise	Malicious software
ARP Poisoning	Interception	Fake ARP
DHCP Spoofing	Redirection	Fake DHCP
MAC Spoofing	Impersonation	Fake MAC


1. Advanced Persistent Threat (APT) Lifecycle
Definition
The APT Lifecycle describes the step-by-step process followed by advanced attackers to:
	• Infiltrate a network 
	• Maintain long-term access 
	• Steal sensitive data 
	• Remain undetected 

Overview of APT Lifecycle Phases
APT attacks are structured, stealthy, and continuous, typically divided into 6 phases:

1. Preparation
Objective:
Plan and gather intelligence before launching the attack.
Activities:
	• Define target (organization, system, individuals) 
	• Perform reconnaissance 
	• Identify: 
		○ Vulnerabilities 
		○ Entry points 
	• Prepare: 
		○ Tools 
		○ Malware 
	• Set up infrastructure: 
		○ Command & Control (C2) servers 
	• Test attack methods to avoid detection 

SOC Insight:
	• Hard to detect 
	• May observe: 
		○ OSINT collection 
		○ External scanning 

2. Initial Intrusion
Objective:
Gain initial access to the target system.
Methods:
	• Phishing emails 
	• Exploiting vulnerabilities 
	• Malicious attachments 
	• Drive-by downloads 
Key Actions:
	• Deploy malware 
	• Establish outbound connection to attacker (C2 communication) 

SOC Indicators:
	• Suspicious email attachments 
	• Unusual outbound traffic 
	• New processes spawning 

3. Expansion (Privilege Escalation & Lateral Movement)
Objective:
Expand control within the network.
Activities:
	• Privilege escalation 
	• Credential harvesting 
	• Lateral movement across systems 

Techniques:
	• Pass-the-hash 
	• Exploiting weak permissions 
	• Using admin tools (living off the land) 

SOC Indicators:
	• Multiple login attempts 
	• Access across multiple hosts 
	• Abnormal user behavior 

4. Persistence
Objective:
Maintain long-term access without detection.
Methods:
	• Backdoors 
	• Scheduled tasks 
	• Registry modifications 
	• Rootkits 

SOC Indicators:
	• Unauthorized services 
	• Unknown scheduled jobs 
	• Persistence mechanisms in registry/startup 

5. Search and Exfiltration
Objective:
Locate and steal sensitive data.
Activities:
	• Search: 
		○ Databases 
		○ File servers 
	• Compress/encrypt data 
	• Exfiltrate data: 
		○ Over HTTP, DNS, or encrypted channels 

SOC Indicators:
	• Large outbound traffic 
	• Data transfers at unusual times 
	• Encrypted traffic anomalies 

6. Cleanup
Objective:
Remove traces of attack and remain undetected.
Activities:
	• Delete logs 
	• Remove malware traces 
	• Obfuscate actions 

SOC Indicators:
	• Missing logs 
	• Log tampering 
	• Sudden gaps in activity logs 

Full APT Flow (Important)
	1. Preparation 
	2. Initial Intrusion 
	3. Expansion 
	4. Persistence 
	5. Search & Exfiltration 
	6. Cleanup 

Key Characteristics of APT Lifecycle
	• Long-term attack 
	• Stealth-focused 
	• Targeted 
	• Data-driven objective 

2. Supply Chain Attack
Definition
A Supply Chain Attack targets an organization by:
	• Exploiting third-party vendors, suppliers, or partners 
	• Gaining indirect access to the main target 

Key Concept
Instead of attacking the organization directly:
	• Attacker compromises a trusted entity 
	• Uses that trust to infiltrate the target 

Supply Chain Components
An organization’s supply chain includes:
	• People 
	• Software vendors 
	• Hardware providers 
	• Service providers 
	• Processes 
	• Infrastructure 

Attack Flow (Working)
	1. Attacker compromises vendor/supplier 
	2. Injects malicious code or gains access 
	3. Trusted connection used to access target organization 
	4. Establishes backdoor 
	5. Data exfiltration occurs 

Assets Targeted in Supply Chain Attacks

1. Systems
	• Servers 
	• Databases 
	• Cloud infrastructure 

2. People
	• Employees 
	• Customers 

3. Software
	• Applications 
	• Updates 
	• Code repositories 

4. Processes
	• Business workflows 
	• Operations 

5. Personal Data
	• Credentials 
	• Financial information 

6. Services
	• APIs 
	• SaaS platforms 
	• Network services 

Attack Techniques Used

1. Malware Injection
	• Inject malicious code into: 
		○ Software updates 
		○ Applications 

2. Social Engineering
	• Target vendor employees 
	• Gain credentials 

3. Brute Force Attacks
	• Target supplier systems 
	• Weak passwords 

4. Exploiting Vulnerabilities
	• Use unpatched systems in vendor network 

5. Physical Access Modification
	• Tampering with hardware or devices 

6. Open-Source Modification
	• Insert malicious code into open-source libraries 

7. Counterfeiting
	• Replace legitimate hardware/software with malicious versions 

Real-World Understanding
Example:
	• A company trusts a software vendor 
	• Vendor software update is compromised 
	• Malware spreads to all customers 

SOC Detection Challenges
	• Traffic appears legitimate 
	• Comes from trusted sources 
	• Hard to differentiate normal vs malicious 

SOC Indicators
	• Unexpected behavior from trusted apps 
	• Unusual updates or patches 
	• Vendor-related anomalies 
	• Sudden access from third-party systems 

Final Comparison
Aspect	APT Attack	Supply Chain Attack
Target	Specific organization	Indirect via vendor
Duration	Long-term	Can be both
Entry	Direct intrusion	Third-party compromise
Goal	Data theft	Access + spread
Detection	Very difficult	Extremely difficult


1. Common Threats Specific to Host Security
Definition of Host Security
Host security refers to the protection of an individual computing device such as:
	• Desktop 
	• Laptop 
	• Server 
	• Workstation 
	• Virtual machine 
	• Mobile endpoint 
A host is a direct target for attackers because it stores:
	• User data 
	• Credentials 
	• Applications 
	• Configuration files 
	• Logs 
	• Access tokens 
	• Cached sessions 

Common Threat Categories Specific to Host Security
The slide highlights three major threat categories affecting host systems:
1. Malware Infection
Examples shown:
	• Viruses 
	• Worms 
	• Trojan 
	• Spyware 
	• Backdoors 
	• Ransomware 
Explanation
Malware infection happens when malicious software is executed on a host and begins performing unauthorized actions such as:
	• Modifying files 
	• Stealing information 
	• Opening remote access 
	• Encrypting data 
	• Disabling security tools 
	• Creating persistence mechanisms 
Why host systems are targeted
Hosts are attractive because they often contain:
	• Saved passwords 
	• Browsing sessions 
	• Email access 
	• Corporate files 
	• Access to internal systems 

2. Accidental or Intentional Deletion of Data
This threat covers both:
	• Accidental loss, such as a user deleting important files by mistake 
	• Intentional deletion, where a malicious insider or attacker removes or destroys data 
Impact
	• Loss of business data 
	• System instability 
	• Interruption of services 
	• Difficulty in investigations if logs are deleted 
	• Recovery costs and downtime 
Examples
	• Employee accidentally deleting a database export 
	• Insider deleting project files before leaving organization 
	• Malware wiping system files 
	• Attacker deleting backups after gaining admin access 

3. Unauthorized Access
Examples shown:
	• Brute force attack 
	• Privilege escalation 
Explanation
Unauthorized access means an attacker or unapproved user gains access to the host or its resources without proper permission.
Methods include
	• Guessing passwords 
	• Exploiting software vulnerabilities 
	• Stealing credentials 
	• Escalating privileges from normal user to administrator 
	• Using backdoors or remote access tools 
Consequences
	• Data theft 
	• Malware installation 
	• Full host takeover 
	• Lateral movement to other systems 
	• Disabling antivirus or logging 

Why Host-Specific Threats Matter in SOC
From a SOC viewpoint, hosts are often where:
	• Initial compromise is observed 
	• Malware executes 
	• Credentials are stolen 
	• Persistence is established 
	• Data is staged before exfiltration 
A SOC analyst must therefore correlate:
	• Endpoint alerts 
	• Process creation logs 
	• File modification activity 
	• Authentication logs 
	• Network connections from the host 

2. Host-based DoS Attacks
Definition
A host-based Denial-of-Service (DoS) attack is an attack in which the attacker attempts to exhaust the victim host’s resources by exploiting weaknesses in:
	• Operating system implementation 
	• Memory structures 
	• Algorithms 
	• Authentication mechanisms 
	• Application behavior 
Unlike network-centric DoS, which mainly floods network bandwidth, host-based DoS focuses on overloading the target machine itself.

Goal of Host-based DoS
The goal is to make the host:
	• Slow 
	• Unresponsive 
	• Crashed 
	• Unable to serve users 
	• Unable to process requests properly 

What Resources Are Targeted
	• CPU 
	• Memory (RAM) 
	• Disk I/O 
	• Process table 
	• Kernel buffers 
	• Application threads 
	• Authentication services 

Examples Mentioned on the Slide
1. Ping of Death Attack
Definition
A Ping of Death attack involves sending malformed or oversized ICMP packets that can cause the target host to crash or behave unexpectedly.
Concept
Historically, some systems could not properly handle oversized packets after fragmentation and reassembly.
Impact
	• System crash 
	• Freeze 
	• Reboot 
	• Service interruption 
SOC relevance
Modern systems are less vulnerable, but the concept matters because it shows how malformed packets can exploit implementation flaws.

2. Teardrop Attack
Definition
A Teardrop attack uses fragmented packets with overlapping or invalid offsets to confuse the target system during packet reassembly.
Impact
	• Crash 
	• Reboot 
	• Host instability 
Underlying issue
Some operating systems historically failed to correctly handle malformed packet fragments.

Difference Between Host-based DoS and Network-based DoS
Host-based DoS
	• Focuses on exhausting the host’s internal resources 
	• Exploits system or application implementation flaws 
	• Can be triggered with malformed traffic or abusive requests 
Network-based DoS
	• Focuses on saturating bandwidth or network stack 
	• Goal is to block connectivity 

SOC Indicators of Host-based DoS
	• Sudden CPU spikes on one host 
	• Memory exhaustion 
	• Repeated application crashes 
	• Kernel or system errors 
	• Service hangs 
	• Unusual ICMP or fragmented packet activity 
	• Endpoint instability after malformed traffic 

3. Brute Force Attacks
Definition
A brute force attack is a method of gaining unauthorized access by systematically trying all possible password combinations until the correct one is found.

How It Works
The slide flow shows the process clearly:
	1. Attacker begins attack 
	2. A list of usernames and password combinations is prepared 
	3. The system is repeatedly tested with login attempts 
	4. The cycle continues until one password works 
	5. Successful credential validation gives access 

Key Idea
Brute force is based on persistence rather than intelligence. It does not rely on stealth or advanced exploitation. Instead, it depends on:
	• Weak passwords 
	• Lack of rate limiting 
	• No account lockout 
	• Poor monitoring 

Characteristics of Brute Force Attacks
	• Repetitive 
	• Automated 
	• High number of failed logins 
	• Usually targets login portals, VPNs, RDP, SSH, email, and web applications 

Common Variants
Even though the slide says brute force generally, in practice this category includes:
1. Pure Brute Force
	• Tries every possible combination 
2. Dictionary Attack
	• Tries common words 
3. Hybrid Attack
	• Dictionary words with added symbols/numbers 
4. Credential Stuffing
	• Uses leaked username/password pairs 
5. Password Spraying
	• Tries a common password across many accounts 

Why Brute Force Is Dangerous
If successful, attacker may:
	• Log in as a valid user 
	• Access sensitive files 
	• Install malware 
	• Escalate privileges 
	• Move laterally 

SOC Detection Clues
	• Many failed logins from one IP 
	• Many failed logins across many accounts 
	• Burst activity on authentication systems 
	• Login attempts outside normal business hours 
	• Success after multiple failures 

Prevention
	• Strong password policies 
	• MFA 
	• Account lockout thresholds 
	• Login throttling 
	• CAPTCHA on web logins 
	• Monitoring and alerting on repeated failures 

4. Spyware Attacks
Definition
A spyware attack involves installing malicious software that secretly monitors a user’s activity and collects information without consent.
The slide specifically focuses on keylogger spyware.

Keylogger Spyware
A keylogger records the user’s keystrokes and can capture:
	• Passwords 
	• Credit card numbers 
	• Personal messages 
	• Search activity 
	• Corporate credentials 

Attack Flow from the Slide
	1. Attacker prepares malicious payload 
	2. Payload is delivered to the user, often via phishing or a malicious email 
	3. User unknowingly executes the payload 
	4. Keylogger is installed 
	5. Attacker tracks and records keyboard activity 

Objectives of Spyware
	• Credential theft 
	• Financial theft 
	• Identity theft 
	• Corporate espionage 
	• Monitoring victim activity 

Common Delivery Methods
	• Phishing attachments 
	• Fake software downloads 
	• Trojanized applications 
	• Malvertising 
	• Infected websites 
	• Drive-by downloads 

Why Spyware Is Dangerous
It is dangerous because it often:
	• Runs silently 
	• Avoids user notice 
	• Captures highly sensitive information 
	• Gives attacker long-term intelligence 

SOC Indicators
	• Unknown processes running in background 
	• Suspicious startup entries 
	• Unusual outbound communications 
	• Unauthorized browser hooks 
	• New services or scheduled tasks 
	• Antivirus detecting keylogger-like behavior 

Prevention
	• Email filtering 
	• Endpoint protection 
	• Least privilege 
	• User awareness training 
	• Blocking unauthorized software installation 
	• Monitoring persistence mechanisms 

5. Ransomware Attacks
Definition
A ransomware attack is a cyberattack in which attackers encrypt a victim’s files or systems and demand payment in exchange for a decryption key.
This effectively holds the victim’s data or system hostage.

Slide Flow
	1. Attacker delivers malicious payload 
	2. Payload executes on victim system 
	3. Critical files are encrypted 
	4. Target system becomes unusable or data inaccessible 

Primary Goal
	• Extort money from the victim 

Modern Ransomware Reality
Many ransomware groups do more than encryption. They may also:
	• Steal data before encrypting it 
	• Threaten public leak of stolen files 
	• Disable backups 
	• Move laterally across the network 
	• Target domain controllers and servers 
This is often called double extortion.

Typical Effects on the Victim
	• Files become unreadable 
	• Business operations stop 
	• Applications may fail 
	• Shared drives may be encrypted 
	• Recovery becomes difficult without backups 
	• Regulatory and legal consequences may occur if data is stolen 

Common Entry Points
	• Phishing emails 
	• Exposed RDP 
	• Exploited vulnerabilities 
	• Stolen credentials 
	• Malicious downloads 
	• Supply chain compromise 

SOC Indicators
	• Rapid file rename/encryption activity 
	• Many file modification events in a short period 
	• Suspicious PowerShell or scripting 
	• Security tool tampering 
	• Backup deletion commands 
	• Unusual SMB access to many file shares 
	• Ransom note creation 

Prevention
	• Offline and tested backups 
	• Patch management 
	• MFA for remote access 
	• Restrict RDP 
	• EDR/XDR monitoring 
	• Network segmentation 
	• Application allowlisting 
	• User phishing awareness 

1. Un-Patched Computers
Explanation
Systems without security updates remain vulnerable to known exploits.
Why this matters
Attackers often scan for:
	• Outdated operating systems 
	• Missing software patches 
	• Vulnerable services 
Result
	• Remote code execution 
	• Malware installation 
	• Privilege escalation 
	• Full host compromise 

2. Email
Explanation
Email is one of the most common threat delivery methods.
Threats delivered through email
	• Phishing 
	• Malware attachments 
	• Malicious links 
	• Credential harvesting pages 
	• Business email compromise attempts 
Why email is effective
It targets human trust and can bypass technical controls if the user interacts.

3. Blended Threats
Definition
A blended threat combines multiple attack methods in one campaign.
Example
An attacker may:
	• Send phishing email 
	• Deliver malware 
	• Exploit an unpatched system 
	• Use stolen credentials for lateral movement 
Why dangerous
They use both technical and human weaknesses, making them harder to stop.

4. Social Engineering
Definition
Manipulating people into performing actions or disclosing information.
Examples
	• Phishing 
	• Vishing 
	• Smishing 
	• Pretexting 
	• Baiting 
Host impact
Social engineering often leads directly to:
	• Malware execution 
	• Credential theft 
	• Remote access installation 

5. Network File Shares
Explanation
Shared drives and common file repositories can spread threats when infected files are accessed.
Risks
	• Malware propagation 
	• Ransomware encryption of shared files 
	• Exposure of sensitive data 
	• Lateral movement 

6. Internet Downloads
Explanation
Threats can be introduced when users download:
	• Pirated software 
	• Cracked tools 
	• Fake updates 
	• Malicious browser extensions 
	• Trojanized applications 
Risk
Users often execute software without verifying authenticity.

7. Connecting All Slides Together
These slides form one connected host security story:
Step 1: Threat Source
Threat may enter through:
	• Email 
	• Downloads 
	• Unpatched systems 
	• File shares 
	• Social engineering 
Step 2: Initial Host Compromise
Attacker may deploy:
	• Spyware 
	• Trojan 
	• Ransomware 
	• Brute force access 
	• Exploit-based malware 
Step 3: Host Impact
Victim host experiences:
	• Data theft 
	• Resource exhaustion 
	• File encryption 
	• Unauthorized access 
	• Data deletion 
Step 4: Possible Escalation
If not contained, compromise can spread to:
	• Other endpoints 
	• Servers 
	• Domain resources 
	• Shared storage 

8. SOC Analyst Perspective
A SOC analyst should think about these host threats in terms of:
	• Initial access 
	• Execution 
	• Persistence 
	• Privilege escalation 
	• Impact 
Example mapping
	• Brute force attack → unauthorized access 
	• Spyware → credential theft and surveillance 
	• Ransomware → impact and extortion 
	• Host-based DoS → availability issue 
	• Malware infection → execution and persistence 
	• Unpatched host → vulnerability exploitation path 

9. Quick Revision Points
Common host threats
	• Malware infection 
	• Data deletion 
	• Unauthorized access 
Host-based DoS examples
	• Ping of Death 
	• Teardrop 
Brute force
	• Tries many password combinations until success 
Spyware
	• Secretly monitors user activity 
	• Keylogger captures keystrokes 
Ransomware
	• Encrypts data and demands payment 
Threat sources
	• Unpatched systems 
	• Email 
	• Blended threats 
	• Social engineering 
	• File shares 
	• Internet downloads 
	
Why are hosts important in security monitoring?
Because hosts are where attackers often:
	• Execute malware 
	• Steal credentials 
	• Gain persistence 
	• Encrypt files 
	• Use valid accounts to move deeper into the network 
How is brute force detected in a SOC?
By monitoring:
	• Repeated failed logins 
	• Many login attempts from one source 
	• Login success after many failures 
	• Unusual authentication patterns 
Why is ransomware so damaging?
Because it affects:
	• Availability 
	• Confidentiality if data is stolen 
	• Business continuity 
	• Recovery costs 
	• Legal and regulatory obligations 
Why are unpatched systems dangerous?
Because attackers exploit publicly known vulnerabilities faster than organizations patch them.


1. SQL Injection (SQLi) Attacks
Definition
SQL Injection (SQLi) is an attack where an attacker injects malicious SQL queries into input fields to:
	• Bypass authentication 
	• Access, modify, or delete database data 
	• Execute administrative operations 

Why SQLi Happens
Occurs when:
	• Application does not validate user input 
	• User input is directly used in SQL queries 

How SQL Injection Works
Normal Flow
User input → Application → SQL query → Database → Result
Attack Flow
Attacker input → Injected SQL → Query altered → Database executes attacker command

Example Concept
Instead of:

SELECT * FROM users WHERE username='admin' AND password='123'

Attacker inputs:
admin' OR '1'='1

Result:

SELECT * FROM users WHERE username='admin' OR '1'='1'
→ Always TRUE → Login bypass

What Attackers Can Do
	• Bypass authentication 
	• Dump database (usernames, passwords, PII) 
	• Modify/delete records 
	• Execute stored procedures 
	• Gain admin privileges 

Conditions Required
	• Dynamic SQL queries 
	• Poor input validation 
	• No parameterization 

SOC Detection Indicators
	• SQL errors in logs 
	• Suspicious characters: 
		○ ' OR 1=1 
		○ -- 
		○ UNION SELECT 
	• Unusual database queries 
	• Multiple failed login attempts followed by success 

Prevention
	• Prepared statements (parameterized queries) 
	• Input validation & sanitization 
	• Use ORM frameworks 
	• Least privilege database access 
	• WAF (Web Application Firewall) 

2. Cross-Site Scripting (XSS)
Definition
XSS is an attack where malicious scripts are injected into web pages and executed in the user’s browser.

Key Idea
	• SQLi targets server/database 
	• XSS targets user/browser 

How XSS Works
	1. Attacker injects script into web application 
	2. Application stores/displays it 
	3. Victim loads page 
	4. Script executes in victim’s browser 

Types (Important)
1. Stored XSS
	• Stored in database 
	• Executes for every user 
2. Reflected XSS
	• Reflected via URL/input 
	• Immediate execution 
3. DOM-based XSS
	• Client-side script manipulation 

What Attackers Can Do
	• Steal cookies/session IDs 
	• Hijack user sessions 
	• Redirect users 
	• Capture keystrokes 
	• Perform actions as victim 

SOC Indicators
	• Suspicious scripts in URLs: 
		○ <script> 
		○ alert() 
	• Unexpected JavaScript execution 
	• User complaints about redirects 

Prevention
	• Input validation 
	• Output encoding 
	• Content Security Policy (CSP) 
	• Secure cookies (HttpOnly, Secure flags) 

3. Parameter Tampering
Definition
Parameter tampering is:
	• Manipulating parameters exchanged between client and server 

What Can Be Modified
	• Price values 
	• User roles 
	• Account IDs 
	• Quantity of items 
	• Permissions 

Example
Original:

price=100
Tampered:

price=1

Why It Works
	• Lack of server-side validation 
	• Trusting client-side input 

Impact
	• Financial fraud 
	• Privilege escalation 
	• Data manipulation 

SOC Indicators
	• Unexpected parameter values 
	• Abnormal transactions 
	• Inconsistent logs vs UI 

Prevention
	• Validate on server-side 
	• Do not trust client input 
	• Use tokens and integrity checks 
	• Encrypt sensitive parameters 

4. Directory Traversal
Definition
Directory traversal allows attackers to:
	• Access restricted files/directories 
	• Execute commands outside web root 

How It Works
Uses:

../
Example:

../../../etc/passwd

What Attackers Access
	• System files 
	• Configuration files 
	• Password files 
	• Logs 
	• Source code 

Impact
	• Information disclosure 
	• Credential leakage 
	• Full system compromise 

SOC Indicators
	• Requests containing: 
		○ ../ 
		○ %2e%2e%2f 
	• Access to unusual files 
	• Unauthorized file reads 

Prevention
	• Input validation 
	• Restrict file paths 
	• Use whitelisting 
	• Run app with limited privileges 

5. Application-Level DoS Attack
Definition
Application-level DoS targets:
	• Application resources, not just network 

How It Works
	• Sends many resource-intensive requests 
	• Example: 
		○ Database-heavy queries 
		○ Large file requests 

Targets
	• CPU 
	• Memory 
	• Disk 
	• Database bandwidth 
	• Worker processes 

Why Hard to Detect
	• Looks like legitimate traffic 
	• Uses normal request patterns 

Causes of Vulnerability
	• Poor input validation 
	• Inefficient queries 
	• Application bottlenecks 
	• Lack of rate limiting 

SOC Indicators
	• High CPU usage on application 
	• Slow responses 
	• High number of similar requests 
	• Database overload 

Prevention
	• Rate limiting 
	• Load balancing 
	• Input validation 
	• Efficient query design 
	• WAF 

6. Session Attacks

6.1 Session Fixation
Definition
Attacker forces a user to use a known session ID

How It Works
	1. Attacker creates session ID 
	2. Sends it to victim 
	3. Victim logs in 
	4. Same session ID is used 
	5. Attacker hijacks session 

Impact
	• Account takeover 
	• Unauthorized access 

Prevention
	• Regenerate session ID after login 
	• Use secure cookies 
	• Invalidate old sessions 

6.2 Cookie Poisoning
Definition
Modifying cookie data to:
	• Gain unauthorized access 
	• Change user identity 

Key Concepts
	• Cookies store: 
		○ Session IDs 
		○ User data 
	• Attackers modify cookie values 

Risks
	• Session hijacking 
	• Privilege escalation 
	• Identity theft 

Weak Practice Highlighted
	• Encoding cookies (like Base64/ROT13) is NOT secure 
	• Attackers can easily decode them 

Prevention
	• Encrypt cookies 
	• Use secure flags: 
		○ HttpOnly 
		○ Secure 
	• Validate cookie data on server 

7. OWASP Top 10 Web Application Security Risks (2021)
Definition
OWASP Top 10 lists the most critical web application risks

List
	1. Broken Access Control 
	2. Cryptographic Failures 
	3. Injection 
	4. Insecure Design 
	5. Security Misconfiguration 
	6. Vulnerable and Outdated Components 
	7. Identification and Authentication Failures 
	8. Software and Data Integrity Failures 
	9. Security Logging and Monitoring Failures 
	10. Server-Side Request Forgery (SSRF) 

Importance
	• Industry standard 
	• Used in: 
		○ Audits 
		○ Security assessments 
		○ SOC awareness 

8. Social Engineering Attacks (Physical)

1. Dumpster Diving
Definition
Searching trash for sensitive information
Data Found
	• Bills 
	• Contact info 
	• Financial records 
	• Internal documents 

2. Piggybacking
Definition
Authorized person allows unauthorized person to enter
Example
	• Holding door open for someone 

3. Tailgating
Definition
Unauthorized person enters by closely following someone
Key Difference
	• Piggybacking → permission given 
	• Tailgating → no permission 

Impact
	• Physical access to systems 
	• Data theft 
	• Device compromise 

Final Summary (Very Important)
Web Attacks
	• SQL Injection → database attack 
	• XSS → browser attack 
	• Parameter Tampering → data manipulation 
	• Directory Traversal → file access 

Application Attacks
	• App DoS → resource exhaustion 
	• Session Fixation → session hijack 
	• Cookie Poisoning → identity manipulation 

Physical/Social Attacks
	• Dumpster diving 
	• Piggybacking 
	• Tailgating 

SOC Thinking (Critical)
When you see:
	• ' OR 1=1 → SQL Injection 
	• <script> → XSS 
	• ../ → Directory Traversal 
	• Strange parameters → Parameter tampering 
	• Same session ID reused → Session fixation 
	• Modified cookies → Cookie poisoning 
	• High app CPU with normal traffic → App DoS

1. Email Attacks
Email is one of the most common initial attack vectors because it targets the human layer, which is often the weakest link.

1.1 Phishing
Definition
Phishing is a social engineering attack where:
	• An attacker sends a legitimate-looking email 
	• Tricks the victim into: 
		○ Clicking a malicious link 
		○ Entering sensitive information 

Attack Flow
	1. Attacker sends fake email (bank, company, etc.) 
	2. Email contains: 
		○ Malicious link or form 
	3. Victim clicks link 
	4. Redirected to fake website 
	5. Victim enters credentials 
	6. Data is sent to attacker 

Key Characteristics
	• Urgency (e.g., “Your account will be locked”) 
	• Spoofed sender email 
	• Fake login pages 
	• Slightly modified domain names 

Impact
	• Credential theft 
	• Financial fraud 
	• Account takeover 
	• Initial access into organization 

SOC Indicators
	• Emails from suspicious domains 
	• Links with mismatched URLs 
	• Multiple users reporting similar emails 
	• Sudden login attempts after email interaction 

Prevention
	• User awareness training 
	• Email filtering (secure email gateways) 
	• URL inspection 
	• MFA 

1.2 Malicious Email Attachments
Definition
Attackers send malicious files as attachments to deliver malware.

Types of Attachments
	• .exe (executables) 
	• .doc/.docx (macros) 
	• .pdf (embedded scripts) 
	• .zip/.rar (compressed malware) 

Attack Flow
	1. Attacker sends email with attachment 
	2. User downloads and opens it 
	3. Malware executes 
	4. System gets infected 

Impact
	• Malware infection 
	• Ransomware deployment 
	• Backdoor installation 
	• Data theft 

SOC Indicators
	• Unusual attachment types 
	• Macro-enabled files 
	• Suspicious file hashes 
	• Endpoint alerts after opening attachment 

Prevention
	• Disable macros by default 
	• Sandboxing attachments 
	• Endpoint protection 
	• Blocking executable attachments 

1.3 Malicious User Redirection
Definition
User is redirected to a malicious site via:
	• Email links 
	• Multiple redirections 

Attack Flow
	1. User clicks link in email 
	2. Redirect chain begins 
	3. Final destination is malicious site 
	4. User: 
		○ Enters credentials OR 
		○ Downloads malware 

Impact
	• Credential theft 
	• Malware infection 
	• Financial fraud 
	• Network infiltration 

SOC Indicators
	• Multiple HTTP redirects 
	• Suspicious domains 
	• Known malicious URLs 

1.4 Spamming
Definition
Spam refers to:
	• Unsolicited commercial emails 
	• Bulk messages 

Characteristics
	• Often fake or misleading 
	• Sent in large volumes 
	• Found in: 
		○ Emails 
		○ Chat rooms 
		○ Message boards 

Risks
	• Phishing delivery 
	• Malware distribution 
	• Social engineering 

SOC Indicators
	• High email volume from same sender 
	• Repetitive content 
	• Known spam domains 

2. Insider Attacks
Definition
Insider attacks are threats originating from individuals within the organization:
	• Employees 
	• Contractors 
	• Partners 

2.1 Unauthorized Access
Description
Insiders access:
	• Data 
	• Systems 
	• Resources
outside their permitted scope 

Example
	• Employee accessing HR/financial data without authorization 

Impact
	• Data breach 
	• Privacy violations 
	• Compliance issues 

2.2 Malicious Software Installation
Description
Insider installs malware intentionally:
	• Spyware 
	• Keyloggers 
	• Backdoors 

Example
	• Installing keylogger to steal colleague credentials 

Impact
	• Credential theft 
	• Internal compromise 
	• Data exfiltration 

SOC Indicators of Insider Threats
	• Access outside job role 
	• Unusual login times 
	• Data access spikes 
	• Installation of unauthorized software 

3. Indicators of Compromise (IoCs)
Definition
IoCs (Indicators of Compromise) are:
	• Artifacts or evidence that indicate: 
		○ A system has been compromised 
		○ Malicious activity has occurred 

Examples of IoCs
	• IP addresses 
	• File hashes 
	• Domain names 
	• URLs 
	• Registry changes 
	• Log anomalies 

Importance of IoCs
	• Help detect: 
		○ Breaches 
		○ Malware 
		○ Intrusions 
	• Provide: 
		○ Evidence for investigation 
		○ Data for threat intelligence 

SOC Role with IoCs
	• Continuous monitoring 
	• Correlation of IoCs 
	• Incident triage 
	• Threat hunting 

4. Why IoCs Are Important
Key Benefits
1. Detect Threats
	• Identify malware and attacks early 

2. Understand Incidents
	• Answer: 
		○ What happened? 
		○ How did it happen? 

3. Improve Response Time
	• Faster detection → faster response 

4. Improve Detection Rate
	• Better rules and alerts 

5. Enable Automation
	• Feed IoCs into: 
		○ SIEM 
		○ SOAR 

6. Support Investigation
Helps answer:
	• Is file malicious? 
	• Is network compromised? 
	• How did infection occur? 
	• What is history of IP/domain? 

5. Network Attack IoCs
Definition
Indicators related to network-level activity

Examples (from table)
1. Unusual Traffic Patterns
	• Abnormal spikes 
	• Unexpected protocols 

2. Anomalous DNS Requests
	• Requests to suspicious domains 
	• Data exfiltration via DNS 

3. Port Scanning Activity
	• Multiple ports probed 

4. Unexpected Protocol Usage
	• Protocols used abnormally 

5. Command & Control (C2) Traffic
	• Communication with attacker servers 

6. Abnormal ARP Traffic
	• Indicates ARP poisoning 

7. Suspicious VPN Activity
	• Unusual remote access 

8. Unauthorized Devices
	• Unknown devices on network 

9. High Failed Login Attempts
	• Possible brute force 

10. Unusual Lateral Movement
	• Movement across systems 

11. Large Data Transfers
	• Possible data exfiltration 

12. Unusual Port Scanning
	• Scanning for vulnerabilities 

Data Sources
	• Firewall logs 
	• IDS/IPS 
	• NetFlow 
	• Packet capture 
	• SIEM 

6. Host Attack IoCs
Definition
Indicators observed on:
	• Endpoints 
	• Servers 
	• Host systems 

Examples

1. Unusual Processes
	• Unknown or suspicious programs running 

2. Network Activity from Host
	• Unexpected outbound connections 

3. File System Changes
	• New or modified files 
	• Unknown executables 

4. Unauthorized User Accounts
	• New accounts created 

5. Abnormal CPU Usage
	• Crypto mining or malware 

6. Persistence Mechanisms
	• Registry changes 
	• Startup entries 

7. Memory Modifications
	• Code injection 

8. Log Deletion
	• Attempt to hide activity 

9. Remote Access Tools
	• Unauthorized RATs 

10. Privilege Escalation Attempts
	• Exploiting vulnerabilities 

11. Suspicious Logs
	• Authentication anomalies 

12. Malware Artifacts
	• Indicators from forensic analysis 

Data Sources
	• Endpoint logs 
	• EDR tools 
	• Antivirus logs 
	• System logs 
	• Application logs 

Final Summary (Very Important)
Email Attacks
	• Phishing → credential theft 
	• Attachments → malware 
	• Redirection → fake sites 
	• Spam → delivery mechanism 

Insider Threats
	• Unauthorized access 
	• Malware installation 

IoCs
	• Evidence of compromise 
	• Used for detection and investigation 

Network IoCs
	• Traffic anomalies 
	• DNS issues 
	• C2 communication 
	• Port scanning 

Host IoCs
	• Suspicious processes 
	• File changes 
	• Persistence 
	• Privilege escalation


1. Application Attack IoCs
Definition
Application IoCs are indicators found by analyzing:
	• Web applications 
	• APIs 
	• Backend systems 
They indicate:
	• Exploitation attempts 
	• Misuse of application logic 

Key Application IoCs
1. Unusual API Requests
	• Abnormal or unauthorized API calls 
	• May indicate: 
		○ API abuse 
		○ Broken authentication 
		○ Injection attempts 

2. Abnormal Traffic Patterns
	• Sudden spikes 
	• Resource-heavy requests 
	• May indicate: 
		○ Application DoS 
		○ Bot activity 

3. Unauthorized Access Attempts
	• Access to restricted endpoints 
	• Example: 
		○ /admin, /config 

4. Injected Code or Scripts
	• SQL injection 
	• XSS payloads 

5. Unauthorized Changes
	• Data modifications without authorization 

6. Failed Login Attempts
	• Brute force attacks 

7. Unusual Authentication Events
	• Logins from: 
		○ Different geolocation 
		○ Unknown devices 

8. Unexpected Data Exfiltration
	• Large data downloads 

9. Kernel Exploit Paths
	• Rare but indicates deep compromise 

10. Malformed Requests
	• Broken syntax 
	• Invalid parameters 

Data Sources
	• Application logs 
	• API gateway logs 
	• SIEM 
	• WAF logs 

2. Social Engineering IoCs
Definition
Indicators derived from:
	• Human behavior 
	• Psychological manipulation patterns 

Key IoCs
	• Phishing emails 
	• Fake domains 
	• Urgent requests 
	• Suspicious phone calls (vishing) 
	• SMS scams (smishing) 
	• Fake job offers 
	• Fake IT support requests 

Behavioral Indicators
	• Employees sharing sensitive info 
	• Clicking suspicious links 
	• Downloading unknown files 
	• Trusting unverified sources 

Data Sources
	• Email logs 
	• User reports 
	• Training platforms 
	• SOC alerts 

3. Email Attack IoCs
Key Indicators

1. Suspicious Email Attachments
	• Malware payloads 

2. Phishing Emails
	• Fake sender 
	• Credential harvesting links 

3. Email Spoofing
	• Forged sender addresses 

4. Malicious URLs
	• Hidden or obfuscated links 

5. Unusual Sending Patterns
	• Bulk emails 
	• Mass campaigns 

6. Forwarding Rules
	• Automatic forwarding (possible compromise) 

7. Embedded Executables
	• Dangerous attachments 

8. Domain Impersonation
	• Look-alike domains 

Data Sources
	• Email gateways 
	• Secure email tools 
	• SIEM 

4. Insider Attack IoCs
Behavioral Indicators

1. Unauthorized Data Access
	• Access outside job role 

2. Data Exfiltration
	• Copying sensitive data 

3. Suspicious Account Usage
	• Access from unusual locations 

4. Abnormal System Activity
	• Unexpected changes 

5. Privilege Misuse
	• Admin actions without reason 

6. Frequent USB Usage
	• Data copying to external devices 

7. Creation of Unauthorized Accounts
	• Backdoor access 

8. High Data Access Requests
	• Bulk downloads 

Data Sources
	• Access logs 
	• DLP tools 
	• Endpoint monitoring 
	• User activity monitoring 

5. Lockheed Martin Cyber Kill Chain
Definition
A model that describes stages of a cyberattack

7 Phases

1. Reconnaissance
	• Gather information about target 

2. Weaponization
	• Create malware/exploit 

3. Delivery
	• Send payload (email, USB, etc.) 

4. Exploitation
	• Execute exploit 

5. Installation
	• Install malware 

6. Command and Control (C2)
	• Establish communication channel 

7. Actions on Objectives
	• Data theft 
	• System control 

Importance
	• Helps SOC: 
		○ Detect early stages 
		○ Break attack chain 

6. MITRE ATT&CK Framework
Definition
A knowledge base of attacker behavior (TTPs)

Purpose
	• Standardize threat detection 
	• Map attacks to techniques 
	• Improve threat hunting 

Structure
	• Tactics (high-level goals) 
	• Techniques (methods) 
	• Procedures (implementation) 

Example Tactics
	• Initial Access 
	• Execution 
	• Persistence 
	• Privilege Escalation 
	• Defense Evasion 
	• Credential Access 
	• Lateral Movement 
	• Exfiltration 

Importance
	• Used in: 
		○ SOC detection rules 
		○ Threat intelligence 
		○ Incident response 

7. Unified Kill Chain
Definition
Combines:
	• Cyber Kill Chain 
	• MITRE ATT&CK 

Phases
IN Phase
	• Reconnaissance 
	• Resource development 
	• Delivery 

THROUGH Phase
	• Execution 
	• Persistence 
	• Lateral movement 
	• Privilege escalation 

OUT Phase
	• Data exfiltration 
	• Impact 
	• Objectives achieved 

Benefit
	• More detailed than traditional kill chain 
	• Covers full attack lifecycle 

8. MITRE D3FEND Framework
Definition
A framework focused on:
	• Defensive techniques 

Purpose
	• Map defenses to attacks 
	• Improve detection and mitigation 

Stages
	1. Model 
	2. Harden 
	3. Detect 
	4. Isolate 
	5. Deceive 
	6. Evict 
	7. Restore 

Mapping
	• Works alongside MITRE ATT&CK 
	• Helps answer: 
		○ “How do we defend this attack?” 

9. Diamond Model of Intrusion Analysis
Definition
A model for analyzing attacks using four core elements

Elements
1. Adversary
	• Who performed the attack 

2. Victim
	• Target of attack 

3. Capability
	• Tools/malware used 

4. Infrastructure
	• Systems used by attacker (IP, domains) 

Purpose
	• Understand relationships 
	• Improve threat intelligence 
	• Link events together 

10. Kill Chain Scenario – Spear Phishing
Attack Mapping

Reconnaissance
	• Gather employee details 

Weaponization
	• Create malicious attachment 

Delivery
	• Send phishing email 

Exploitation
	• User opens attachment 

Installation
	• Malware installed 

Command & Control
	• Connect to attacker server 

Actions on Objectives
	• Data theft 
	• Lateral movement 

SOC Use Cases
	• Detect suspicious attachments 
	• Monitor execution of unknown programs 
	• Detect outbound connections 
	• Identify credential misuse 

11. Gaining TTP Knowledge via Hacker Forums
Purpose
Attackers share:
	• Techniques 
	• Tools 
	• Exploits 
	• Evasion methods 

Examples Mentioned
	• Hackaday 
	• Ethical Hacker Network 
	• Hack This Site 
	• Hack Forums 
	• Evil Zone 

SOC Relevance
	• Threat intelligence gathering 
	• Early warning of new attacks 
	• Understanding attacker behavior 

12. NIST Cybersecurity Framework 2.0
Definition
A standardized framework for managing cybersecurity risk

Core Functions

1. Govern
	• Risk management 
	• Policies 

2. Identify
	• Assets 
	• Risks 
	• Vulnerabilities 

3. Protect
	• Safeguards 
	• Controls 

4. Detect
	• Identify incidents 

5. Respond
	• Handle incidents 

6. Recover
	• Restore systems 

Importance
	• Widely used globally 
	• Aligns with SOC operations 
	• Helps build security strategy 

Final Big Picture (VERY IMPORTANT)
Full SOC Understanding
Attack Side
	• TTPs → MITRE ATT&CK 
	• Kill Chain → Attack stages 
	• APT → Advanced attacks 

Detection Side
	• IoCs: 
		○ Network 
		○ Host 
		○ Application 
		○ Email 
		○ Insider 

Defense Side
	• MITRE D3FEND 
	• NIST Framework 

Analysis Side
	• Diamond Model

