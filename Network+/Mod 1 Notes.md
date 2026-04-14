# Network+ Notes — Domain 1.0: Networking Concepts

---

## 1.0 OSI Reference Model (Open Systems Interconnection)

**Definition:** The OSI Model is a seven-layer conceptual framework developed by the International Organization for Standardization (ISO) that describes how data is transmitted across a network. Each layer has a distinct role and communicates only with the layers directly above and below it.

### Why the OSI Model Matters

- Provides a universal language for describing network functions across different vendors and technologies
- Enables systematic troubleshooting by isolating problems to a specific layer
- Maps protocols, devices, and services to their corresponding layer for clarity

---

### OSI Layer Reference Table

| Layer | Name | Key Concept | Functions | Protocols / Technologies | Devices |
|---|---|---|---|---|---|
| 7 | Application | Closest to the end user; provides network services to applications | HTTP, FTP, DNS, email access | HTTP, FTP, SMTP, DNS, SNMP | — |
| 6 | Presentation | Translates data between application format and network format | Encryption, encoding, compression | SSL/TLS, ASCII, JPEG, MPEG | — |
| 5 | Session | Manages and controls dialogue between two communicating systems | Session establishment, maintenance, termination, checkpoints | NetBIOS, RPC | — |
| 4 | Transport | Ensures reliable end-to-end data delivery between hosts | Segmentation, flow control, error recovery, port addressing | TCP (reliable), UDP (fast, connectionless) | — |
| 3 | Network | Handles logical addressing and determines the best path for data | IP addressing, routing, packet forwarding | IP, ICMP, OSPF, BGP | Routers |
| 2 | Data Link | Manages node-to-node communication and physical addressing | MAC addressing, framing, error detection (CRC) | Ethernet (802.3), PPP | Switches, Bridges |
| 1 | Physical | Transmits raw bits (0s and 1s) over a physical medium | Electrical signals, voltages, data rate, cable specifications | 802.3 (Ethernet physical), DSL | Hubs, Repeaters, Cables |

### Data Link Sub-layers

| Sub-layer | Name | Role |
|---|---|---|
| LLC | Logical Link Control | Interfaces between the Network layer and MAC sub-layer; handles flow control and error notification |
| MAC | Media Access Control | Controls how devices on the network gain access to the medium and permission to transmit data |

---

## 1.1 Networking Appliances, Applications, and Functions

### Network Appliances

| Appliance | OSI Layer | Definition |
|---|---|---|
| Router | Layer 3 | A device that connects multiple networks and forwards packets between them based on IP addresses and routing tables |
| Switch | Layer 2 (some Layer 3) | A device that connects multiple devices within a LAN and forwards frames based on MAC addresses |
| Firewall | Layers 3–7 | A security device that inspects and filters traffic based on configured rules, controlling what enters or exits a network |
| IDS (Intrusion Detection System) | Layers 3–7 | Monitors network traffic and generates alerts when suspicious or malicious activity is detected; does not block traffic |
| IPS (Intrusion Prevention System) | Layers 3–7 | Monitors network traffic and actively blocks or rejects detected threats in real time |
| Load Balancer | Layer 4–7 | Distributes incoming network traffic across multiple servers to ensure no single server is overwhelmed, improving availability and performance |
| Proxy Server | Layer 7 | Acts as an intermediary between clients and servers, providing anonymity, content filtering, and caching |
| NAS (Network Attached Storage) | Layer 7 | A file-level storage device connected directly to a network, accessible by multiple clients simultaneously |
| SAN (Storage Area Network) | Layer 2 | A high-speed, dedicated network that provides block-level storage access to servers, typically using Fibre Channel or iSCSI |

### Wireless Components

| Component | Definition |
|---|---|
| Access Point (AP) | A device that provides wireless (Wi-Fi) connectivity to clients and bridges wireless traffic to a wired network |
| Wireless Controller | A centralized device or software platform that manages the configuration, monitoring, and firmware of multiple access points simultaneously |

### Application-Level Functions

| Function | Definition |
|---|---|
| CDN (Content Delivery Network) | A geographically distributed group of servers that cache and deliver content to users from the nearest location, reducing latency and improving load times |
| VPN (Virtual Private Network) | Creates an encrypted, secure tunnel over a public network (such as the internet), allowing remote users to access private network resources safely |
| QoS (Quality of Service) | A set of techniques that prioritize certain types of traffic (e.g., VoIP calls) over less time-sensitive traffic (e.g., file downloads) to ensure performance |
| TTL (Time to Live) | A field in IP packets that limits the lifespan of a packet by decrementing a counter at each router hop; when it reaches zero, the packet is discarded to prevent infinite loops |

