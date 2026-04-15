# Network+ Notes — Domain 4.0: Network Security

---

## 4.1 Basic Network Security Concepts

### The CIA Triad

**Definition:** The CIA Triad is the foundational model of information security. Every security control, policy, and technology is designed to protect one or more of its three core principles.

| Principle | Definition |
|---|---|
| Confidentiality | Ensuring that data is accessible only to authorized individuals and is protected from unauthorized disclosure |
| Integrity | Ensuring that data remains accurate, consistent, and unmodified except through authorized processes |
| Availability | Ensuring that systems, services, and data are accessible to authorized users when needed |

---

### Encryption

**Definition:** Encryption is the process of converting readable data (plaintext) into an unreadable format (ciphertext) using a cryptographic algorithm and key, so that only authorized parties with the correct key can decode it.

| State | Definition | Common Technologies |
|---|---|---|
| Data in Transit | Data actively moving across a network between two endpoints | TLS (HTTPS), VPN (IPSec, SSL), SSH |
| Data at Rest | Data stored on a disk, database, or storage device | Full-disk encryption (BitLocker, FileVault), database encryption |
| Data in Use | Data actively being processed in memory by a running application | Secure enclaves, memory encryption |

---

### Public Key Infrastructure (PKI) and Certificates

**Definition:** PKI is a framework of policies, procedures, hardware, and software used to create, manage, distribute, store, and revoke digital certificates. It enables secure, authenticated communication using asymmetric cryptography.

| Component | Definition |
|---|---|
| Certificate Authority (CA) | A trusted entity that issues and signs digital certificates, vouching for the identity of the certificate holder |
| Digital Certificate | An electronic document that binds a public key to an entity's identity, signed by a CA to prove its authenticity |
| Self-Signed Certificate | A certificate signed by the entity that created it rather than a trusted CA; not trusted by browsers or operating systems by default, but usable in internal or testing environments |
| Certificate Revocation List (CRL) | A list published by a CA of certificates that have been revoked before their expiration date |
| OCSP (Online Certificate Status Protocol) | A real-time protocol that allows clients to check whether a specific certificate has been revoked, as an alternative to downloading the full CRL |

---

### Identity and Access Management (IAM)

**Definition:** IAM is the discipline of managing who can access network resources, what they are allowed to do, and how their identity is verified. It is divided into two functions: authentication and authorization.

---

#### Authentication — Verifying Identity

**Definition:** Authentication is the process of confirming that a user, device, or system is who or what it claims to be.

| Technology | Definition |
|---|---|
| MFA (Multi-Factor Authentication) | Requires two or more independent factors to authenticate: something you know (password), something you have (OTP token), or something you are (biometric) |
| SSO (Single Sign-On) | Allows a user to authenticate once and gain access to multiple applications or services without re-entering credentials for each one |
| RADIUS (Remote Authentication Dial-In User Service) | A centralized AAA (Authentication, Authorization, Accounting) protocol that validates credentials for network access; commonly used with 802.1X and VPNs |
| TACACS+ (Terminal Access Controller Access-Control System Plus) | A Cisco-developed AAA protocol that separates authentication, authorization, and accounting into independent functions, providing more granular control than RADIUS; encrypts the entire payload |
| LDAP (Lightweight Directory Access Protocol) | A protocol used to query and authenticate against directory services such as Microsoft Active Directory |
| SAML (Security Assertion Markup Language) | An XML-based standard used to exchange authentication and authorization data between an identity provider (IdP) and a service provider; commonly used for web-based SSO |
| Time-Based OTP (TOTP) | A one-time password generated from a shared secret and the current time; valid for a short window (typically 30 seconds) before expiring |

---

#### Authorization — Controlling Access

**Definition:** Authorization determines what an authenticated user or device is permitted to do or access within a system.

| Concept | Definition |
|---|---|
| Least Privilege | A security principle stating that users and systems should be granted only the minimum permissions required to perform their specific function, reducing the potential damage from a compromised account |
| RBAC (Role-Based Access Control) | Access permissions are assigned to roles (e.g., Network Admin, Help Desk) rather than individual users; users are granted access by being assigned to a role |
| Geofencing | A location-based access control mechanism that restricts or triggers access based on whether a device is within a defined geographic boundary |

---

### Physical Security

**Definition:** Physical security refers to measures that prevent unauthorized physical access to network equipment, facilities, and data.

