# Network+ Notes — Domain 3.0: Network Operations

---

## 3.1 Organizational Processes and Procedures

### Network Documentation

**Definition:** Network documentation is the collection of diagrams, records, and reference materials that describe the design, configuration, and physical layout of a network. It supports troubleshooting, onboarding, auditing, and change management.

#### Diagram Types

| Diagram Type | Description |
|---|---|
| Physical Diagram | Represents the actual physical layout of the network, including cable runs, hardware locations, rack positions, and port connections |
| Logical Diagram | Represents the abstract structure of the network, including IP addressing schemes, VLANs, routing boundaries, and traffic flows without reference to physical location |
| Rack Diagram | A scaled visual representation of equipment installed within a rack enclosure, showing device placement, rack unit (U) positioning, and cabling, used for installation planning and airflow management |
| Cable Map | Documents every cable connection between devices, including cable type, length, origin port, and destination port; essential for resolving Layer 1 issues |

#### Network Diagrams by OSI Layer

| Layer | Focus |
|---|---|
| Layer 1 (Physical) | Cable types, connector types, physical port connections, hardware locations |
| Layer 2 (Data Link) | Switch connections, VLAN assignments, trunk links, spanning tree topology |
| Layer 3 (Network) | Router interfaces, IP addressing, subnet boundaries, routing protocol relationships |

---

### Asset Inventory

**Definition:** An asset inventory is a comprehensive record of all hardware, software, and licensing resources within an organization's network infrastructure. It enables lifecycle tracking, support planning, and compliance auditing.

| Asset Category | Examples |
|---|---|
| Hardware | Routers, switches, firewalls, access points, servers, cabling infrastructure |
| Software | Operating systems, network management platforms, security tools, applications |
| Licensing | Software license keys, subscription renewal dates, seat counts |
| Warranty and Support | Vendor support contract numbers, expiration dates, hardware replacement entitlements |

---

### IP Address Management (IPAM)

**Definition:** IPAM is a method of planning, tracking, and managing the allocation of IP address space within a network. It prevents IP conflicts, provides visibility into address utilization, and assists with subnet design.

| Function | Description |
|---|---|
| Address tracking | Records which IP addresses are assigned, to which devices, and when leases expire |
| Conflict prevention | Identifies duplicate IP assignments before they cause connectivity issues |
| Subnet planning | Visualizes available and exhausted subnets to support network growth planning |

---

### Service Level Agreement (SLA)

**Definition:** An SLA is a formal contract between a service provider and a customer that defines the expected level of service, including uptime guarantees, performance benchmarks, response times for incidents, and the penalties or remedies if those standards are not met.

| SLA Component | Description |
|---|---|
| Uptime / Availability | Expressed as a percentage (e.g., 99.9% uptime = approximately 8.7 hours of downtime per year) |
| Response time | The maximum time the provider will take to acknowledge a reported issue |
| Resolution time | The maximum time the provider will take to fully resolve a reported issue |
| Penalties | Financial credits or other remedies applied when SLA targets are not met |

---

### Wireless Site Survey and Heat Map

**Definition:** A wireless site survey is the process of planning and analyzing the deployment of a wireless network. A heat map is the visual output of a survey, displaying signal strength, coverage areas, and dead zones across a floor plan.

**Purpose:** Ensures optimal access point placement for coverage, capacity, and minimal interference before and after deployment.

---

### Life-Cycle Management

**Definition:** Life-cycle management is the process of tracking and managing network hardware and software through every stage of its operational life, from procurement to decommissioning.

| Stage | Definition |
|---|---|
| EOL (End-of-Life) | The date after which the vendor no longer sells or manufactures the product. Hardware or software past EOL should be scheduled for replacement |
| EOS (End-of-Support) | The date after which the vendor no longer provides patches, security updates, or technical support. Devices past EOS represent a security and compliance risk |
| Patch Management | The process of regularly applying vendor-released patches to fix security vulnerabilities and software defects |
| OS Updates | Scheduled updates to operating systems that improve performance, stability, and security |
| Firmware Updates | Updates applied to the hardware-embedded software of network devices (switches, APs, firewalls) to address bugs and vulnerabilities |
| Decommissioning | The process of safely removing a device from service, including data sanitization (wiping), physical removal, asset record updates, and responsible disposal |