---

## 1.2 Cloud Networking Concepts

### Network Functions Virtualization (NFV)

**Definition:** NFV replaces traditional dedicated hardware appliances (such as firewalls, routers, and load balancers) with software-based equivalents running on standard servers or in the cloud. This reduces hardware costs and increases flexibility.

---

### Virtual Private Cloud (VPC)

**Definition:** A VPC is a logically isolated section of a public cloud provider's infrastructure where an organization can deploy resources in a private, controlled networking environment.

---

### Cloud Security Controls

| Control | Type | Definition |
|---|---|---|
| Security Groups | Stateful firewall | Virtual firewall rules applied at the instance level; return traffic is automatically permitted when outbound traffic is allowed |
| Network ACLs | Stateless firewall | Rules applied at the subnet level; both inbound and outbound rules must be explicitly defined as there is no state tracking |

---

### Cloud Gateway Types

| Gateway | Purpose |
|---|---|
| Internet Gateway | Enables resources in a VPC to communicate with the public internet |
| NAT Gateway | Allows instances in private subnets to initiate outbound internet connections without being directly reachable from the internet |

---

### Cloud Connectivity Options

| Option | Definition |
|---|---|
| VPN | An encrypted connection over the public internet between an on-premises network and a cloud environment |
| Direct Connect | A dedicated, private physical link between an organization's data center and a cloud provider, bypassing the public internet for improved speed and reliability |

---

### Cloud Deployment Models

| Model | Definition |
|---|---|
| Public Cloud | Infrastructure owned and operated by a cloud provider (e.g., AWS, Azure) and shared among multiple customers |
| Private Cloud | Infrastructure dedicated to a single organization, hosted either on-premises or by a third party |
| Hybrid Cloud | A combination of public and private cloud environments that are integrated to allow data and applications to move between them |

---

### Cloud Service Models

| Model | Full Name | Definition | Example |
|---|---|---|---|
| SaaS | Software as a Service | Fully managed software applications delivered over the internet | Gmail, Microsoft 365 |
| PaaS | Platform as a Service | A platform providing tools and infrastructure for developers to build and deploy applications | AWS Elastic Beanstalk, Heroku |
| IaaS | Infrastructure as a Service | Virtualized computing resources including servers, storage, and networking, delivered on demand | AWS EC2, Microsoft Azure VMs |

---

### Cloud Key Concepts

| Concept | Definition |
|---|---|
| Scalability | The ability to increase or decrease resources to meet demand, typically through manual or planned adjustment |
| Elasticity | The ability to automatically scale resources up or down in real time in response to changing workloads |
| Multitenancy | A cloud architecture where multiple customers share the same underlying physical infrastructure while remaining logically isolated from one another |

---

## 1.3 Ports, Protocols, and Services

### Common Ports and Protocols

| Protocol / Service | Port(s) | Transport | Description |
|---|---|---|---|
| FTP (File Transfer Protocol) | 20 / 21 | TCP | Transfers files between client and server; port 21 is for control, port 20 for data |
| SSH (Secure Shell) / SFTP | 22 | TCP | Encrypted remote access and secure file transfer |
| Telnet | 23 | TCP | Unencrypted remote access; largely replaced by SSH |
| SMTP (Simple Mail Transfer Protocol) | 25 | TCP | Sends email between mail servers |
| DNS (Domain Name System) | 53 | TCP/UDP | Resolves hostnames to IP addresses |
| DHCP (Dynamic Host Configuration Protocol) | 67 / 68 | UDP | Port 67 for server, port 68 for client; dynamically assigns IP configuration |
| TFTP (Trivial File Transfer Protocol) | 69 | UDP | Lightweight file transfer with no authentication; used for device firmware upgrades |
| HTTP (Hypertext Transfer Protocol) | 80 | TCP | Unencrypted web traffic |
| NTP (Network Time Protocol) | 123 | UDP | Synchronizes clocks across network devices |
| SNMP (Simple Network Management Protocol) | 161 / 162 | UDP | Port 161 for queries; port 162 for traps (alerts sent to management station) |
| LDAP (Lightweight Directory Access Protocol) | 389 | TCP/UDP | Accesses and manages directory services (e.g., Active Directory) |
| HTTPS (HTTP Secure) | 443 | TCP | Encrypted web traffic using TLS |
| SMB (Server Message Block) | 445 | TCP | File and printer sharing on Windows networks |
| Syslog | 514 | UDP | Sends system log messages to a centralized log server |
| SMTPS (SMTP Secure) | 587 | TCP | Encrypted email submission from client to mail server |
| LDAPS (LDAP Secure) | 636 | TCP | Encrypted LDAP communication |
| SQL Server | 1433 | TCP | Microsoft SQL Server database communication |
| RDP (Remote Desktop Protocol) | 3389 | TCP | Provides graphical remote desktop access to Windows systems |
| SIP (Session Initiation Protocol) | 5060 / 5061 | TCP/UDP | Initiates and terminates VoIP sessions; port 5061 for TLS-encrypted SIP |