| Control | Description |
|---|---|
| Cameras (CCTV) | Provide continuous surveillance of sensitive areas; serve as both a deterrent and a means of investigating incidents after the fact |
| Locks | Prevent unauthorized physical access to network rooms, racks, and equipment; includes keyed locks, badge readers, and combination locks |
| Badge / Access Control Systems | Require identity verification before granting physical entry to secure areas; create an audit trail of access events |
| Biometric Controls | Use physical characteristics (fingerprint, retina, face) to authenticate individuals before granting physical access |

---

### Deception Technologies

| Technology | Definition |
|---|---|
| Honeypot | A deliberately vulnerable decoy system designed to attract and trap attackers; provides early warning of intrusion attempts and allows analysis of attacker techniques without risk to production systems |
| Honeynet | A network of multiple honeypot systems designed to simulate an entire network environment, providing broader deception coverage and more detailed intelligence on attacker behavior |

---

### Common Security Terminology

| Term | Definition |
|---|---|
| Risk | The potential for loss or damage when a threat exploits a vulnerability; typically expressed as the likelihood of an event multiplied by its impact |
| Vulnerability | A weakness in a system, application, configuration, or process that could be exploited by a threat actor |
| Threat | Any potential event or actor that could exploit a vulnerability and cause harm to a system or organization |
| Exploit | A specific technique, tool, or piece of code used to take advantage of a vulnerability |
| Attack Surface | The total set of points on a system or network where an attacker could attempt to gain unauthorized access |

---

### Compliance and Regulatory Frameworks

| Framework | Description |
|---|---|
| PCI DSS (Payment Card Industry Data Security Standard) | A set of security requirements for organizations that handle credit card data, mandating controls such as encryption, access control, and regular security testing |
| GDPR (General Data Protection Regulation) | A European Union regulation that governs how personal data of EU residents is collected, stored, processed, and shared; imposes strict requirements and significant fines for non-compliance |
| Data Locality | A regulatory requirement that certain types of data must be stored and processed within a specific geographic region or country to comply with local laws |

---

### Network Segmentation

**Definition:** Network segmentation is the practice of dividing a network into smaller, isolated zones to limit the lateral movement of attackers, contain breaches, and apply tailored security policies to different device types.

| Segment Type | Description |
|---|---|
| IoT / IIoT | Internet of Things devices (smart sensors, cameras, building systems) are isolated because they often run outdated firmware and cannot support security agents |
| SCADA / ICS / OT | Industrial Control Systems and Operational Technology networks control physical infrastructure (power grids, manufacturing); they require strict isolation from IT networks due to safety and availability requirements |
| Guest Network | An isolated wireless network that provides internet access to visitors without any connectivity to internal corporate resources |
| BYOD (Bring Your Own Device) | Personal employee devices placed in a dedicated segment to prevent unmanaged devices from directly accessing sensitive internal systems |

---

## 4.2 Network Attacks

### Denial of Service Attacks

| Attack | Definition |
|---|---|
| DoS (Denial of Service) | An attack from a single source that floods a target system with traffic or requests, overwhelming it and preventing it from serving legitimate users |
| DDoS (Distributed Denial of Service) | A coordinated DoS attack launched simultaneously from a large number of compromised systems (a botnet), making it far more difficult to filter or stop |
| Amplification Attack | An attacker exploits a protocol (e.g., DNS, NTP) that returns a much larger response than the request, using spoofed source IPs to direct amplified traffic at the victim |

---

### Layer 2 Attacks

| Attack | Definition |
|---|---|
| VLAN Hopping | An attacker manipulates 802.1Q tagging or exploits the switch's native VLAN configuration to send traffic into VLANs they should not have access to; prevented by disabling DTP and explicitly assigning native VLANs |
| MAC Flooding | An attacker sends thousands of frames with fake source MAC addresses to overwhelm the switch's MAC address table. When the table is full, the switch fails open and broadcasts all frames to every port, enabling the attacker to intercept traffic |
| MAC Spoofing | An attacker changes their device's MAC address to impersonate a trusted device, bypassing MAC-based access controls |

---

### ARP Attacks

| Attack | Definition |
|---|---|
| ARP Poisoning / Spoofing | An attacker sends unsolicited ARP replies that associate their MAC address with a legitimate IP address (such as the default gateway). Devices update their ARP cache with the false mapping, causing traffic to be redirected to the attacker |

