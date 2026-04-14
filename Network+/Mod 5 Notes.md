# Network+ Notes — Domain 5: Network Troubleshooting

---

## 5.1 Troubleshooting Methodology

A structured troubleshooting methodology ensures problems are resolved systematically, consistently, and with minimal disruption. The CompTIA Network+ exam follows a seven-step process.

---

### Step 1: Identify the Problem

The first step is to gather enough information to clearly define what is wrong before attempting any fix.

| Action | Description |
|---|---|
| Gather information | Collect logs, alerts, and error messages from affected systems |
| Question users | Ask what happened, when it started, and how it was discovered |
| Identify symptoms | Distinguish between symptoms (slow network) and root causes |
| Check recent changes | Review any configuration, hardware, or software changes made prior to the issue |
| Reproduce the issue | Attempt to trigger the problem again to confirm it is consistent |
| Isolate multiple issues | If more than one problem exists, handle each separately |

---

### Step 2: Establish a Theory of Probable Cause

After identifying symptoms, form a hypothesis about the likely cause. Three common approaches exist:

| Approach | Description |
|---|---|
| Top-to-Bottom (OSI) | Begin troubleshooting at Layer 7 (Application) and work down to Layer 1 (Physical) |
| Bottom-to-Top (OSI) | Begin at Layer 1 (Physical) and work up to Layer 7 (Application) |
| Divide and Conquer | Start at a middle layer — commonly Layer 3 (Network) — and work outward based on findings |

> **Best Practice:** Always question the obvious first. Many network issues are caused by simple problems such as unplugged cables, disabled ports, or incorrect IP settings.

---

### Step 3: Test the Theory

Once a theory is formed, test it to determine whether it explains the observed symptoms.

| Outcome | Action |
|---|---|
| Theory confirmed | Proceed to plan a solution |
| Theory incorrect | Formulate a new theory and repeat, or escalate to a higher-level technician |

---

### Step 4: Establish a Plan of Action

Before making any changes, document the intended fix and assess its potential impact on users and systems.

- Identify the specific corrective action required.
- Evaluate risks: Will the fix cause downtime? Will it affect other services?
- Schedule maintenance windows if necessary.

---

### Step 5: Implement the Solution

Apply the planned fix. If the issue is beyond your scope or authorization, escalate to the appropriate person or team.

---

### Step 6: Verify Full System Functionality

After applying the fix, confirm that the original problem is resolved and that no new issues have been introduced.

- Test the affected system from the user's perspective.
- Implement preventive measures to reduce the likelihood of recurrence.

---

### Step 7: Document Findings, Actions, and Outcomes

Documentation is critical for organizational knowledge and future troubleshooting.

| What to Document | Purpose |
|---|---|
| Description of the issue | Provides a reference for similar future problems |
| Steps taken to diagnose | Shows the troubleshooting path followed |
| Solution applied | Records what actually fixed the problem |
| Outcome | Confirms whether the solution was successful |
| Lessons learned | Helps improve future troubleshooting processes |

---

## 5.2 Cabling and Interface Issues

Physical layer (Layer 1) problems are among the most common causes of network failures. These issues relate to cables, connectors, ports, and hardware components.

---

### Cable Issues

#### Incorrect Cable Type

Using the wrong cable type for a given environment or application will cause connectivity problems or degraded performance.

| Cable Mismatch | Description |
|---|---|
| Single-mode vs. multimode fiber | Single-mode supports longer distances; multimode is for short runs. Using the wrong type causes signal loss or no link |
| Cat5 / Cat6 / Cat7 / Cat8 mismatch | Higher categories support faster speeds and more bandwidth. Mixing categories limits performance to the lowest-rated cable |
| STP vs. UTP | Shielded Twisted Pair (STP) protects against electromagnetic interference. Using UTP in high-EMI environments causes noise and errors |

#### Signal Degradation

Signal degradation occurs when the quality or strength of a signal is reduced as it travels through a cable.

