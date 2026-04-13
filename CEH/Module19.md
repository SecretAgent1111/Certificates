
# Module 19: Cloud Computing

## 1. Introduction to Cloud Computing

**Definition:**  
Cloud computing is the delivery of computing services over the Internet, including servers, storage, databases, networking, software, and analytics.

**Explanation:**  
Instead of buying and maintaining physical hardware, users rent resources on-demand from remote data centers. This makes cloud environments flexible, scalable, and cost-efficient compared to traditional IT.

**Key Characteristics:**  
- **On-demand self-service** — Users can provision resources without human interaction.  
- **Broad network access** — Services are reachable over the internet.  
- **Resource pooling** — Multiple customers share the same infrastructure.  
- **Rapid elasticity** — Resources can scale up or down quickly.  
- **Measured service** — Users pay only for what they use.  

**Example:**  
Hosting a website on AWS instead of buying and maintaining a physical server.

---

## 2. Cloud Service Models

### 2.1 Infrastructure as a Service (IaaS)

**Definition:**  
Provides virtualized computing resources such as servers, storage, and networks.

**You control:**  
- Operating system  
- Applications  
- Network settings  

**Provider controls:**  
- Physical hardware  
- Virtualization layer  

**Examples:**  
- AWS EC2  
- Microsoft Azure Virtual Machines  

### 2.2 Platform as a Service (PaaS)

**Definition:**  
Provides a platform to build, deploy, and manage applications without managing infrastructure.

**You control:**  
- Applications  
- Data  

**Provider controls:**  
- Operating system  
- Runtime  
- Infrastructure  

**Examples:**  
- Google App Engine  
- AWS Elastic Beanstalk  

### 2.3 Software as a Service (SaaS)

**Definition:**  
Provides ready-to-use applications over the internet.

**You control:**  
- User settings only  

**Examples:**  
- Gmail  
- Microsoft 365  

### Service Model Comparison

| Model | Control | Management | Example |
|------|---------|------------|---------|
| **IaaS** | High | User-heavy | AWS EC2 |
| **PaaS** | Medium | Balanced | Google App Engine |
| **SaaS** | Low | Provider-heavy | Gmail |

---

## 3. Shared Responsibility Model

**Definition:**  
Security responsibilities are shared between the cloud provider and the customer.

**Provider responsibility:**  
- Physical security  
- Data center infrastructure  
- Network hardware  

**Customer responsibility:**  
- Data security  
- Identity and access management (IAM)  
- OS patching in IaaS  

**Example:**  
AWS secures the data center, while you secure your EC2 instance and data.

**Interview Insight:**  
Misconfiguration by users is one of the most common causes of cloud breaches.

---

## 4. Cloud Deployment Models

### 4.1 Public Cloud

**Definition:**  
Cloud resources are available to the public and shared across multiple tenants.

**Example:**  
AWS, Microsoft Azure, Google Cloud.

### 4.2 Private Cloud

**Definition:**  
Cloud infrastructure dedicated to one organization only.

**Benefit:**  
Greater control and customization.

### 4.3 Hybrid Cloud

**Definition:**  
Combination of public and private cloud environments.

**Use Case:**  
Sensitive data stays private while public cloud handles scaling.

### 4.4 Community Cloud

**Definition:**  
Shared by organizations with common goals or compliance needs.

---

## 5. NIST Cloud Architecture

**Key Actors:**  
- Cloud Consumer  
- Cloud Provider  
- Cloud Broker  
- Cloud Auditor  
- Cloud Carrier  

**Purpose:**  
NIST defines roles and structure to improve interoperability, governance, and security.

---

## 6. Cloud Storage Architecture

### Types of Storage

| Type | Use | Example |
|------|-----|---------|
| **Object Storage** | Stores data as objects | AWS S3 |
| **Block Storage** | Used for disks and volumes | AWS EBS |
| **File Storage** | Shared file systems | AWS EFS |

### Security Concerns
- Data leakage  
- Misconfigured buckets  
- Unauthorized access  

---

## 7. Fog and Edge Computing

### Fog Computing

**Definition:**  
An extension of cloud computing closer to devices to reduce latency.

### Edge Computing

**Definition:**  
Processing happens at or near the device itself.

### Cloud vs Fog vs Edge

| Feature | Cloud | Fog | Edge |
|--------|------|-----|------|
| **Location** | Central | Intermediate | Near device |
| **Latency** | High | Medium | Low |

**Example:**  
IoT and smart camera processing often use edge computing.

---

## 8. Cloud vs Grid Computing

**Cloud Computing:**  
Provides on-demand services and scalable virtual resources over the internet.

**Grid Computing:**  
Combines distributed computing resources to complete a specific task.