**Mitigation:** Dynamic ARP Inspection (DAI) on managed switches validates ARP packets against the DHCP snooping binding table.

---

### DNS Attacks

| Attack | Definition |
|---|---|
| DNS Poisoning / Spoofing | An attacker injects fraudulent DNS records into a resolver's cache, causing users to be directed to malicious IP addresses when querying legitimate domain names |
| DNS Hijacking | An attacker modifies DNS settings on a router or host to redirect all DNS queries through a malicious server under their control |

**Mitigation:** DNSSEC, DoH, DoT, and monitoring for unusual DNS query patterns.

---

### Rogue Device Attacks

| Attack | Definition |
|---|---|
| Rogue DHCP Server | An unauthorized DHCP server on the network that responds to client requests and issues incorrect IP configuration — including a malicious default gateway — redirecting all client traffic through an attacker-controlled device |
| Rogue Access Point | An unauthorized wireless AP connected to the network, allowing attackers to bypass wired security controls and gain network access |
| Evil Twin | A rogue AP that broadcasts the same SSID as a legitimate network to trick clients into connecting to it, enabling credential theft and traffic interception |

**Mitigation:** DHCP snooping (blocks unauthorized DHCP servers), wireless intrusion detection systems (WIDS), 802.1X port authentication.

---

### On-Path Attack (Man-in-the-Middle)

**Definition:** An on-path attack (formerly called a Man-in-the-Middle or MITM attack) occurs when an attacker secretly positions themselves between two communicating parties, intercepting and potentially modifying all traffic without either party's knowledge. ARP spoofing and DNS poisoning are common methods used to establish an on-path position.

---

### Social Engineering Attacks

| Attack | Definition |
|---|---|
| Phishing | A fraudulent email or message designed to trick recipients into revealing credentials, clicking malicious links, or downloading malware by impersonating a trusted entity |
| Spear Phishing | A targeted phishing attack customized with personal details about a specific individual or organization to increase its credibility |
| Dumpster Diving | Searching through discarded documents and equipment to find sensitive information such as passwords, network diagrams, or account details |
| Shoulder Surfing | Observing someone entering sensitive information (passwords, PINs) by looking over their shoulder in a physical location |
| Tailgating / Piggybacking | Gaining unauthorized physical access to a secured area by following an authorized person through a door before it closes |

---

### Malware Types

| Type | Definition |
|---|---|
| Virus | Malicious code that attaches itself to legitimate files or programs and spreads when those files are executed |
| Worm | Self-replicating malware that spreads across networks automatically without requiring user interaction or a host file |
| Ransomware | Malware that encrypts a victim's files and demands payment (ransom) in exchange for the decryption key |
| Trojan | Malware disguised as legitimate software that tricks users into installing it, then performs malicious actions in the background |
| Spyware | Software that secretly monitors and collects user activity, keystrokes, and credentials without the user's knowledge |

---

## 4.3 Security Controls and Defense

### Device Hardening

**Definition:** Device hardening is the process of reducing the attack surface of a network device by eliminating unnecessary services, enforcing secure configurations, and applying security best practices before deployment.

| Action | Description |
|---|---|
| Disable unused ports and services | Every open port or running service is a potential attack vector; disabling what is not needed minimizes exposure |
| Change default credentials | Manufacturers ship devices with well-known default usernames and passwords that attackers routinely attempt; these must be changed immediately |
| Apply firmware and software patches | Keeps devices protected against known vulnerabilities |
| Disable unneeded protocols | Remove legacy or insecure protocols such as Telnet, SNMPv1/v2c, and HTTP in favor of their secure equivalents |
| Enable logging | Configure devices to send logs to a syslog server or SIEM for audit and anomaly detection |

---

### Network Access Control (NAC)

**Definition:** NAC is a security approach that enforces policy-based access control at the point where devices connect to the network, ensuring only authorized and compliant devices can gain access.

| Technology | Definition |
|---|---|
| Port Security | A Layer 2 switch feature that restricts the number of MAC addresses allowed on a port and can shut down a port or drop frames if an unauthorized device connects |
| IEEE 802.1X | A port-based Network Access Control standard that requires devices to authenticate to a RADIUS server before being granted network access; unauthenticated devices are placed in a restricted VLAN or denied access entirely |
| MAC Filtering | A basic access control mechanism that allows only pre-approved MAC addresses to connect to a port or wireless network; not considered strong security on its own as MAC addresses can be spoofed |
| Posture Assessment | A NAC feature that evaluates whether a connecting device meets security requirements (e.g., up-to-date antivirus, current OS patches) before granting full network access |