| Issue | Definition |
|---|---|
| Crosstalk | Electromagnetic interference from adjacent cable pairs within the same cable, causing signals to bleed into one another |
| EMI (Electromagnetic Interference) | External noise from motors, fluorescent lights, or other electrical equipment interfering with cable signals |
| Attenuation | The natural weakening of a signal as it travels over distance; excessive attenuation causes data loss or errors |

#### Physical Termination Problems

| Issue | Description |
|---|---|
| Bad crimping | Improperly terminated RJ-45 connectors cause intermittent or no connectivity |
| Loose connectors | Connectors that are not fully seated result in packet loss and unreliable links |
| TX/RX transposition | Transmit and receive wires are crossed incorrectly, preventing communication. Common in fiber and direct-attach copper connections |

---

### Interface Issues

Network interface counters provide diagnostic information about errors occurring at the port level.

#### Interface Error Counters

| Counter | Definition |
|---|---|
| CRC Errors | Cyclic Redundancy Check errors indicate corrupted frames, usually caused by physical layer problems such as bad cables or connectors |
| Runts | Frames that are smaller than the minimum Ethernet frame size (64 bytes), often caused by collisions or faulty hardware |
| Giants | Frames that exceed the maximum Ethernet frame size (1518 bytes), often caused by misconfigured MTU settings |
| Drops | Packets discarded by the interface due to buffer overflow, congestion, or resource exhaustion |

#### Port Status Indicators

| Status | Definition |
|---|---|
| Error-disabled | The port has been automatically shut down by the switch due to a security violation or loop detection (e.g., PortFast with a BPDU received) |
| Administratively down | The port has been manually disabled by a network administrator using the `shutdown` command |
| Suspended | The port is inactive due to a VLAN mismatch, spanning tree inconsistency, or configuration conflict |

---

### Hardware Issues

#### Power over Ethernet (PoE)

PoE allows network switches to deliver electrical power to connected devices (e.g., IP phones, access points) through the Ethernet cable.

| Issue | Description |
|---|---|
| Power budget exceeded | The total PoE power demanded by all connected devices exceeds the switch's maximum PoE output capacity |
| PoE standard mismatch | Devices requiring PoE+ (802.3at) or PoE++ (802.3bt) may not function properly when connected to a switch only supporting standard PoE (802.3af) |

#### Transceivers

Transceivers (e.g., SFP, SFP+, QSFP) are modular components used to connect switches and routers via fiber or copper.

| Issue | Description |
|---|---|
| Transceiver mismatch | Using incompatible SFP types (e.g., mixing single-mode and multimode SFPs) prevents link establishment |
| Weak signal / low optical power | Dirty or damaged fiber connectors, excessive bend radius, or long cable runs result in insufficient optical power at the receiver |

---

## 5.3 Network Service Issues

Service issues occur at Layers 2 through 4 of the OSI model and relate to switching, routing, IP addressing, and DHCP.

---

### Switching Issues

#### Spanning Tree Protocol (STP)

**Definition:** STP (IEEE 802.1D) is a Layer 2 protocol that prevents network loops in switched environments by placing redundant ports into a blocking state.

| STP Problem | Description |
|---|---|
| Network loops | Occur when STP is disabled or misconfigured, causing broadcast storms that consume all available bandwidth |
| Wrong root bridge election | The root bridge is elected based on the lowest bridge ID. If a non-optimal switch wins the election, traffic paths become suboptimal |
| Incorrect port roles or states | Ports in wrong roles (root, designated, blocked) or stuck in transitional states cause forwarding delays or loops |

#### VLAN Issues

**Definition:** A Virtual LAN (VLAN) is a logical grouping of network devices that separates broadcast domains regardless of physical location.

| VLAN Problem | Description |
|---|---|
| Wrong VLAN assignment | A device placed in the incorrect VLAN cannot communicate with its intended peers |
| Trunk misconfiguration | Trunk links carry traffic for multiple VLANs between switches. If VLANs are not allowed on the trunk, traffic is dropped silently |

