# Domain 4 – Security Operations

This domain focuses on applying security techniques, managing assets, monitoring systems, handling vulnerabilities, and responding to incidents.

---

## 4.1 Security Techniques for Computing Resources

Security techniques protect systems, devices, and infrastructure.

---

### Secure Baselines

A secure baseline is a predefined configuration standard.

| Phase     | Description |
|-----------|------------|
| Establish | Define secure configurations |
| Deploy    | Apply configurations |
| Maintain  | Update configurations regularly |

---

### Hardening Targets

Hardening reduces vulnerabilities by minimizing attack surface.

| Target              | Security Measures |
|---------------------|------------------|
| Mobile Devices      | MDM, encryption, app control |
| Workstations        | Antivirus, patching, least privilege |
| Switches            | Port security, VLANs |
| Routers             | Disable unused services, firmware updates |
| Cloud Infrastructure| Access control, encryption, monitoring |
| Servers             | Patching, monitoring, access control |
| ICS / SCADA         | Segmentation, monitoring |
| Embedded Systems    | Limited controls, hardware constraints |
| RTOS                | Real-time secure processing |
| IoT Devices         | Strong authentication, firmware updates |

---

### Wireless Security

#### Installation Considerations

- Site surveys  
- Heat maps  

---

### Mobile Device Management (MDM)

Capabilities:
- Remote wipe  
- Encryption  
- Application control  

---

### Deployment Models

| Model | Description | Risk |
|-------|------------|------|
| BYOD  | Personal devices | Data leakage |
| COPE  | Corporate-owned | Moderate risk |
| CYOD  | Approved device list | Controlled risk |

---

### Connection Methods

- Cellular  
- Wi-Fi  
- Bluetooth  

---

### Wireless Security Controls

- WPA3  
- RADIUS  

---

### Application Security

| Technique             | Description |
|----------------------|------------|
| Input Validation     | Prevent malicious input |
| Secure Cookies       | Protect session data |
| Static Code Analysis | Code review without execution |
| Code Signing         | Verify software integrity |
| Sandboxing           | Isolate execution |
| Monitoring           | Detect anomalies |

---

## 4.2 Asset Management

Asset management ensures visibility and control over systems.

---

### Asset Lifecycle

| Phase                  | Description |
|-----------------------|------------|
| Acquisition           | Secure procurement |
| Assignment            | Track ownership |
| Monitoring            | Maintain inventory |
| Disposal              | Secure removal |

---

### Key Concepts

- Ownership  
- Classification  
- Inventory  
- Enumeration  

---

### Secure Disposal

| Method        | Description |
|---------------|------------|
| Sanitization  | Data removal |
| Destruction   | Physical damage |
| Certification | Proof of removal |

---

### Data Retention

Defines how long data is stored.

---

## 4.3 Vulnerability Management

Identifies and fixes security weaknesses.

---

### Identification Methods

- Vulnerability scanning  
- Static analysis  
- Dynamic analysis  
- Package monitoring  
- Threat intelligence feeds  
- Penetration testing  
- Bug bounty programs  
- Audits  

---

### Threat Intelligence Sources

- OSINT  
- Proprietary feeds  
- Sharing organizations  
- Dark web monitoring  

---

### Vulnerability Analysis

| Concept            | Description |
|-------------------|------------|
| False Positive    | Incorrect detection |
| False Negative    | Missed vulnerability |
| CVSS              | Severity scoring |
| CVE               | Public vulnerability database |

---

### Risk Factors

- Exposure factor  
- Environmental variables  
- Industry impact  
- Risk tolerance  

---

### Remediation

- Patching  
- Segmentation  
- Compensating controls  
- Risk acceptance  

---

### Validation

- Rescanning  
- Audit verification  

---

### Reporting

Document vulnerabilities and fixes.

---

## 4.4 Security Monitoring and Alerting

Monitoring detects malicious activity.

---

### Monitoring Targets

- Systems  
- Applications  
- Infrastructure  

---

### Security Activities

- Log aggregation  
- Alerting  
- Scanning  
- Reporting  
- Log archiving  

---

### Monitoring Tools

| Tool        | Description |
|-------------|------------|
| SIEM        | Log analysis platform |
| Antivirus   | Malware detection |
| DLP         | Data protection |
| NetFlow     | Traffic monitoring |
| SNMP Traps  | Device alerts |
| Vulnerability Scanners | Weakness detection |

---

### Frameworks and Standards

- SCAP  
- CIS Benchmarks  

---

### Monitoring Types

| Type        | Description |
|-------------|------------|
| Agent-Based | Installed on system |
| Agentless   | Remote monitoring |

---

### Alert Response

- Quarantine systems  
- Tune alerts  

---

## 4.5 Enterprise Security Modifications

Improving security controls.

---

### Examples

- Firewall rules  
- IDS/IPS tuning  
- Web filtering  
- DNS filtering  
- Email security  

---

### Email Security Controls

- SPF  
- DKIM  
- DMARC  

---

### Detection Technologies

| Tool | Description |
|------|------------|
| FIM  | File integrity monitoring |
| EDR  | Endpoint detection |
| XDR  | Extended detection |
| UBA  | User behavior analytics |

---

## 4.6 Identity and Access Management (IAM)

Ensures only authorized access.

---

### Account Management

- Provisioning  
- De-provisioning  
- Permission assignment  

---

### Identity Concepts

- Identity proofing  
- Federation  
- Single Sign-On (SSO)  

---

### Protocols

- LDAP  
- OAuth  
- SAML  

---

### Access Control Models

| Model | Description |
|-------|------------|
| MAC   | Strict control |
| DAC   | Owner-based |
| RBAC  | Role-based |
| Rule-Based | Rule-driven |
| ABAC  | Attribute-based |

---

### Authentication Controls

- MFA  
- Biometrics  
- Tokens  
- Security keys  

---

### Authentication Factors

- Something you know  
- Something you have  
- Something you are  
- Somewhere you are  

---

### Password Security

- Complexity  
- Length  
- Expiration  
- Reuse restrictions  

---

### Advanced Concepts

- Password managers  
- Passwordless authentication  
- Privileged Access Management (PAM)  

---

## 4.7 Automation and Orchestration

Automation improves efficiency and consistency.

---

### Use Cases

- User provisioning  
- Resource provisioning  
- Ticketing  
- Escalation workflows  

---

### Technologies

- APIs  
- CI/CD pipelines  

---

### Benefits

- Efficiency  
- Scalability  
- Faster response  

---

### Risks

- Complexity  
- Cost  
- Single point of failure  
- Maintenance challenges  

---

## 4.8 Incident Response

Process for handling security incidents.

---

### Phases

1. Preparation  
2. Detection  
3. Analysis  
4. Containment  
5. Eradication  
6. Recovery  
7. Lessons learned  

---

### Key Activities

- Training  
- Testing (tabletop, simulation)  
- Root cause analysis  
- Threat hunting  
- Digital forensics  

---

### Legal Considerations

- Legal hold  
- Chain of custody  
- Evidence acquisition  
- Evidence preservation  
- E-discovery  

---

## 4.9 Investigation Data Sources

Used for security investigations.

---

### Log Sources

- Firewall logs  
- Application logs  
- Endpoint logs  
- OS logs  
- IDS/IPS logs  
- Network logs  

---

### Additional Data

- Metadata  
- Vulnerability scan results  
- Security reports  
- Dashboards  
- Packet captures (PCAP)  

---