---

### Key Management

**Definition:** Key management encompasses the processes and systems used to generate, distribute, store, rotate, and revoke cryptographic keys. Poor key management is one of the most common causes of encryption failures.

| Practice | Description |
|---|---|
| Key rotation | Regularly replacing encryption keys to limit the exposure window if a key is compromised |
| Key escrow | Storing a copy of encryption keys with a trusted third party for recovery purposes |
| Hardware Security Module (HSM) | A dedicated physical device that securely generates, stores, and manages cryptographic keys, preventing key extraction even by administrators |

---

### Traffic Filtering and Access Control

| Control | Definition |
|---|---|
| ACL (Access Control List) | An ordered list of permit and deny rules applied to a router interface or firewall that controls which traffic is allowed to pass based on source/destination IP, protocol, and port |
| URL Filtering | A security control that inspects web requests and blocks access to URLs categorized as malicious, inappropriate, or against policy |
| Content Filtering | Inspects the content of network traffic (web pages, email, file downloads) and blocks material that violates organizational policy or contains threats |

---

### Network Zones and Segmentation

| Zone | Definition |
|---|---|
| Trusted Zone | The internal corporate network where devices and users are considered authorized and subject to internal security policies |
| Untrusted Zone | Any external network, including the internet, where traffic is assumed to be potentially hostile and must be inspected before being permitted inward |
| Screened Subnet (DMZ — Demilitarized Zone) | An isolated network segment positioned between the trusted internal network and the untrusted internet. Public-facing servers (web, email, DNS) are placed here so that if they are compromised, the attacker cannot directly reach internal systems. Typically implemented with two firewalls: one between the internet and the DMZ, and one between the DMZ and the internal network |

---

### Firewall Types

| Type | Description |
|---|---|
| Packet Filtering Firewall | Inspects individual packets based on source/destination IP, protocol, and port; stateless and does not track connection state |
| Stateful Inspection Firewall | Tracks the state of active connections and only permits packets that are part of an established, legitimate session |
| Next-Generation Firewall (NGFW) | Combines traditional stateful inspection with deep packet inspection (DPI), application awareness, intrusion prevention, and user identity-based policies |
| Web Application Firewall (WAF) | Specifically protects web applications by inspecting HTTP/HTTPS traffic for application-layer attacks such as SQL injection and cross-site scripting (XSS) |

---

## Summary Reference Table

| Area | Key Concepts | Key Technologies |
|---|---|---|
| CIA Triad | Confidentiality, integrity, availability | Foundation of all security decisions |
| Encryption | Data in transit, data at rest | TLS, IPSec, VPN, disk encryption, PKI |
| IAM — Authentication | MFA, SSO, OTP | RADIUS, TACACS+, LDAP, SAML |
| IAM — Authorization | Least privilege, RBAC, geofencing | Active Directory, role assignments |
| Physical Security | Cameras, locks, badge access | CCTV, biometrics, access control systems |
| Deception | Honeypots, honeynets | Early warning and attacker intelligence |
| Compliance | Regulatory adherence | PCI DSS, GDPR, data locality |
| Segmentation | IoT, SCADA, guest, BYOD isolation | VLANs, firewall zones, NAC |
| DoS / DDoS | Traffic flooding, botnet attacks | Rate limiting, scrubbing services |
| Layer 2 Attacks | VLAN hopping, MAC flooding, spoofing | Dynamic ARP Inspection, DHCP snooping |
| DNS / ARP Attacks | Cache poisoning, traffic redirection | DNSSEC, DAI, DoH, DoT |
| Rogue Devices | Rogue DHCP, rogue AP, evil twin | 802.1X, DHCP snooping, WIDS |
| Social Engineering | Phishing, tailgating, shoulder surfing | Security awareness training |
| Device Hardening | Reduce attack surface | Disable unused services, patch management |
| NAC | Enforce access policy at connection | 802.1X, port security, posture assessment |
| Traffic Filtering | Control permitted traffic | ACLs, URL filtering, content filtering |
| Network Zones | Trusted, untrusted, DMZ | Screened subnet, dual-firewall architecture |
| Firewall Types | Packet filter, stateful, NGFW, WAF | Deep packet inspection, application awareness |
