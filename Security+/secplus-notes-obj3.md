Domain 3 – Security Architecture

Security architecture focuses on designing secure enterprise systems and infrastructure.
It includes network architecture, secure communication, infrastructure protection, data protection, and resilience planning.

3.1 Compare and Contrast Security Implications of Different Architecture Models

Security architecture models determine how systems and infrastructure are designed, deployed, and secured.

Architecture and Infrastructure Concepts
Cloud Computing

Cloud computing delivers computing services over the internet.

Security responsibility is shared between the cloud provider and the customer.

Responsibility Matrix

Defines which security responsibilities belong to:

Cloud provider

Customer

Example:

Provider responsibilities

Physical data center security

Hardware infrastructure

Customer responsibilities

Data protection

Identity management

Application security

Hybrid Cloud Considerations

Hybrid cloud combines:

On-premises infrastructure

Cloud services

Security concerns include:

Data movement

Identity management

Network security

Third-Party Vendors

External companies providing services such as:

Cloud hosting

Software platforms

Managed security services

Security risks include:

supply chain attacks

data exposure

service compromise

Infrastructure as Code (IaC)

Infrastructure managed through configuration files or scripts rather than manual processes.

Benefits:

automation

consistent deployments

faster provisioning

Risk:

misconfiguration at scale.

Serverless Architecture

Cloud model where developers deploy code without managing servers.

Example:

AWS Lambda

Security considerations:

API security

function permissions

identity access management

Microservices Architecture

Applications divided into small independent services.

Benefits:

scalability

flexibility

fault isolation

Risks:

complex security management

API exposure

Network Infrastructure

Includes physical and virtual networking components such as:

routers

switches

gateways

firewalls

Proper design improves:

segmentation

traffic monitoring

attack detection

Physical Isolation

Physical separation of systems to prevent unauthorized communication.

Air-Gapped Systems

Systems completely isolated from networks and the internet.

Used in:

military systems

critical infrastructure

Logical Segmentation

Separating networks using logical controls such as:

VLANs

subnets

firewall rules

Purpose:

reduce attack surface

limit lateral movement

Software-Defined Networking (SDN)

Network architecture controlled through software rather than hardware.

Benefits:

centralized management

automated configuration

Risk:

compromise of central controller.

On-Premises Infrastructure

Systems hosted within the organization's physical environment.

Advantages:

full control over security

compliance management

Disadvantages:

high maintenance cost.

Centralized vs Decentralized Architecture

Centralized architecture

control managed from one location.

Decentralized architecture

distributed across multiple systems.

Security considerations:

centralized systems easier to monitor

decentralized systems improve resilience.

Containerization

Applications packaged into containers that include all dependencies.

Example:

Docker containers.

Benefits:

portability

scalability

resource efficiency

Risks:

container escape

insecure container images.

Virtualization

Running multiple virtual machines on one physical system.

Benefits:

resource optimization

isolation between systems

Risks:

hypervisor attacks

VM escape.

Internet of Things (IoT)

Devices connected to the internet.

Examples:

smart cameras

smart thermostats

industrial sensors

Risks:

weak authentication

outdated firmware

limited security controls.

Industrial Control Systems (ICS) / SCADA

Systems used to control industrial processes.

Examples:

power plants

water treatment

manufacturing systems

Security concerns:

critical infrastructure attacks

legacy system vulnerabilities.

Real-Time Operating Systems (RTOS)

Operating systems designed to process data in real-time with minimal delay.

Used in:

embedded systems

robotics

aviation systems.

Embedded Systems

Dedicated computing systems integrated into hardware devices.

Examples:

medical devices

vehicle control systems

smart appliances.

High Availability

Systems designed to operate continuously without downtime.

Methods include:

redundancy

clustering

load balancing.

Architecture Design Considerations

When designing secure infrastructure, consider:

Availability

Ensuring systems remain accessible to users.

Resilience

Ability of systems to recover quickly from disruptions.

Cost

Balancing security with operational budget.

Responsiveness

System performance and user experience.

Scalability

Ability to expand infrastructure as demand increases.

Ease of Deployment

How quickly systems can be implemented.

Risk Transference

Shifting risk to third parties such as cloud providers or insurance.

Ease of Recovery

Ability to restore systems after incidents.

Patch Availability

Ability to apply security updates.

Inability to Patch

Some legacy systems cannot receive updates.

Power Requirements

Systems require reliable electricity sources.

Compute Resources

Processing capacity required for workloads.

3.2 Apply Security Principles to Secure Enterprise Infrastructure

Infrastructure security involves protecting network devices, communication channels, and system access points.

Infrastructure Considerations
Device Placement

Positioning devices strategically to protect critical assets.

Example:

placing firewalls at network boundaries.

Security Zones

Dividing networks into zones based on trust level.

Examples:

DMZ (Demilitarized Zone)

Internal network

External network

Attack Surface

