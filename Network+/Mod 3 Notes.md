Network+ Notes – Domain 3: Network Operations
📄 3.1 Organizational Processes & Procedures
🔹 Documentation
Network Documentation
📌 Purpose:

Provides visibility, troubleshooting support, and standardization

🔸 Physical vs Logical Diagrams
Physical → Shows cables, racks, hardware
Logical → Shows IPs, VLANs, traffic flow
🔸 Rack Diagrams
Layout of devices inside racks
Helps with installation & airflow planning
🔸 Cable Maps
Shows cable connections between devices
Helps in troubleshooting Layer 1 issues
🔸 Network Diagrams
Layer 1 → Physical connections
Layer 2 → Switching, VLANs
Layer 3 → Routing, IP addressing
🔹 Asset Inventory
Asset Inventory

Tracks all resources:

Hardware → routers, switches
Software → OS, applications
Licensing → subscription tracking
Warranty → support contracts
🔹 IP Address Management (IPAM)
IP Address Management
Tracks IP usage
Prevents conflicts
Helps in subnet planning
🔹 SLA (Service-Level Agreement)
Service Level Agreement
Defines uptime, response time
Agreement between provider & customer
🔹 Wireless Survey / Heat Map
Shows signal strength
Helps optimize AP placement
🔄 Life-Cycle Management
🔸 EOL (End-of-Life)
Product no longer sold
🔸 EOS (End-of-Support)
No more updates/support
🔸 Software Management
Patches → Fix vulnerabilities
OS updates → Improve performance
Firmware → Hardware-level updates
🔸 Decommissioning
Safely removing devices
Data wiping is critical
🔄 Change Management
Change Management
Formal process for making changes
Includes approval + tracking
⚙️ Configuration Management
Production config → Current running setup
Backup config → Saved version
Baseline (Golden config) → Standard template
📡 3.2 Network Monitoring Technologies
🔹 SNMP (Simple Network Management Protocol)
SNMP
Features:
Monitors devices
Collects performance data
🔸 Traps
Alerts sent automatically
🔸 MIB (Management Information Base)
Database of device info
🔸 Versions
v2c → Community-based
v3 → Secure (authentication + encryption)
🔸 Community Strings
Like passwords for SNMP
🔹 Flow Data
Tracks traffic patterns (NetFlow)
🔹 Packet Capture
Captures packets for analysis (Wireshark)
🔹 Baseline Metrics
Normal network performance values
🔸 Anomaly Detection
Alerts when behavior deviates
🔹 Log Aggregation
🔸 Syslog Collector
Syslog
Central log storage
🔸 SIEM
Security Information and Event Management
Correlates logs
Detects threats
🔹 API Integration
Automates monitoring tools
🔹 Port Mirroring
Copies traffic to monitoring system
💥 3.3 Disaster Recovery (DR)
🔹 DR Metrics
Metric	Meaning
RPO	Data loss tolerance
RTO	Recovery time
MTTR	Repair time
MTBF	Time between failures
🔹 DR Sites
Cold Site → Empty, slow setup
Warm Site → Partial setup
Hot Site → Fully ready
🔹 High Availability
Active-Active → Both running
Active-Passive → Backup standby
🔹 Testing
Tabletop → Discussion-based
Validation → Real testing
🌐 3.4 Network Services (IPv4 & IPv6)
🔹 DHCP
DHCP
Features:
Assigns IP automatically
🔸 Key Concepts:
Reservation → Fixed IP
Scope → Range of IPs
Lease time → Duration
Options → DNS, gateway
🔸 DHCP Relay (IP Helper)
Forwards DHCP requests across networks
🔸 Exclusions
Reserved IPs not assigned
🔹 SLAAC (IPv6)
Auto-configures IPv6 without DHCP
🔹 DNS
DNS
🔸 Security:
DNSSEC → Prevents spoofing
DoH / DoT → Encrypted DNS
🔸 Record Types:
A → IPv4
AAAA → IPv6
CNAME → Alias
MX → Mail server
TXT → Info
NS → Name server
PTR → Reverse lookup
🔸 Zones:
Forward → Name → IP
Reverse → IP → Name
🔸 Types:
Authoritative → Owns data
Non-authoritative → Cached
🔸 Recursive DNS
Resolves queries fully
🔹 Hosts File
Local DNS override
⏱️ Time Protocols
🔸 NTP
Network Time Protocol
Syncs time across network
🔸 PTP
High precision (finance/industrial)
🔸 NTS
Secure time sync
🔐 3.5 Network Access & Management
🔹 VPN Types
🔸 Site-to-Site VPN
Connects networks
🔸 Client-to-Site VPN
Remote user access
🔸 Clientless VPN
Browser-based access
🔸 Split vs Full Tunnel
Split → Only some traffic via VPN
Full → All traffic via VPN
🔹 Management Methods
SSH → Secure CLI
GUI → Visual interface
API → Automation
Console → Direct access
🔹 Jump Box
Jump Server
Secure intermediate system
🔹 In-band vs Out-of-band
In-band → Uses production network
Out-of-band → Separate management network
🧠 FINAL SUMMARY
Section	Key Focus
3.1	Documentation & processes
3.2	Monitoring (SNMP, SIEM)
3.3	Disaster recovery
3.4	DHCP, DNS, NTP
3.5	VPN & access