---

### IP Protocol Types

| Protocol | Definition |
|---|---|
| ICMP (Internet Control Message Protocol) | Used for error reporting and diagnostic functions such as ping and traceroute |
| TCP (Transmission Control Protocol) | A connection-oriented protocol that guarantees reliable, ordered delivery of data using handshaking and acknowledgments |
| UDP (User Datagram Protocol) | A connectionless protocol that transmits data quickly with no guaranteed delivery, suitable for real-time applications |
| GRE (Generic Routing Encapsulation) | A tunneling protocol that encapsulates a wide variety of network layer protocols within point-to-point virtual links |
| IPSec AH (Authentication Header) | Provides data integrity and authentication for IP packets but does not encrypt the payload |
| IPSec ESP (Encapsulating Security Payload) | Provides encryption, data integrity, and authentication for IP packets |
| IPSec IKE (Internet Key Exchange) | Negotiates and manages cryptographic keys and security associations for IPSec connections |

---

### Traffic Types

| Type | Definition |
|---|---|
| Unicast | A one-to-one transmission where a packet is sent from a single source to a single specific destination |
| Broadcast | A one-to-all transmission where a packet is sent to all devices within a network segment |
| Multicast | A one-to-many transmission where a packet is sent to a defined group of interested receivers simultaneously |
| Anycast | A routing method where a packet is delivered to the topologically nearest node from a group of potential receivers sharing the same address |

---

## 1.4 Transmission Media and Transceivers

### Wireless Media

| Technology | Description |
|---|---|
| 802.11 (Wi-Fi) | The IEEE standard for wireless LAN communication, available in multiple generations (802.11a/b/g/n/ac/ax) |
| Cellular (4G/5G) | Wide-area wireless communication through mobile carrier infrastructure |
| Satellite | Global wireless communication via satellite in orbit; high latency but wide geographic coverage |

### Wired Media

| Type | Sub-type | Description |
|---|---|---|
| Ethernet (802.3) | — | The dominant standard for wired LAN communication over copper and fiber |
| Fiber Optic | Single-mode (SMF) | Uses a single light path; supports long distances (up to 100 km+); narrower core; used in WANs and data center interconnects |
| Fiber Optic | Multimode (MMF) | Uses multiple light paths simultaneously; supports shorter distances; wider core; used within buildings and campuses |
| Copper | Coaxial | A shielded cable with a central conductor used in older Ethernet installations and cable TV |
| Copper | Twinax (DAC) | Direct Attach Copper cables using twin-axial construction; used for short-range, high-speed connections in data centers |

### Transceivers

| Type | Full Name | Description |
|---|---|---|
| SFP | Small Form-factor Pluggable | A compact, hot-swappable transceiver used for 1 Gbps fiber or copper connections |
| SFP+ | Enhanced SFP | Supports 10 Gbps; physically identical to SFP but not backward compatible for speed |
| QSFP | Quad Small Form-factor Pluggable | Supports 40 Gbps or higher by combining four lanes; used in high-speed data center environments |

### Connector Types

| Connector | Used With | Description |
|---|---|---|
| RJ-45 | Ethernet (copper) | The standard 8-pin connector used for twisted-pair Ethernet cables |
| RJ-11 | Telephone | A 6-pin connector used for telephone and DSL connections |
| LC | Fiber optic | A small form-factor fiber connector used in high-density environments |
| SC | Fiber optic | A push-pull fiber connector commonly used in enterprise networking |
| ST | Fiber optic | A bayonet-style fiber connector used in older installations |
| BNC | Coaxial | A twist-lock connector used with coaxial cable in legacy Ethernet and test equipment |
| F-type | Coaxial (cable TV) | A threaded connector used for cable television and broadband cable modems |

---

## 1.5 Network Topologies and Architectures

### Physical and Logical Topologies