Total number of potential entry points attackers can exploit.

Reducing attack surface improves security.

Connectivity

Network connections between systems.

Examples:

wired networks

wireless networks

VPN connections.

Failure Modes

How systems behave during failure.

Fail-Open

System allows traffic when failure occurs.

Advantage:

availability

Risk:

security exposure.

Fail-Closed

System blocks traffic during failure.

Advantage:

strong security

Risk:

service disruption.

Device Attributes
Active vs Passive

Active devices

interact with network traffic.

Passive devices

monitor traffic without altering it.

Inline vs Tap / Monitor

Inline devices

placed directly in network path.

Tap / monitor devices

observe traffic without interrupting flow.

Network Appliances
Jump Server

Secure server used to access sensitive systems.

Purpose:

controlled administrative access.

Proxy Server

Server that acts as intermediary between users and internet resources.

Functions:

filtering traffic

anonymizing requests

caching data.

Intrusion Detection System (IDS)

Monitors network traffic for suspicious activity.

Alerts administrators but does not block traffic.

Intrusion Prevention System (IPS)

Actively blocks malicious traffic.

Load Balancer

Distributes network traffic across multiple servers.

Benefits:

performance improvement

high availability.

Sensors

Devices that collect security data for monitoring.

Examples:

network sensors

environmental sensors.

Port Security
IEEE 802.1X

Network authentication protocol controlling access to network ports.

Extensible Authentication Protocol (EAP)

Framework used for authentication methods in network access.

Firewall Types
Web Application Firewall (WAF)

Protects web applications from attacks such as:

SQL injection

cross-site scripting.

Unified Threat Management (UTM)

Security device combining multiple security functions such as:

firewall

antivirus

intrusion detection.

Next-Generation Firewall (NGFW)

Advanced firewall with features such as:

deep packet inspection

application awareness

intrusion prevention.

Layer 4 vs Layer 7 Firewalls

Layer 4 firewall

filters traffic based on IP and port.

Layer 7 firewall

inspects application-level data.

Secure Communication
Virtual Private Network (VPN)

Encrypted tunnel allowing secure remote access.

Remote Access

Access to corporate systems from external locations.

Tunneling Protocols

Protocols that encapsulate data for secure transmission.

Examples:

Transport Layer Security (TLS)

Internet Protocol Security (IPSec)

Software-Defined WAN (SD-WAN)

Software-based technology managing wide area network connectivity.

Benefits:

improved performance

centralized control.

Secure Access Service Edge (SASE)

Cloud-based architecture combining networking and security services.

Includes:

secure web gateways

firewall as a service

zero trust network access.

Selection of Effective Controls

Security controls must be selected based on:

risk level

system requirements

compliance regulations.

3.3 Protect Data

Protecting organizational data is a critical part of security architecture.

Data Types
Regulated Data

Data governed by laws and regulations.

Examples:

health records

financial data

Trade Secrets

Confidential business information.

Intellectual Property

Patents, designs, and proprietary knowledge.

Legal Information

Documents related to legal matters.

Financial Information

Accounting records and financial transactions.

Human-Readable Data

Data understandable by humans.

Example:

documents.

Non-Human-Readable Data

Machine-readable data such as binary files.

Data Classification

Organizations categorize data based on sensitivity.

Examples:

Sensitive
Confidential
Public
Restricted
Private
Critical

Data States
Data at Rest

Data stored on storage devices.

Data in Transit

Data moving across networks.

Data in Use

Data actively being processed.

Data Sovereignty

Legal requirement that data must remain within specific geographic locations.

Geolocation

Tracking data location for regulatory compliance.

Methods to Secure Data

Geographic restrictions

Encryption

Hashing

Masking

Tokenization

Obfuscation

Segmentation

Permission restrictions

3.4 Resilience and Recovery

Resilience ensures systems continue operating during disruptions.

Recovery ensures systems return to normal after incidents.

High Availability
Load Balancing

Distributes workloads across servers.

Clustering

Multiple systems working together as a single system.

Site Types
Hot Site

Fully operational backup facility.

Cold Site

Backup location with minimal infrastructure.

Warm Site

Partially equipped backup facility.

Geographic Dispersion

Systems distributed across multiple locations.

Platform Diversity

Using different hardware or software to reduce risk of single vulnerability affecting all systems.

Multi-Cloud Systems

Using multiple cloud providers for redundancy and resilience.

Continuity of Operations

Plans ensuring essential services continue during disruptions.

Capacity Planning

Planning system resources including:

People

Technology

Infrastructure

Testing Methods

Tabletop exercises

Failover testing

Simulation

Parallel processing

Backup Methods

Onsite backups

Offsite backups

Backup frequency

Encrypted backups

Snapshots

Data replication

Journaling

Power Protection
Generators

Backup power supply.

Uninterruptible Power Supply (UPS)

Battery system providing temporary power during outages.
