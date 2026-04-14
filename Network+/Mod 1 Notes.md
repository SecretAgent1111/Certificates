Network+ Notes – Domain 1.0: Networking Concepts
🌐 1.0 OSI Reference Model (Open Systems Interconnection)

The OSI Model is a 7-layer conceptual framework used to understand how data travels across a network.

🧠 Why OSI matters
Helps in troubleshooting
Standardizes communication between vendors
Maps protocols and technologies to layers
🔹 Layer 1 – Physical Layer
5
Key Concept:

Deals with physical transmission of raw bits (0s and 1s)

Functions:
Electrical signals, voltages
Cable types (fiber, copper)
Data rate and bandwidth
Devices:
Hubs
Repeaters
Cables
🔹 Layer 2 – Data Link Layer
6
Key Concept:

Handles node-to-node communication

Functions:
MAC addressing
Error detection (CRC)
Framing
Sub-layers:
LLC (Logical Link Control)
MAC (Media Access Control)
Devices:
Switches
Bridges
🔹 Layer 3 – Network Layer
5
Key Concept:

Responsible for logical addressing and routing

Functions:
IP addressing
Path selection
Packet forwarding
Protocols:
IP
ICMP
Devices:
Routers
🔹 Layer 4 – Transport Layer
4
Key Concept:

Ensures end-to-end communication

Functions:
Segmentation
Flow control
Error recovery
Protocols:
TCP (reliable)
UDP (fast, unreliable)
🔹 Layer 5 – Session Layer
Key Concept:

Manages sessions between applications

Functions:
Session establishment
Session termination
Checkpoints & recovery
🔹 Layer 6 – Presentation Layer
Key Concept:

Handles data formatting, encryption, compression

Functions:
Encryption (SSL/TLS)
Encoding (ASCII, JPEG)
🔹 Layer 7 – Application Layer
5
Key Concept:

Closest to the user → interface for applications

Examples:
HTTP
FTP
SMTP
DNS
⚙️ 1.1 Networking Appliances, Applications & Functions
🖥️ Appliances
🔹 Router
Connects networks
Works at Layer 3
Uses IP routing
🔹 Switch
Connects devices in LAN
Uses MAC addresses
Layer 2 (some L3 switches exist)
🔹 Firewall
Filters traffic based on rules
Can be hardware or software
🔹 IDS / IPS
IDS: Detects attacks
IPS: Detects + blocks attacks
🔹 Load Balancer
Distributes traffic across servers
Improves availability
🔹 Proxy
Acts as intermediary
Provides anonymity & filtering
🔹 NAS (Network Attached Storage)
File-level storage over network
🔹 SAN (Storage Area Network)
High-speed block-level storage
📡 Wireless Components
Access Point (AP)
Provides Wi-Fi connectivity
Controller
Central management for multiple APs
🌍 Applications
CDN (Content Delivery Network)
Distributes content globally
Reduces latency
⚙️ Functions
VPN (Virtual Private Network)
Secure encrypted tunnel over internet
QoS (Quality of Service)
Prioritizes traffic (VoIP > downloads)
TTL (Time To Live)
Prevents infinite loops in networks
☁️ Cloud Concepts
🔹 NFV (Network Functions Virtualization)
Converts hardware functions into software
🔹 VPC (Virtual Private Cloud)
Isolated cloud network
🔹 Security Controls
Security Groups (stateful firewall)
Network ACLs (stateless)
🔹 Cloud Gateways
Internet Gateway → Public access
NAT Gateway → Private instances access internet
🔹 Connectivity Options
VPN → Encrypted connection
Direct Connect → Dedicated link
🔹 Deployment Models
Public cloud
Private cloud
Hybrid cloud
🔹 Service Models
SaaS → Software (e.g., Gmail)
PaaS → Platform (developers)
IaaS → Infrastructure (VMs)
🔹 Key Concepts
Scalability → increase capacity
Elasticity → auto scale
Multitenancy → shared resources
🔌 Ports, Protocols & Services
Protocol	Port
FTP	20/21
SSH / SFTP	22
Telnet	23
SMTP	25
DNS	53
DHCP	67/68
TFTP	69
HTTP	80
NTP	123
SNMP	161/162
LDAP	389
HTTPS	443
SMB	445
Syslog	514
SMTPS	587
LDAPS	636
SQL	1433
RDP	3389
SIP	5060/5061
🔹 IP Protocol Types
ICMP → Error reporting (ping)
TCP → Reliable
UDP → Fast
GRE → Tunneling
IPSec:
AH → Authentication
ESP → Encryption
IKE → Key exchange
🔹 Traffic Types
Unicast → One-to-one
Broadcast → One-to-all
Multicast → One-to-many group
Anycast → Nearest node
📡 Transmission Media & Transceivers
🔹 Wireless
802.11 → Wi-Fi
Cellular → 4G/5G
Satellite → Global coverage
🔹 Wired
Ethernet (802.3)
Standard wired LAN
Fiber
Single-mode → Long distance
Multimode → Short distance
Copper
Coaxial
Twinax (DAC)
🔹 Transceivers
SFP → Small pluggable
QSFP → High-speed
🔹 Connectors
RJ45 → Ethernet
RJ11 → Telephone
LC/SC/ST → Fiber
BNC → Coax
F-type → Cable TV
🕸️ Network Topologies & Architectures
4
🔹 Types
Mesh → Redundant
Star → Central hub
Hybrid → Combination
Spine-Leaf → Data centers
Point-to-Point → Direct link
🔹 Three-Tier Model
Core → Backbone
Distribution → Policy
Access → End devices
🔹 Traffic Flow
North-South → Client ↔ Server
East-West → Server ↔ Server
🌍 IPv4 Addressing
🔹 Public vs Private
Private (RFC1918):
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
Special:
APIPA → 169.254.x.x
Loopback → 127.0.0.1
🔹 Subnetting
CIDR → flexible addressing
VLSM → efficient subnet use
🔹 Classes
Class	Range
A	1–126
B	128–191
C	192–223
D	Multicast
E	Experimental
🚀 Modern Network Use Cases
🔹 SDN / SD-WAN
Centralized control
Application-aware routing
Zero-touch provisioning
🔹 VXLAN
Extends Layer 2 over Layer 3
Used in data centers
🔹 Zero Trust Architecture (ZTA)
Never trust, always verify
Least privilege access
🔹 SASE / SSE
Cloud-delivered security
🔹 Infrastructure as Code (IaC)
Features:
Automation
Version control
Templates
Configuration consistency
🔹 IPv6
Why:
IPv4 exhaustion
Solutions:
Dual stack
Tunneling
NAT64