#### ACL Issues

**Definition:** An Access Control List (ACL) is an ordered set of rules applied to an interface that permits or denies traffic based on defined criteria.

| ACL Problem | Description |
|---|---|
| Unintentional traffic blocking | Overly broad or incorrectly ordered ACL entries may block legitimate traffic |

---

### Routing Issues

| Problem | Description |
|---|---|
| Incorrect routing table | Missing or incorrect routes cause packets to be forwarded to the wrong destination or dropped |
| Missing default route | Without a default route (0.0.0.0/0), a router cannot forward packets destined for unknown networks, causing connectivity failures |

---

### IP Addressing Issues

| Problem | Description |
|---|---|
| IP address conflict | Two devices sharing the same IP address on the same network cause intermittent connectivity for both devices |
| Incorrect subnet mask | A wrong subnet mask causes a device to misidentify which hosts are local vs. remote, breaking communication |
| Incorrect default gateway | Devices with a wrong default gateway cannot route traffic outside their local subnet |

---

### DHCP Issues

**Definition:** DHCP (Dynamic Host Configuration Protocol) automatically assigns IP addresses and configuration parameters to clients on a network.

| Problem | Description |
|---|---|
| Address pool exhaustion | When all addresses in the DHCP scope have been leased, new clients cannot obtain an IP address and receive an APIPA address (169.254.x.x) instead |

---

## 5.4 Performance Issues

Performance issues affect the quality and speed of network communications and may be caused by hardware limitations, traffic congestion, or wireless interference.

---

### Wired Network Performance

| Issue | Definition |
|---|---|
| Congestion | Occurs when the volume of traffic exceeds the capacity of a network link or device, causing queuing and delays |
| Bottleneck | A single device, link, or segment limits overall network throughput for all traffic passing through it |
| Bandwidth limitation | A link with insufficient capacity for the traffic load results in degraded performance for all users sharing it |

---

### Key Performance Metrics

| Metric | Definition |
|---|---|
| Latency | The time it takes for a packet to travel from source to destination, measured in milliseconds (ms) |
| Packet Loss | The percentage of transmitted packets that never reach their destination, often caused by congestion or faulty hardware |
| Jitter | Variation in the delay between packets arriving at the destination; high jitter degrades real-time applications such as VoIP and video conferencing |

---

### Wireless Performance Issues

| Issue | Definition |
|---|---|
| RF Interference | Competing signals from other wireless devices (microwaves, Bluetooth, neighboring networks) degrade signal quality |
| Channel Overlap | Adjacent wireless access points using overlapping channels (e.g., channels 1, 6, 11 in 2.4 GHz) cause co-channel or adjacent-channel interference |
| Weak Signal Strength | Physical obstructions, distance from the access point, or low transmit power result in poor coverage and throughput |
| Client Disconnection | Clients may drop connections due to authentication failures, expired DHCP leases, or roaming handoff problems |
| Roaming Misconfiguration | Improper access point placement or inconsistent SSID/security configuration causes poor or failed handoff when clients move between access points |

---

## 5.5 Troubleshooting Tools

A wide range of software and hardware tools are available to assist in diagnosing network problems.

---

### Software Tools

#### Protocol Analyzer

**Definition:** A protocol analyzer (also called a packet sniffer) captures and decodes network traffic for detailed inspection.

| Tool | Description |
|---|---|
| Wireshark | The most widely used open-source packet capture and analysis tool; supports hundreds of protocols and provides deep packet inspection |
| tcpdump | A command-line packet capture tool available on Linux and macOS; useful for capturing traffic on remote systems without a GUI |

---

#### Command-Line Diagnostic Tools