---

### Change Management

**Definition:** Change management is a formal organizational process for requesting, reviewing, approving, implementing, and documenting changes to the network or IT infrastructure. It reduces the risk of unplanned outages caused by poorly planned changes.

| Component | Description |
|---|---|
| Change request | A formal submission describing the proposed change, its purpose, affected systems, and rollback plan |
| Approval process | Review by a change advisory board (CAB) or designated approvers before implementation |
| Maintenance window | A scheduled period of low activity during which the change is applied to minimize user impact |
| Rollback plan | A documented procedure to reverse the change if it causes unexpected problems |
| Post-change documentation | Updated records reflecting the new configuration or topology after a successful change |

---

### Configuration Management

**Definition:** Configuration management is the practice of systematically maintaining and controlling the configurations of network devices to ensure consistency, accuracy, and the ability to recover from failures.

| Configuration Type | Definition |
|---|---|
| Production configuration | The currently active, running configuration on a device; what the device is using right now |
| Backup configuration | A saved copy of a device's configuration, stored off-device, used to restore settings after a failure or misconfiguration |
| Baseline (Golden configuration) | A vetted, approved template configuration representing the standard, secure setup for a device type; used as the reference for auditing and provisioning new devices |

---

## 3.2 Network Monitoring Technologies

### SNMP (Simple Network Management Protocol)

**Definition:** SNMP is an application-layer protocol used to monitor and manage network devices. A network management system (NMS) uses SNMP to query devices for performance data, receive alerts, and in some cases modify device configuration.

| Component | Definition |
|---|---|
| SNMP Manager | The central system (NMS) that polls devices and receives alerts |
| SNMP Agent | Software running on a managed device that responds to manager queries and sends traps |
| MIB (Management Information Base) | A structured database that defines all the variables a device exposes via SNMP, organized in a hierarchical tree using object identifiers (OIDs) |
| Trap | An unsolicited alert sent by a device to the SNMP manager when a specific event occurs (e.g., interface goes down, temperature threshold exceeded) |
| Community String | A text string acting as a simple authentication credential in SNMPv1 and v2c; read-only and read-write communities are common |

#### SNMP Versions

| Version | Security | Description |
|---|---|---|
| SNMPv1 | None | Original version; uses cleartext community strings; not recommended for production |
| SNMPv2c | None | Improved performance and error handling over v1; still uses cleartext community strings |
| SNMPv3 | Authentication + Encryption | Adds user-based authentication (MD5/SHA) and data encryption (AES/DES); the recommended version for secure environments |

---

### Flow Data

**Definition:** Flow data provides a summary of network traffic conversations, recording source IP, destination IP, ports, protocol, and byte counts without capturing the actual packet contents. It is used for traffic analysis, capacity planning, and anomaly detection.

| Protocol | Description |
|---|---|
| NetFlow | A Cisco-developed protocol that exports flow records from routers and switches to a flow collector for analysis |
| sFlow | A sampling-based flow protocol that captures a statistical sample of traffic rather than all flows; scales better on high-throughput links |
| IPFIX | The IETF standard version of NetFlow (Internet Protocol Flow Information Export); vendor-neutral |

---

### Packet Capture

**Definition:** Packet capture is the process of intercepting and recording raw network traffic at the frame or packet level for detailed inspection and analysis.

| Tool | Description |
|---|---|
| Wireshark | An open-source graphical packet analyzer that captures and decodes traffic across hundreds of protocols |
| tcpdump | A command-line packet capture tool for Linux and macOS; lightweight and suitable for remote use |

---

### Baseline Metrics