**Key Difference:**  
Cloud is service-oriented, while grid is task-oriented.

---

## 9. Container Technology

**Definition:**  
Containers package an application with its dependencies and runtime environment.

**Benefits:**  
- Lightweight  
- Portable  
- Fast deployment  

### Container vs Virtual Machine

| Feature | Container | VM |
|------|----------|----|
| OS | Shared | Separate |
| Size | Small | Large |
| Boot time | Fast | Slow |

---

## 10. Docker

**Definition:**  
Docker is a platform used to build, ship, and run containers.

**Components:**  
- Docker Engine  
- Docker Images  
- Docker Containers  
- Docker Hub  

**Example:**  
A developer packages a web app into a Docker image and runs it anywhere.

---

## 11. Container Orchestration

**Definition:**  
Automating deployment, scaling, networking, and management of containers.

**Tools:**  
- Kubernetes  
- Docker Swarm  

---

## 12. Kubernetes

**Definition:**  
A container orchestration platform used to manage clusters of containers.

**Key Components:**  
- Pods  
- Nodes  
- Cluster  
- API Server  

**Example:**  
Kubernetes automatically restarts failed containers and balances workload across nodes.

---

## 13. Container Security Challenges

**Common Issues:**  
- Weak isolation  
- Vulnerable images  
- Misconfigurations  
- Privileged containers  

**Risk:**  
If a container is over-privileged, attackers may escape to the host system.

---

## 14. Serverless Computing

**Definition:**  
Running code without managing servers.

**Example:**  
AWS Lambda.

**Benefits:**  
- No server management  
- Auto-scaling  
- Cost-efficient  

### Serverless vs Containers

| Feature | Serverless | Containers |
|------|-----------|------------|
| Control | Low | High |
| Scaling | Automatic | Manual or automatic |

---

## 15. Cloud Computing Threats

### Common Risks
- Data breaches  
- Misconfiguration  
- Insecure APIs  
- Account hijacking  

### Container Risks
- Image vulnerabilities  
- Runtime attacks  

### Kubernetes Risks
- Misconfigured RBAC  
- API exposure  

### Serverless Risks
- Event injection  
- Function abuse  

---

## 16. Cloud Attacks

**Common Attacks:**  
- Data exfiltration  
- DDoS  
- Cryptojacking  
- IAM privilege escalation  

**Example:**  
An attacker abuses cloud credentials to spin up mining instances or download sensitive buckets.

---

## 17. Cloud Hacking Methodology

1. Reconnaissance  
2. Scanning  
3. Enumeration  
4. Exploitation  
5. Privilege escalation  
6. Maintaining access  
7. Covering tracks  

---

## 18. Cloud Enumeration Tools

| Tool | Use |
|------|-----|
| **Masscan** | Fast port scanning |
| **Prowler** | AWS auditing |
| **CloudSploit** | Misconfiguration detection |

---

## 19. AWS Hacking

### Common Targets
- S3 buckets  
- EC2 instances  
- IAM roles  
- RDS databases  

### Risks
- Public S3 bucket exposure  
- Open ports on EC2  
- Weak SSH keys  
- IAM privilege escalation  

### Tools
- S3Scanner  
- BucketLoot  
- CloudBrute  
- CloudFox  
- Cartography  

---

## 20. Cloud Security

**Control Layers:**  
- Physical  
- Network  
- Application  
- Data  

**Key Controls:**  
- Encryption  
- IAM  
- Logging  
- Monitoring  

---

## 21. Best Practices

### General
- Least privilege access  
- Multi-factor authentication  
- Regular audits  

### AWS
- Secure S3 buckets  
- Use IAM roles  
- Enable CloudTrail  

### Azure
- Use RBAC  
- Enable Security Center  

### GCP
- Use IAM policies  
- Enable logging  

---

## 22. SAML

**Definition:**  
Security Assertion Markup Language is used for Single Sign-On (SSO).

**Example:**  
Login once and access multiple cloud services without re-authenticating.

---

## 23. Cloud Network Security

**Controls:**  
- Firewalls  
- VPN  
- Security groups  
- Network ACLs  

---

## 24. Zero Trust Model

**Definition:**  
"Never trust, always verify."

**Principles:**  
- Continuous authentication  
- Least privilege  
- Micro-segmentation  

---

## 25. Compliance Checklist

**Common Standards:**  
- GDPR  
- HIPAA  
- ISO 27001  

**Purpose:**  
Ensure cloud environments meet legal and regulatory requirements.

---

## 26. Shadow Cloud

**Definition:**  
Unauthorized use of cloud services inside an organization.

**Risk:**  
- Data leakage  
- No visibility  
- No control  