| Topology | Description |
|---|---|
| Mesh | Every device connects to every other device; provides maximum redundancy; used in WANs and wireless backhaul |
| Star | All devices connect to a central device (switch or hub); the most common LAN topology; single point of failure at the center |
| Hybrid | A combination of two or more topology types used to meet specific performance or redundancy requirements |
| Spine-Leaf | A two-tier data center architecture where every leaf switch connects to every spine switch; provides predictable latency and easy scalability |
| Point-to-Point | A direct dedicated link between exactly two nodes |

### Three-Tier Hierarchical Network Model

| Tier | Name | Role |
|---|---|---|
| Tier 1 | Core | High-speed backbone of the network; routes traffic between distribution layers; optimized for speed, not policy enforcement |
| Tier 2 | Distribution | Aggregates access layer connections; enforces routing policies, ACLs, and QoS; separates core from access |
| Tier 3 | Access | Connects end devices (computers, phones, printers) to the network; provides port security and VLAN assignment |

### Traffic Flow Patterns

| Pattern | Description |
|---|---|
| North-South | Traffic flowing between clients and servers (into or out of a data center); traditionally the dominant traffic pattern |
| East-West | Traffic flowing between servers within a data center; has grown significantly with virtualization and microservices architectures |

---

## 1.6 IPv4 Addressing

### Public vs. Private Address Spaces

| Type | Range | Description |
|---|---|---|
| Private (Class A) | 10.0.0.0 – 10.255.255.255 (/8) | Large private networks; 16 million addresses |
| Private (Class B) | 172.16.0.0 – 172.31.255.255 (/12) | Medium private networks |
| Private (Class C) | 192.168.0.0 – 192.168.255.255 (/16) | Small private networks; most common in home and small office environments |
| APIPA | 169.254.0.0 – 169.254.255.255 | Automatically assigned when a device cannot reach a DHCP server; not routable |
| Loopback | 127.0.0.1 | Used to test the local TCP/IP stack; traffic never leaves the device |

### IPv4 Address Classes

| Class | Range | Default Subnet Mask | Use |
|---|---|---|---|
| A | 1.0.0.0 – 126.255.255.255 | /8 (255.0.0.0) | Large organizations; supports ~16 million hosts per network |
| B | 128.0.0.0 – 191.255.255.255 | /16 (255.255.0.0) | Medium organizations; supports ~65,000 hosts per network |
| C | 192.0.0.0 – 223.255.255.255 | /24 (255.255.255.0) | Small organizations; supports 254 hosts per network |
| D | 224.0.0.0 – 239.255.255.255 | N/A | Reserved for multicast group addressing |
| E | 240.0.0.0 – 255.255.255.255 | N/A | Reserved for experimental use |

### Subnetting Concepts

| Concept | Definition |
|---|---|
| CIDR (Classless Inter-Domain Routing) | A method of allocating IP addresses using variable-length subnet masks (e.g., /26), replacing rigid class-based addressing to reduce waste |
| VLSM (Variable Length Subnet Masking) | An extension of CIDR that allows different subnets within the same network to use different subnet mask lengths, enabling more efficient use of address space |

---

## 1.7 Modern Network Use Cases

### Software-Defined Networking (SDN) and SD-WAN

**Definition:** SDN separates the control plane (the decision-making component) from the data plane (the packet-forwarding component), allowing a centralized software controller to manage network behavior across all devices rather than configuring each device individually.

**Definition:** SD-WAN applies SDN principles to wide area networks, intelligently routing traffic across multiple transport types (MPLS, broadband, LTE/5G) based on application requirements and link conditions.

| Feature | Description |
|---|---|
| Application-aware routing | Traffic is routed based on the application type; critical applications (e.g., VoIP) receive priority paths automatically |
| Zero-touch provisioning (ZTP) | New devices automatically download and apply their configuration when connected, requiring no manual setup |
| Transport agnostic | Functions over any available connection type (MPLS, broadband, LTE) without dependence on a single provider |
| Centralized policy management | All network policies are defined and pushed from a single management dashboard to all connected devices |

---

### VXLAN (Virtual Extensible LAN)

**Definition:** VXLAN is a network virtualization technology that encapsulates Layer 2 Ethernet frames within Layer 3 UDP packets, allowing Layer 2 networks to be extended across Layer 3 infrastructure.

| Feature | Description |
|---|---|
| Segment scale | Supports up to 16 million virtual network segments (VNIs), compared to the 4,096 VLAN limit of traditional 802.1Q |
| Data Center Interconnect (DCI) | Connects geographically separate data centers over IP networks while maintaining Layer 2 adjacency |
| VM mobility | Enables virtual machines to migrate between data centers or physical hosts without changing their IP or MAC address |

---

