# CompTIA Security+ Notes

1.0 General Security Concepts
1.1 Security Controls

Security controls are safeguards implemented to reduce risk and protect systems, networks, and data.

Categories of Security Controls

Technical Controls
Security mechanisms implemented using technology such as firewalls, encryption, and intrusion detection systems.

Managerial Controls
Policies, procedures, and governance mechanisms created by management to guide security operations.

Operational Controls
Processes and procedures executed by people such as security awareness training and incident response.

Physical Controls
Physical measures used to protect infrastructure such as locks, guards, and surveillance cameras.

Types of Security Controls

Preventive Controls
Prevent security incidents before they occur.
Example: firewall, access control.

Deterrent Controls
Discourage attackers from attempting an attack.
Example: warning banners, security cameras.

Detective Controls
Identify security incidents after they occur.
Example: IDS, SIEM alerts.

Corrective Controls
Restore systems after an incident.
Example: backups, patching.

Compensating Controls
Alternative security measures used when primary controls cannot be implemented.

Directive Controls
Policies or guidelines directing behavior.
Example: security policies.

1.2 Fundamental Security Concepts
CIA Triad

The CIA Triad is the foundation of information security.

Confidentiality
Ensures that data is accessible only to authorized users.

Integrity
Ensures that data remains accurate and unchanged unless modified by authorized users.

Availability
Ensures that systems and data are accessible when needed.

Non-repudiation

Guarantees that a user cannot deny performing an action such as sending a message or initiating a transaction.

Implemented using:

Digital signatures

Logging

Cryptographic proof

AAA Framework

Authentication
Verifying the identity of a user or system.

Authorization
Determining what actions an authenticated user is allowed to perform.

Accounting
Tracking user actions for auditing and monitoring.

Gap Analysis

A process used to identify the difference between the current security posture and the desired security posture.

Used to identify:

missing controls

compliance gaps

security weaknesses

Zero Trust Architecture

Zero Trust assumes no implicit trust and requires continuous verification of users and systems.

Control Plane

Handles identity verification and access decisions.

Components include:

Adaptive identity
Continuous verification of user identity.

Threat scope reduction
Limits attacker movement in a network.

Policy-driven access control
Access decisions based on policies.

Policy Administrator
Implements access policies.

Policy Engine
Evaluates policies and decides access permissions.

Data Plane

Handles the actual data traffic.

Components include:

Implicit trust zones
Network segments with controlled trust boundaries.

Subject/System
User or device requesting access.

Policy Enforcement Point
Component that enforces access policies.

Physical Security Controls

Bollards
Barriers used to stop vehicles from entering restricted areas.

Access Control Vestibule (Mantrap)
A small secured area requiring authentication before entering.

Fencing
Physical barrier protecting facility perimeter.

Video Surveillance
Cameras monitoring activity.

Security Guard
Human personnel monitoring security.

Access Badge
Electronic card used for authentication.

Lighting
Illumination used to deter criminals.

Security Sensors

Infrared Sensors
Detect heat or movement.

Pressure Sensors
Detect weight on surfaces.

Microwave Sensors
Detect motion using microwave signals.

Ultrasonic Sensors
Detect movement using sound waves.

Deception Technologies

Used to detect attackers.

Honeypot
Decoy system designed to attract attackers.

Honeynet
Network of honeypots.

Honeyfile
Fake files used to detect unauthorized access.

Honeytoken
Fake credentials or data used to identify attackers.

1.3 Change Management

Change management ensures that system changes do not introduce security vulnerabilities.

Business Process Elements

Approval Process
Formal approval before changes occur.

Ownership
Defined responsibility for systems.

Stakeholders
Individuals affected by system changes.

Impact Analysis
Evaluation of risks before implementation.

Test Results
Testing ensures changes work correctly.

Backout Plan
Rollback strategy if changes fail.

Maintenance Window
Scheduled time for changes.

Standard Operating Procedures (SOP)
Documented procedures for operations.

Technical Implications

Allow lists / Deny lists
Define permitted or blocked access.

Restricted activities
Limit high-risk operations.

Downtime
Time systems are unavailable.

Service restart
Restarting services to apply changes.

Application restart
Restarting software.

Legacy applications
Older systems that may be incompatible with updates.

Dependencies
Systems relying on each other.

Documentation

Updating diagrams
Updating policies and procedures

Version Control

Tracking changes in system configurations and code.

1.4 Cryptographic Solutions

Cryptography protects data using mathematical techniques.

Public Key Infrastructure (PKI)

Framework used for managing encryption keys.

Public Key
Shared key used to encrypt data.

Private Key
Secret key used to decrypt data.

Key Escrow
Storage of encryption keys by a trusted third party.

Encryption

Encryption converts plaintext into ciphertext.

Types include:

Full disk encryption
Encrypts entire hard drive.

Partition encryption
Encrypts disk partitions.

File encryption
Encrypts individual files.

Volume encryption
Encrypts logical storage volumes.

Database encryption
Encrypts database content.

Record encryption
Encrypts specific database entries.

Encryption Methods

Symmetric Encryption
Uses one key for encryption and decryption.

Asymmetric Encryption
Uses public and private keys.

Key Exchange
Securely sharing encryption keys.

Algorithms
Mathematical formulas used for encryption.

Key Length
Size of encryption key affecting security strength.

Cryptographic Hardware

Trusted Platform Module (TPM)
Hardware chip storing encryption keys.

Hardware Security Module (HSM)
Secure hardware device for managing cryptographic keys.

Key Management System
Manages encryption keys.

Secure Enclave
Isolated secure memory area.

Obfuscation Techniques

Steganography
Hiding data within another file.

Tokenization
Replacing sensitive data with tokens.

Data Masking
Hiding data with fictional values.

Hashing

One-way mathematical function converting data into fixed-length value.

Salting

Adding random data to passwords before hashing.

Digital Signatures

Cryptographic mechanism ensuring data authenticity and integrity.

Key Stretching

Technique that strengthens passwords by increasing hashing complexity.

Blockchain

Distributed ledger storing transaction records.

Certificates

Digital documents verifying identity.

Types include:

Certificate Authorities (CA)
Trusted organizations issuing certificates.

Certificate Revocation Lists (CRL)
List of revoked certificates.

Online Certificate Status Protocol (OCSP)
Real-time certificate validation.

Self-signed certificates
Certificates created by the owner.

Third-party certificates
Certificates issued by trusted authorities.

Root of trust
Trusted starting point in certificate hierarchy.

Certificate Signing Request (CSR)
Request sent to a CA to obtain a certificate.

Wildcard certificates
Certificates securing multiple subdomains.
