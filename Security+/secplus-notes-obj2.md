Domain 2 – Threats, Vulnerabilities, and Mitigations (22%)

This domain focuses on understanding attackers, vulnerabilities, attack techniques, indicators of compromise, and security mitigation methods used to protect enterprise systems.

2.1 Compare and Contrast Common Threat Actors and Motivations
Threat Actors
Nation-State

Government-sponsored attackers conducting cyber operations for espionage, warfare, or intelligence gathering.
They usually have large resources, advanced tools, and skilled teams.

Example:

Cyber warfare operations

Intelligence gathering from other governments

Unskilled Attacker (Script Kiddie)

An individual with little technical knowledge who uses pre-built tools or scripts to perform attacks.

Characteristics:

Low skill level

Uses automated tools

Limited understanding of exploits

Example:

Downloading hacking tools and attacking websites.

Hacktivist

Attackers motivated by political or ideological beliefs.

Common targets:

Governments

Corporations

Political organizations

Common activities:

Website defacement

Data leaks

DDoS attacks

Insider Threat

An employee, contractor, or partner with authorized access who intentionally or unintentionally causes harm.

Types:

Malicious insider
An employee deliberately stealing or damaging data.

Negligent insider
An employee who accidentally exposes sensitive data.

Compromised insider
An employee account taken over by attackers.

Organized Crime

Cybercriminal groups performing attacks for financial gain.

Activities include:

Ransomware campaigns

Identity theft

Credit card fraud

Data selling on dark web

Shadow IT

Technology systems, applications, or services used without approval from the IT department.

Examples:

Personal cloud storage

Unauthorized SaaS tools

Unapproved devices

Shadow IT increases security risk because IT cannot monitor or secure these systems.

Attributes of Threat Actors
Internal vs External

Internal actors
Employees or insiders with system access.

External actors
Attackers outside the organization attempting unauthorized access.

Resources / Funding

Attackers differ in their available resources:

Low resources
Script kiddies.

Moderate resources
Hacktivists.

High resources
Nation-state attackers.

Level of Sophistication

Sophistication refers to the technical expertise and complexity of attacks.

Low sophistication
Automated attacks.

High sophistication
Advanced Persistent Threats (APT).

Threat Actor Motivations
Data Exfiltration

Stealing sensitive data such as:

Intellectual property

Personal data

Financial information

Espionage

Stealing confidential information for political or strategic advantage.

Service Disruption

Interrupting system operations such as:

Websites

Online services

Corporate networks

Example: DDoS attacks.

Blackmail

Threatening to release stolen data unless payment is made.

Example:
Ransomware attacks.

Financial Gain

Attackers seek profit through:

Fraud

Cryptocurrency theft

Data resale

Philosophical or Political Beliefs

Hacktivists attacking organizations they oppose.

Ethical Motivation

Security researchers who test systems to improve security.

Revenge

Disgruntled employees seeking retaliation.

Disruption / Chaos

Attackers aiming to create instability or damage.

War (Cyber Warfare)

Government-backed cyber operations during geopolitical conflict.

2.2 Explain Common Threat Vectors and Attack Surfaces

A threat vector is the path attackers use to gain access to systems.

An attack surface is the total number of possible entry points in a system.

Message-Based Threat Vectors
Email

Most common attack vector.

Examples:

Phishing emails

Malware attachments

Malicious links

Short Message Service (SMS)

SMS-based attacks called smishing.

Example:

Fake banking messages requesting login credentials.

Instant Messaging (IM)

Malicious links sent via:

Slack

Teams

WhatsApp

Telegram

Image-Based Threats

Malicious payloads hidden inside image files.

Example:

Steganography hiding malware inside images.

File-Based Threats

Attackers distribute malicious files such as:

PDFs

Word documents

Executables

Often used in malware campaigns.

Voice Call Attacks

Voice phishing known as vishing.

Example:

Attacker impersonating bank support.

Removable Device Attacks

Malware delivered through devices such as:

USB drives

External hard drives

Example:
USB drop attacks.

Vulnerable Software

Software flaws that attackers exploit.

Types:

Client-based attacks
Target software on user devices.

Agentless attacks
Exploit systems remotely without installed agents.

Unsupported Systems

Systems no longer receiving security updates.

Example:

End-of-life operating systems

Outdated applications

Unsecure Networks
Wireless

Weak Wi-Fi security configurations.

Wired

Unsecured internal networks.

Bluetooth

Short-range wireless attacks.

Example:
Bluejacking or Bluesnarfing.

Open Service Ports

Unused open ports that attackers exploit.

Example:

Port scanning to find vulnerabilities.

Default Credentials

Devices shipped with default usernames and passwords.

Example:

admin / admin

Supply Chain Attacks

Attacks targeting vendors to compromise organizations.

Examples:

Managed Service Providers (MSP)

Vendors