**Definition:** A performance baseline is a recorded measurement of normal network behavior — including bandwidth utilization, latency, error rates, and CPU usage — captured during typical operating conditions. Baselines serve as a reference point for detecting anomalies.

**Anomaly Detection:** Monitoring systems compare real-time metrics against the established baseline and generate alerts when values deviate significantly, indicating potential failures, attacks, or capacity issues.

---

### Log Aggregation and Analysis

| Component | Definition |
|---|---|
| Syslog | A standard protocol (UDP port 514) used by network devices to send event and status log messages to a centralized syslog server |
| Syslog Collector | A server that receives, stores, and organizes syslog messages from multiple network devices for review and archival |
| SIEM (Security Information and Event Management) | A platform that aggregates log data from multiple sources (firewalls, switches, servers, endpoints), correlates events across systems, and generates alerts for suspicious or malicious activity |

---

### Additional Monitoring Technologies

| Technology | Definition |
|---|---|
| Port Mirroring (SPAN) | A switch feature that copies all traffic passing through a specified port or VLAN and sends a duplicate to a designated monitoring port connected to a packet analyzer or IDS |
| API Integration | Monitoring tools can consume vendor APIs to collect device data, trigger actions, and integrate with automation platforms without requiring SNMP |

---

## 3.3 Disaster Recovery

### Key DR Metrics

| Metric | Full Name | Definition |
|---|---|---|
| RPO | Recovery Point Objective | The maximum amount of data loss an organization can tolerate, expressed as a time interval (e.g., RPO of 4 hours means backups must occur at least every 4 hours) |
| RTO | Recovery Time Objective | The maximum acceptable length of time to restore a system or service to full operation after a failure |
| MTTR | Mean Time to Repair | The average time required to diagnose and repair a failed component or system |
| MTBF | Mean Time Between Failures | The average time a system or component operates without failure; used to predict reliability and plan maintenance |

---

### Disaster Recovery Site Types

| Site Type | Setup Level | Recovery Speed | Cost | Description |
|---|---|---|---|---|
| Cold Site | Minimal | Slow (days to weeks) | Low | A physical facility with basic infrastructure (power, cooling, space) but no pre-installed equipment or data. Hardware must be sourced and configured after a disaster |
| Warm Site | Partial | Moderate (hours to days) | Medium | A facility with hardware already installed and partially configured. Data must be restored from backups before operations can resume |
| Hot Site | Full | Fast (minutes to hours) | High | A fully operational duplicate of the production environment with live data replication. Can take over immediately upon failover |

---

### High Availability Configurations

| Model | Description |
|---|---|
| Active-Active | All nodes are operational simultaneously and share the traffic load. If one node fails, the remaining nodes absorb its traffic with minimal disruption |
| Active-Passive | A primary node handles all traffic while a secondary node remains on standby. The standby node activates only when the primary fails |

---

### DR Testing Methods

| Method | Description |
|---|---|
| Tabletop Exercise | A discussion-based test where key stakeholders walk through a disaster scenario verbally to identify gaps in the plan without making any changes to live systems |
| Functional / Validation Test | An actual execution of recovery procedures, which may involve activating the DR site, restoring backups, or failing over services to verify the plan works as documented |

---

## 3.4 Network Services

### DHCP (Dynamic Host Configuration Protocol)

**Definition:** DHCP is an application-layer protocol that automatically assigns IP addresses and network configuration parameters to devices on a network, eliminating the need for manual IP address assignment.

| Concept | Definition |
|---|---|
| Scope | The defined range of IP addresses a DHCP server is configured to assign to clients on a given subnet |
| Lease Time | The duration for which an IP address is assigned to a client. When the lease expires, the client must renew it or obtain a new address |
| Reservation | A configuration that permanently maps a specific IP address to a device's MAC address, ensuring that device always receives the same IP |
| Exclusion | An IP address or range within a scope that is excluded from dynamic assignment, typically reserved for statically configured devices |
| DHCP Options | Additional configuration parameters delivered alongside the IP address, including default gateway (Option 3), DNS server (Option 6), and domain name (Option 15) |
| DHCP Relay (IP Helper) | A configuration on a router that forwards DHCP broadcast requests from clients on one subnet to a DHCP server on a different subnet. Without a relay, DHCP broadcasts cannot cross router boundaries |

