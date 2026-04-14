Network+ Notes – Domain 4: Network Security
🛡️ 4.1 Basic Network Security Concepts
🔹 Logical Security
🔸 Encryption
Encryption
📌 Purpose:

Protects data from unauthorized access

✅ Data in Transit
Data moving across network
Protected using TLS, VPN, HTTPS
✅ Data at Rest
Stored data (disk, database)
Protected using disk encryption
🔹 Certificates
Public Key Infrastructure
📌 PKI:

Framework for managing certificates

🔸 Self-Signed Certificates
Created by user
Not trusted publicly
🔹 Identity & Access Management (IAM)
Identity and Access Management
🔸 Authentication (Who you are)
✅ MFA (Multi-Factor Authentication)
Password + OTP + biometrics
✅ SSO (Single Sign-On)
One login → multiple services
🔸 RADIUS
Centralized authentication
🔸 LDAP
Directory-based authentication
🔸 SAML
Used in web SSO
🔸 TACACS+
More secure than RADIUS
✅ Time-based authentication
OTP expires after time
🔸 Authorization (What you can access)
✅ Least Privilege
Minimum access needed
✅ RBAC (Role-Based Access Control)
Access based on role
🔸 Geofencing
Restrict access based on location
🔹 Physical Security
Cameras → Surveillance
Locks → Restrict physical access
🎭 Deception Technologies
🔸 Honeypot
Fake system to attract attackers
🔸 Honeynet
Network of honeypots
🔹 Common Security Terms
Term	Meaning
Risk	Potential loss
Vulnerability	Weakness
Threat	Possible danger
Exploit	Attack method
🔹 CIA Triad
CIA Triad
Confidentiality → Privacy
Integrity → Data accuracy
Availability → Access when needed
🔹 Compliance & Audits
🔸 Data Locality
Data must stay in specific region
🔸 PCI DSS
Secures credit card data
🔸 GDPR
Protects user data privacy
🔹 Network Segmentation Enforcement
IoT / IIoT → Smart devices
SCADA / ICS / OT → Industrial systems
Guest networks → Isolated
BYOD → Personal devices

👉 Segmentation reduces attack spread

💥 4.2 Network Attacks
🔹 DoS / DDoS
Distributed Denial of Service
Overwhelms system with traffic
🔹 VLAN Hopping
Access other VLANs illegally
🔹 MAC Flooding
Fills switch MAC table → causes broadcast
🔹 ARP Attacks
🔸 ARP Poisoning
🔸 ARP Spoofing
Redirects traffic to attacker
🔹 DNS Attacks
🔸 DNS Poisoning
🔸 DNS Spoofing
Redirects to fake websites
🔹 Rogue Devices
Rogue DHCP → Gives wrong IP
Rogue AP → Fake Wi-Fi
🔹 Evil Twin
Fake Wi-Fi mimicking real network
🔹 On-Path Attack (MITM)
Attacker sits between communication
🔹 Social Engineering
Phishing → Fake emails
Dumpster diving → Trash data
Shoulder surfing → Watching screen
Tailgating → Following into secure area
🔹 Malware
Virus, worm, ransomware
🛡️ 4.3 Security Controls & Defense
🔹 Device Hardening
Disable unused ports
Change default passwords
🔹 Network Access Control (NAC)
🔸 Port Security
Limits MAC addresses per port
🔸 IEEE 802.1X
Authenticates devices before access
🔸 MAC Filtering
Allows specific devices only
🔹 Key Management
Handles encryption keys securely
🔹 Security Rules
🔸 ACL (Access Control List)
Access Control List
Filters traffic based on rules
🔸 URL Filtering
Blocks malicious websites
🔸 Content Filtering
Controls web access
🔹 Network Zones
🔸 Trusted vs Untrusted
Internal vs external network
🔸 Screened Subnet (DMZ)
Demilitarized Zone
Isolated zone for public servers
🧠 FINAL SUMMARY
Area	Key Idea
Encryption	Protect data
IAM	Control access
Attacks	DDoS, ARP, DNS
Defense	ACL, NAC, hardening
Compliance	GDPR, PCI DSS
