# Domain 3 – Security Architecture

Security architecture focuses on designing secure enterprise systems and infrastructure.  
It includes network architecture, secure communication, infrastructure protection, data protection, and resilience planning.

---

## 3.1 Security Architecture Models

Security architecture models define how systems are designed, deployed, and secured.

---

### Cloud Computing

Cloud computing delivers services over the internet using a shared responsibility model.

#### Responsibility Matrix

| Responsibility        | Cloud Provider | Customer |
|----------------------|--------------|----------|
| Physical Security    | ✓            |          |
| Hardware             | ✓            |          |
| Data Protection      |              | ✓        |
| Identity Management  |              | ✓        |
| Application Security |              | ✓        |

---

### Hybrid Cloud

Combination of on-premises and cloud infrastructure.

**Security Concerns:**
- Data movement  
- Identity management  
- Network security  

---

### Third-Party Vendors

External service providers (e.g., cloud, SaaS, MSSP).

**Risks:**
- Supply chain attacks  
- Data exposure  
- Service compromise  

---

### Infrastructure as Code (IaC)

Infrastructure managed using scripts/config files.

**Benefits:**
- Automation  
- Consistency  
- Faster deployment  

**Risk:**
- Misconfiguration at scale  

---

### Serverless Architecture

Code execution without managing servers.

**Example:** AWS Lambda  

**Security Considerations:**
- API security  
- Permissions  
- Identity access management  

---

### Microservices Architecture

Applications split into smaller independent services.

**Benefits:**
- Scalability  
- Flexibility  
- Fault isolation  

**Risks:**
- Complex security  
- API exposure  

---

### Network Infrastructure

Includes:
- Routers  
- Switches  
- Firewalls  
- Gateways  

**Benefits:**
- Segmentation  
- Monitoring  
- Threat detection  

---

### Isolation Techniques

#### Physical Isolation
- Complete separation of systems  

#### Air-Gapped Systems
- No network/internet connection  
- Used in critical environments  

---

### Logical Segmentation

- VLANs  
- Subnets  
- Firewall rules  

**Purpose:**
- Reduce attack surface  
- Prevent lateral movement  

---

### Software-Defined Networking (SDN)

Network controlled via software.

**Benefits:**
- Centralized control  
- Automation  

**Risk:**
- Controller compromise  

---

### On-Premises Infrastructure

**Advantages:**
- Full control  
- Easier compliance  

**Disadvantages:**
- High cost  
- Maintenance overhead  

---

### Architecture Models

| Model         | Description |
|---------------|------------|
| Centralized   | Single control point |
| Decentralized | Distributed systems |

**Security Insight:**
- Centralized → easier monitoring  
- Decentralized → better resilience  

---

### Containerization

Applications packaged with dependencies.

**Example:** Docker  

**Benefits:**
- Portability  
- Scalability  

**Risks:**
- Container escape  
- Insecure images  

---

### Virtualization

Multiple VMs on one system.

**Benefits:**
- Resource efficiency  
- Isolation  

**Risks:**
- Hypervisor attacks  
- VM escape  

---

### IoT (Internet of Things)

Connected smart devices.

**Risks:**
- Weak authentication  
- Outdated firmware  
- Limited security  

---

### ICS / SCADA

Industrial control systems.

**Examples:**
- Power plants  
- Manufacturing  

**Risks:**
- Critical infrastructure attacks  
- Legacy vulnerabilities  

---

### RTOS (Real-Time OS)

Used in:
- Robotics  
- Aviation  
- Embedded systems  

---

### Embedded Systems

Dedicated systems inside hardware.

**Examples:**
- Medical devices  
- Vehicles  

---

### High Availability

Ensures continuous operation.

**Methods:**
- Redundancy  
- Clustering  
- Load balancing  

---

### Architecture Design Considerations

- Availability  
- Resilience  
- Cost  
- Responsiveness  
- Scalability  
- Ease of deployment  
- Risk transference  
- Recovery capability  
- Patch availability  
- Power requirements  
- Compute resources  