### Zero Trust Architecture (ZTA)

**Definition:** Zero Trust is a security model based on the principle of "never trust, always verify." No user, device, or network segment is trusted by default, regardless of whether it is inside or outside the corporate network perimeter.

| Principle | Description |
|---|---|
| Policy-based authentication | Access decisions are made based on verified identity, device health, location, and other contextual factors |
| Least privilege access | Users and devices are granted only the minimum permissions required to perform their function, reducing the potential impact of a breach |
| Continuous verification | Trust is not assumed after initial authentication; access is continuously evaluated throughout a session |

---

### SASE and SSE

| Framework | Full Name | Definition |
|---|---|---|
| SASE | Secure Access Service Edge | A cloud-delivered architecture that combines wide-area networking (SD-WAN) with comprehensive security services (firewall, CASB, ZTNA) into a single, unified service |
| SSE | Security Service Edge | A subset of SASE that focuses exclusively on the security components (CASB, SWG, ZTNA), without the networking functions |

Both frameworks support remote workforces and cloud-first organizations by replacing traditional perimeter-based security with identity-aware, cloud-delivered controls.

---

### Infrastructure as Code (IaC)

**Definition:** IaC is the practice of managing and provisioning infrastructure resources (servers, networks, storage) through machine-readable configuration files rather than through manual processes or interactive configuration tools.

| Feature | Description |
|---|---|
| Automation | Infrastructure is deployed and configured automatically from code, eliminating manual intervention |
| Playbooks and templates | Reusable configuration files (e.g., Ansible playbooks, Terraform templates) define the desired state of infrastructure |
| Configuration drift detection | IaC tools continuously compare actual infrastructure state against the defined state and alert on or correct unauthorized changes |
| Version control integration | Infrastructure code is stored in repositories (e.g., GitHub), enabling change tracking, rollback, and team collaboration |
| Branching | Changes can be tested in isolated branches before being merged to production, reducing risk |

---

### IPv6 Addressing

**Definition:** IPv6 is the sixth version of the Internet Protocol, using 128-bit addresses (compared to IPv4's 32-bit) to provide an effectively unlimited address space. It was developed to address IPv4 exhaustion.

| Feature | Description |
|---|---|
| Address space | 128-bit addresses provide 340 undecillion (3.4 x 10^38) unique addresses |
| No NAT required | Every device can have a globally unique address, enabling true end-to-end connectivity |
| Built-in IPSec support | IPv6 was designed with IPSec integration, improving baseline security |
| Simplified header | The IPv6 header is more efficient than IPv4, improving routing performance |

### IPv4 to IPv6 Transition Techniques

| Technique | Definition |
|---|---|
| Dual Stack | A device runs both IPv4 and IPv6 simultaneously, using whichever protocol the destination supports |
| Tunneling | IPv6 packets are encapsulated inside IPv4 packets to traverse IPv4-only infrastructure |
| NAT64 | Translates between IPv6 and IPv4 at the network boundary, allowing IPv6-only clients to communicate with IPv4-only servers. It does not convert an entire network — it performs address translation at the protocol boundary |

---

## Summary Reference Table

| Topic | Key Concepts | Key Technologies |
|---|---|---|
| OSI Model | 7 layers; each layer has a defined role | TCP/IP, Ethernet, HTTP, TLS |
| Network Appliances | Routers, switches, firewalls, IDS/IPS, load balancers | Hardware and virtualized appliances |
| Cloud Concepts | VPC, security groups, NAT gateway, service models | SaaS, PaaS, IaaS, NFV |
| Ports and Protocols | Common port numbers and their associated services | TCP/UDP, ICMP, IPSec |
| Transmission Media | Fiber, copper, wireless; connectors and transceivers | SFP, QSFP, RJ-45, LC, SC |
| Topologies | Star, mesh, spine-leaf, three-tier model | Ethernet switching, routing |
| IPv4 Addressing | Private ranges, classes, CIDR, VLSM, APIPA | RFC 1918, subnetting |
| SDN / SD-WAN | Separated control/data planes; intelligent WAN routing | SD-WAN, ZTP, MPLS |
| VXLAN | Layer 2 over Layer 3; 16M segments | UDP encapsulation, VNI |
| Zero Trust | Never trust, always verify; least privilege | ZTNA, identity-based access |
| SASE / SSE | Cloud-delivered security and networking | CASB, SWG, SD-WAN |
| IaC | Infrastructure managed through code | Ansible, Terraform, GitHub |
| IPv6 | 128-bit addressing; replaces IPv4 | Dual stack, tunneling, NAT64 |