Hardware suppliers

Software providers

Human Vectors (Social Engineering)
Phishing

Fraudulent emails tricking users into revealing information.

Vishing

Voice-based phishing attacks.

Smishing

SMS phishing attacks.

Misinformation / Disinformation

False information designed to manipulate people.

Impersonation

Pretending to be someone else.

Example:
IT support impersonation.

Business Email Compromise (BEC)

Attack targeting corporate email accounts.

Example:
Fake CEO requesting urgent money transfer.

Pretexting

Creating a fabricated scenario to obtain information.

Watering Hole Attack

Compromising websites frequently visited by the target.

Brand Impersonation

Fake websites mimicking legitimate brands.

Typosquatting

Using misspelled domain names to trick users.

Example:

amaz0n.com

2.3 Explain Various Types of Vulnerabilities

A vulnerability is a weakness that attackers can exploit.

Application Vulnerabilities
Memory Injection

Malicious code injected into application memory.

Buffer Overflow

Occurs when data exceeds allocated memory buffer.

Allows attackers to execute malicious code.

Race Conditions

Security issues caused by improper timing of processes.

Types:

Time-of-check (TOC)

Time-of-use (TOU)

Malicious Update

Compromised software update delivering malware.

Operating System Vulnerabilities

Security flaws in OS components.

Examples:

Kernel vulnerabilities

Privilege escalation bugs

Web-Based Vulnerabilities
SQL Injection (SQLi)

Injecting malicious SQL commands into database queries.

Cross-Site Scripting (XSS)

Injecting malicious scripts into web pages.

Hardware Vulnerabilities

Weaknesses in physical hardware.

Examples:

Firmware vulnerabilities

End-of-life hardware

Legacy systems

Virtualization Vulnerabilities
VM Escape

Attack escaping virtual machine isolation.

Resource Reuse

Improper reuse of memory or storage between VMs.

Cloud-Specific Vulnerabilities

Misconfigured cloud services.

Example:

Public cloud storage buckets.

Supply Chain Vulnerabilities

Security weaknesses in vendors or suppliers.

Cryptographic Vulnerabilities

Weak encryption algorithms.

Poor key management.

Misconfiguration

Incorrect system settings exposing vulnerabilities.

Example:

Open ports or weak firewall rules.

Mobile Device Vulnerabilities
Side Loading

Installing apps outside official app stores.

Jailbreaking

Removing manufacturer security restrictions.

Zero-Day Vulnerability

Previously unknown vulnerability exploited before patches exist.

2.4 Analyze Indicators of Malicious Activity

Indicators of compromise (IoCs) help detect attacks.

Malware Attacks
Ransomware

Encrypts files and demands payment.

Trojan

Malware disguised as legitimate software.

Worm

Self-replicating malware spreading across networks.

Spyware

Software secretly monitoring user activity.

Bloatware

Unwanted software consuming system resources.

Virus

Malware attaching to legitimate files.

Keylogger

Records user keystrokes.

Logic Bomb

Malicious code triggered by conditions.

Rootkit

Malware hiding attacker presence.

Physical Attacks

Brute force attacks

RFID cloning

Environmental attacks

Network Attacks

Distributed Denial-of-Service (DDoS)

Amplified attacks

Reflected attacks

DNS attacks

Wireless attacks

On-path attacks (Man-in-the-Middle)

Credential replay attacks

Malicious code attacks

Application Attacks

Injection attacks

Buffer overflow

Replay attacks

Privilege escalation

Forgery

Directory traversal

Cryptographic Attacks

Downgrade attacks

Collision attacks

Birthday attacks

Password Attacks

Password spraying

Brute force attacks

Indicators of Compromise

Account lockouts

Concurrent session usage

Blocked content

Impossible travel

Resource consumption spikes

Resource inaccessibility

Out-of-cycle logging

Published or documented vulnerabilities

Missing logs

2.5 Mitigation Techniques

Mitigation techniques reduce security risks.

Segmentation

Dividing networks into isolated segments.

Limits lateral movement of attackers.

Access Control

Restricting system access based on policies.

Access Control Lists (ACL)

Rules controlling network traffic.

Permissions

User privileges determining allowed actions.

Application Allow List

Only approved applications are allowed to run.

Isolation

Separating systems from networks.

Example:

Quarantining infected machines.

Patching

Applying updates to fix vulnerabilities.

Encryption

Protecting data confidentiality using cryptographic methods.

Monitoring

Continuous monitoring of systems and networks.

Least Privilege

Users receive the minimum access required.

Configuration Enforcement

Maintaining secure system configurations.

Decommissioning

Securely removing outdated systems from service.

Hardening Techniques

Encryption

Endpoint protection

Host-based firewall

Host-based intrusion prevention system (HIPS)

Disabling unnecessary ports and protocols

Changing default passwords

Removing unnecessary software