---

## 3.2 Securing Enterprise Infrastructure

---

### Infrastructure Considerations

| Concept          | Description |
|------------------|------------|
| Device Placement | Strategic positioning (e.g., firewalls) |
| Security Zones   | Network segmentation by trust level |
| Attack Surface   | Total entry points |
| Connectivity     | Network connections |

---

### Failure Modes

| Mode        | Behavior | Risk |
|-------------|----------|------|
| Fail-Open   | Allows traffic | Security risk |
| Fail-Closed | Blocks traffic | Availability risk |

---

### Device Types

| Type     | Description |
|----------|------------|
| Active   | Interacts with traffic |
| Passive  | Monitors only |

---

### Inline vs Monitor

| Type   | Description |
|--------|------------|
| Inline | In traffic path |
| Tap    | Observes traffic |

---

### Network Appliances

| Device        | Purpose |
|---------------|--------|
| Jump Server   | Secure admin access |
| Proxy Server  | Intermediary for requests |
| IDS           | Detects threats |
| IPS           | Blocks threats |
| Load Balancer | Distributes traffic |
| Sensors       | Collect data |

---

### Port Security

- IEEE 802.1X  
- EAP (Extensible Authentication Protocol)  

---

### Firewall Types

| Firewall Type | Description |
|---------------|------------|
| WAF           | Protects web apps |
| UTM           | Multiple security functions |
| NGFW          | Advanced inspection |

---

### Layer 4 vs Layer 7

| Layer | Function |
|-------|---------|
| L4    | IP and port filtering |
| L7    | Application-level inspection |

---

### Secure Communication

| Technology | Description |
|------------|------------|
| VPN        | Encrypted tunnel |
| TLS        | Secure communication |
| IPSec      | Network-level encryption |

---

### Advanced Networking

| Technology | Description |
|------------|------------|
| SD-WAN     | Software-managed WAN |
| SASE       | Cloud-based networking + security |

---

### Control Selection

Controls should be based on:
- Risk level  
- System requirements  
- Compliance  

---

## 3.3 Data Protection

---

### Data Types

| Type                  | Description |
|-----------------------|------------|
| Regulated Data        | Legal/compliance data |
| Trade Secrets         | Confidential business data |
| Intellectual Property | Patents, designs |
| Financial Data        | Transactions, accounting |
| Legal Data            | Legal documents |

---

### Data Formats

- Human-readable (documents)  
- Machine-readable (binary)  

---

### Data Classification

- Public  
- Private  
- Confidential  
- Restricted  
- Critical  

---

### Data States

| State         | Description |
|---------------|------------|
| At Rest       | Stored data |
| In Transit    | Moving data |
| In Use        | Processing data |

---

### Data Governance

- Data sovereignty  
- Geolocation compliance  

---

### Data Protection Methods

- Encryption  
- Hashing  
- Masking  
- Tokenization  
- Obfuscation  
- Segmentation  
- Access control  

---

## 3.4 Resilience and Recovery

---

### High Availability Techniques

- Load balancing  
- Clustering  

---

### Site Types

| Type      | Description |
|-----------|------------|
| Hot Site  | Fully operational |
| Warm Site | Partially ready |
| Cold Site | Minimal setup |

---

### Resilience Strategies

- Geographic dispersion  
- Platform diversity  
- Multi-cloud environments  

---

### Continuity Planning

Ensures business operations continue during disruptions.

---

### Capacity Planning

Includes:
- Personnel  
- Technology  
- Infrastructure  

---

### Testing Methods

- Tabletop exercises  
- Failover testing  
- Simulations  
- Parallel testing  

---

### Backup Methods

- Onsite backups  
- Offsite backups  
- Encrypted backups  
- Snapshots  
- Data replication  
- Journaling  

---

### Power Protection

| Method     | Description |
|------------|------------|
| Generators | Backup power |
| UPS        | Temporary power supply |

---