#### DHCP Process (DORA)

| Step | Name | Description |
|---|---|---|
| 1 | Discover | Client broadcasts a request to find available DHCP servers |
| 2 | Offer | DHCP server responds with an available IP address and configuration |
| 3 | Request | Client broadcasts acceptance of the offered IP address |
| 4 | Acknowledge | DHCP server confirms the lease and delivers full configuration options |

---

### SLAAC (Stateless Address Autoconfiguration)

**Definition:** SLAAC is an IPv6 mechanism that allows a device to automatically generate its own IPv6 address without a DHCP server. The device uses the network prefix advertised by a local router and combines it with its own interface identifier (derived from its MAC address or randomly generated) to form a complete 128-bit address.

---

### DNS (Domain Name System)

**Definition:** DNS is a hierarchical, distributed naming system that translates human-readable hostnames (e.g., www.example.com) into IP addresses that routers can use to forward traffic.

#### DNS Record Types

| Record | Description |
|---|---|
| A | Maps a hostname to an IPv4 address |
| AAAA | Maps a hostname to an IPv6 address |
| CNAME (Canonical Name) | Creates an alias that points one hostname to another hostname |
| MX (Mail Exchange) | Specifies the mail servers responsible for accepting email for a domain |
| TXT | Stores arbitrary text data; commonly used for domain verification and email security records (SPF, DKIM, DMARC) |
| NS (Name Server) | Identifies the authoritative name servers for a domain |
| PTR (Pointer) | Maps an IP address back to a hostname; used for reverse DNS lookups |
| SOA (Start of Authority) | Contains administrative information about a DNS zone, including the primary name server and zone serial number |

#### DNS Zone Types

| Zone Type | Description |
|---|---|
| Forward Lookup Zone | Resolves hostnames to IP addresses (the standard direction of DNS resolution) |
| Reverse Lookup Zone | Resolves IP addresses back to hostnames using PTR records |
| Authoritative Zone | A DNS server that holds the original, definitive records for a domain and responds with its own data |
| Non-authoritative (Cached) | A DNS server that returns previously cached answers obtained from an authoritative server; may be slightly out of date |

#### DNS Resolution Types

| Type | Description |
|---|---|
| Recursive Resolution | The DNS resolver takes full responsibility for resolving a query on behalf of the client, contacting other DNS servers as needed until it obtains a definitive answer |
| Iterative Resolution | The DNS server returns the best answer it currently has (such as a referral to another server) and the client is responsible for following up |

#### DNS Security

| Technology | Definition |
|---|---|
| DNSSEC (DNS Security Extensions) | Adds cryptographic signatures to DNS records, allowing resolvers to verify that responses have not been tampered with or forged |
| DoH (DNS over HTTPS) | Encrypts DNS queries within HTTPS traffic (port 443), preventing eavesdropping and manipulation of DNS requests |
| DoT (DNS over TLS) | Encrypts DNS queries using TLS on a dedicated port (853), providing confidentiality and integrity for DNS traffic |

---

### Hosts File

**Definition:** The hosts file is a local text file on an operating system that manually maps hostnames to IP addresses. Entries in the hosts file are consulted before DNS queries are made, allowing local overrides of DNS resolution for testing or access control purposes.

- **Windows location:** `C:\Windows\System32\drivers\etc\hosts`
- **Linux/macOS location:** `/etc/hosts`

---

### Time Protocols

