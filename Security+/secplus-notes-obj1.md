# CompTIA Security+ Notes

---

## 1.0 General Security Concepts

---

## 1.1 Security Controls

Security controls are safeguards implemented to reduce risk and protect systems, networks, and data.

### Categories of Security Controls

| Category       | Description |
|---------------|------------|
| Technical     | Security mechanisms implemented using technology (e.g., firewalls, encryption, IDS) |
| Managerial    | Policies, procedures, and governance mechanisms created by management |
| Operational   | Processes executed by people (e.g., training, incident response) |
| Physical      | Physical measures (e.g., locks, guards, cameras) |

### Types of Security Controls

| Control Type        | Description | Example |
|--------------------|------------|---------|
| Preventive         | Prevent incidents before they occur | Firewall, access control |
| Deterrent          | Discourage attackers | Warning banners, cameras |
| Detective          | Identify incidents after they occur | IDS, SIEM alerts |
| Corrective         | Restore systems after incidents | Backups, patching |
| Compensating       | Alternative controls when primary controls are not possible | — |
| Directive          | Guide behavior through policies | Security policies |

---

## 1.2 Fundamental Security Concepts

### CIA Triad

The CIA Triad is the foundation of information security:

| Principle        | Description |
|-----------------|------------|
| Confidentiality | Data accessible only to authorized users |
| Integrity       | Data remains accurate and unaltered |
| Availability    | Systems and data available when needed |

### Non-repudiation

Ensures a user cannot deny performing an action.

**Implemented using:**
- Digital signatures  
- Logging  
- Cryptographic proof  

---

### AAA Framework

| Component       | Description |
|----------------|------------|
| Authentication | Verifying identity |
| Authorization  | Determining access permissions |
| Accounting     | Tracking user activity |

---

### Gap Analysis

Identifies the difference between current and desired security posture.

**Used to identify:**
- Missing controls  
- Compliance gaps  
- Security weaknesses  

---

### Zero Trust Architecture

Zero Trust assumes no implicit trust and requires continuous verification.

#### Control Plane

Handles identity verification and access decisions.

- Adaptive identity  
- Continuous verification  
- Threat scope reduction  
- Policy-driven access control  

**Components:**
- Policy Administrator  
- Policy Engine  

#### Data Plane

Handles actual data traffic.

**Components:**
- Implicit trust zones  
- Subject/System  
- Policy Enforcement Point  

---

### Physical Security Controls

| Control                     | Description |
|----------------------------|------------|
| Bollards                   | Prevent vehicle access |
| Mantrap                    | Secured entry requiring authentication |
| Fencing                    | Perimeter protection |
| Video Surveillance         | Monitoring via cameras |
| Security Guard             | Human monitoring |
| Access Badge               | Electronic authentication |
| Lighting                   | Crime deterrence |

---

### Security Sensors

| Sensor Type        | Function |
|-------------------|----------|
| Infrared          | Detect heat/movement |
| Pressure          | Detect weight |
| Microwave         | Detect motion via signals |
| Ultrasonic        | Detect movement via sound |

---

### Deception Technologies

Used to detect attackers:

| Type        | Description |
|-------------|------------|
| Honeypot    | Decoy system |
| Honeynet    | Network of honeypots |
| Honeyfile   | Fake files |
| Honeytoken  | Fake credentials/data |

---

## 1.3 Change Management

Ensures system changes do not introduce vulnerabilities.

### Business Process Elements

- Approval process  
- Ownership  
- Stakeholders  
- Impact analysis  
- Test results  
- Backout plan  
- Maintenance window  
- Standard Operating Procedures (SOP)  

---

### Technical Implications

- Allow lists / Deny lists  
- Restricted activities  
- Downtime  
- Service restart  
- Application restart  
- Legacy applications  
- Dependencies  

---

### Documentation

- Updating diagrams  
- Updating policies and procedures  

---

### Version Control

Tracks changes in configurations and code.

---

## 1.4 Cryptographic Solutions

Cryptography protects data using mathematical techniques.

---

### Public Key Infrastructure (PKI)

Framework for managing encryption keys.

| Component   | Description |
|-------------|------------|
| Public Key  | Used to encrypt data |
| Private Key | Used to decrypt data |
| Key Escrow  | Third-party key storage |

---

### Encryption

Converts plaintext into ciphertext.

**Types:**
- Full disk encryption  
- Partition encryption  
- File encryption  
- Volume encryption  
- Database encryption  
- Record encryption  

---

### Encryption Methods

| Method        | Description |
|---------------|------------|
| Symmetric     | Single key |
| Asymmetric    | Public/private key pair |

---

### Key Concepts

- Key exchange  
- Algorithms  
- Key length  

---

### Cryptographic Hardware

| Component | Description |
|----------|------------|
| TPM      | Secure key storage chip |
| HSM      | Dedicated cryptographic device |
| KMS      | Key management system |
| Secure Enclave | Isolated secure memory |

---

### Obfuscation Techniques

| Technique       | Description |
|----------------|------------|
| Steganography  | Hiding data in files |
| Tokenization   | Replacing sensitive data |
| Data Masking   | Obscuring data |

---

### Hashing

One-way function producing fixed-length output.

### Salting

Adds random data before hashing passwords.

---

### Digital Signatures

Ensure authenticity and integrity.

---

### Key Stretching

Increases password hashing complexity.

---

### Blockchain

Distributed ledger for transactions.

---

### Certificates

Digital identity verification.

| Type                          | Description |
|-------------------------------|------------|
| Certificate Authority (CA)    | Issues certificates |
| CRL                           | Revoked certificates list |
| OCSP                          | Real-time validation |
| Self-signed                   | Created by owner |
| Third-party                   | Issued by trusted CA |
| Root of Trust                 | Trust anchor |
| CSR                           | Certificate request |
| Wildcard Certificates         | Secure subdomains |

---