| Command | Platform | Purpose |
|---|---|---|
| `ping` | Windows / Linux / macOS | Tests basic Layer 3 connectivity between two hosts using ICMP Echo requests |
| `traceroute` / `tracert` | Linux / Windows | Traces the path packets take to a destination, identifying each hop and its response time |
| `nslookup` | Windows / Linux | Queries DNS servers to resolve hostnames to IP addresses and diagnose DNS issues |
| `dig` | Linux / macOS | Advanced DNS query tool providing detailed DNS record information and query diagnostics |
| `netstat` | Windows / Linux | Displays active TCP/UDP connections, listening ports, and network statistics |
| `ipconfig` | Windows | Displays IP configuration for all network adapters, including IP address, subnet mask, and default gateway |
| `ifconfig` | Linux / macOS | Displays and configures network interface settings on Unix-based systems |
| `arp` | Windows / Linux | Displays the ARP cache, mapping IP addresses to MAC addresses; useful for detecting IP conflicts |

---

#### Network Scanning Tools

| Tool | Description |
|---|---|
| Nmap | An open-source network scanner used to discover hosts, detect open ports, identify services, and fingerprint operating systems on a network |

---

#### Discovery and Monitoring Protocols

| Protocol / Tool | Definition |
|---|---|
| LLDP (Link Layer Discovery Protocol) | An IEEE 802.1AB standard protocol that allows network devices to advertise their identity and capabilities to directly connected neighbors |
| CDP (Cisco Discovery Protocol) | A Cisco-proprietary protocol similar to LLDP; used to discover neighboring Cisco devices and their configurations |
| Speed Tester | A software utility that measures actual bandwidth throughput between a device and a test server |

---

### Hardware Tools

| Tool | Description |
|---|---|
| Toner (Toner Probe) | A two-part tool used to trace and identify cable runs through walls or across a building. The tone generator injects a signal and the probe detects it |
| Cable Tester | Verifies the electrical continuity and correct wiring of copper cables; identifies opens, shorts, and miswired pairs |
| Network TAP (Test Access Point) | A passive hardware device inserted into a network link that copies traffic to a monitoring port without interrupting the original connection |
| Wi-Fi Analyzer | A hardware or software tool that scans the wireless environment, displaying access points, signal strengths, channel usage, and interference sources |
| Visual Fault Locator (VFL) | A handheld device that injects visible red laser light into a fiber optic cable to visually identify breaks, bends, or connector faults |

---

### Device Show Commands (Cisco CLI)

These commands are used on Cisco switches and routers to retrieve operational and configuration data for troubleshooting.

| Command | Purpose |
|---|---|
| `show mac-address-table` | Displays the MAC address table, showing which MAC addresses are associated with which switch ports and VLANs |
| `show ip route` | Displays the routing table, showing all known routes and their sources (static, OSPF, EIGRP, etc.) |
| `show interfaces` | Shows detailed statistics for all interfaces, including status, error counters, bandwidth, and duplex settings |
| `show running-config` | Displays the currently active configuration in RAM |
| `show ip arp` | Displays the ARP table, mapping IP addresses to MAC addresses |
| `show vlan` | Lists all configured VLANs and the ports assigned to each |
| `show power inline` | Displays PoE status for all ports, including power consumption and available budget |

---

## Summary Reference Table

| Domain Area | Key Topics | Common Tools |
|---|---|---|
| Troubleshooting Methodology | 7-step process, OSI-based approaches, documentation | N/A |
| Cabling and Physical Layer | Cable types, signal degradation, interface errors, PoE | Cable tester, toner, VFL |
| Switching and VLANs | STP, VLAN assignment, trunking, ACLs | `show vlan`, `show mac-address-table` |
| Routing and IP Addressing | Routing tables, default routes, IP conflicts, gateway | `show ip route`, `ping`, `traceroute` |
| DHCP | Pool exhaustion, APIPA fallback | `ipconfig`, `show running-config` |
| Performance | Latency, jitter, packet loss, congestion | Wireshark, `ping`, speed tester |
| Wireless | Interference, channel overlap, roaming, signal strength | Wi-Fi analyzer |
| Diagnostic Tools | CLI tools, protocol analyzers, hardware tools | Nmap, Wireshark, `show` commands |