| Protocol | Full Name | Description |
|---|---|---|
| NTP | Network Time Protocol | Synchronizes the clocks of network devices to a reference time source over UDP port 123; accurate to within milliseconds |
| PTP | Precision Time Protocol (IEEE 1588) | Provides sub-microsecond time synchronization; used in environments requiring extremely precise timing such as financial trading systems, telecommunications, and industrial control |
| NTS | Network Time Security | An extension to NTP that adds cryptographic authentication, ensuring that time synchronization responses come from a legitimate and unmodified source |

---

## 3.5 Network Access and Management

### VPN Types

**Definition:** A VPN (Virtual Private Network) creates an encrypted, logical connection over a public or untrusted network, allowing secure communication between endpoints.

| VPN Type | Description |
|---|---|
| Site-to-Site VPN | A permanent encrypted tunnel between two network gateways (e.g., two office locations), connecting entire networks to each other transparently |
| Client-to-Site VPN | A VPN connection initiated by an individual remote user's device to connect securely to the corporate network; requires VPN client software |
| Clientless VPN | A browser-based VPN that provides access to specific internal web applications without requiring a dedicated VPN client to be installed on the user's device |
| Split Tunnel | Only traffic destined for the corporate network is routed through the VPN; all other internet traffic goes directly to the internet. Reduces VPN load but provides less control |
| Full Tunnel | All traffic from the client device is routed through the VPN, regardless of destination. Provides maximum visibility and control but increases VPN bandwidth consumption |

---

### Management Methods

| Method | Description |
|---|---|
| SSH (Secure Shell) | An encrypted protocol for remote command-line access to network devices over port 22; the standard replacement for unencrypted Telnet |
| GUI (Graphical User Interface) | Web-based or application-based management interfaces that provide visual dashboards and point-and-click configuration; suited for less experienced administrators or complex visual tasks |
| API (Application Programming Interface) | Allows programmatic interaction with network devices and management platforms for automation, scripting, and integration with orchestration systems |
| Console Access | Direct physical connection to a device's console port using a serial cable; used for initial setup or when network access to the device is unavailable |

---

### Jump Server (Jump Box)

**Definition:** A jump server (also called a bastion host) is a hardened, dedicated server that acts as a secure intermediary access point between an administrator and devices in a protected network segment. Administrators first authenticate to the jump server, then connect from it to internal devices, ensuring all administrative traffic passes through a single, audited, and controlled point.

---

### In-Band vs. Out-of-Band Management

| Method | Definition | Advantage | Risk |
|---|---|---|---|
| In-band management | Administrative traffic travels over the same network infrastructure used for production data (e.g., SSH over the production LAN) | Simple; no additional infrastructure required | If the production network is down or compromised, management access is also lost |
| Out-of-band management | A dedicated, separate network path (e.g., a management VLAN, serial console server, or cellular modem) is used exclusively for administrative access | Access remains available even when the production network is down | Requires additional infrastructure and cost |

---

## Summary Reference Table

| Section | Key Topics | Key Technologies |
|---|---|---|
| Documentation | Physical/logical diagrams, rack diagrams, cable maps | IPAM, asset inventory |
| Life-Cycle Management | EOL, EOS, patching, decommissioning | Firmware updates, data wiping |
| Change Management | Formal approval, rollback plans, maintenance windows | CAB, change request process |
| Configuration Management | Production, backup, and baseline configs | Golden config, version control |
| Network Monitoring | SNMP traps, MIB, flow data, packet capture | SNMPv3, NetFlow, Wireshark, SIEM |
| Disaster Recovery | RPO, RTO, MTTR, MTBF, site types | Hot/warm/cold site, active-active/passive |
| DHCP | Scopes, leases, reservations, relay | DORA process, IP helper |
| DNS | Record types, zones, security extensions | DNSSEC, DoH, DoT, PTR, MX |
| Time Protocols | Clock synchronization, precision timing | NTP, PTP, NTS |
| VPN | Site-to-site, client-to-site, tunnel types | Split/full tunnel, clientless VPN |
| Management Methods | CLI, GUI, API, console, jump server | SSH, out-of-band management |
