# Network+ Notes — Domain 2.0: Network Implementation

---

## 2.1 Routing Technologies

### Static Routing

**Definition:** Static routing is a method where an administrator manually configures routes in a router's routing table. The router does not learn or update these routes automatically.

| Attribute | Detail |
|---|---|
| Route updates | Manual only; no automatic updates |
| CPU overhead | Very low; no routing protocol processing |
| Security | High; no route information is advertised to neighbors |
| Scalability | Poor; each route must be added and maintained manually |
| Failover | None; if a link fails, the static route remains until manually removed |

**Use Case:** Best suited for small, stable networks with few routes and predictable traffic paths, or for defining a default route of last resort.

---

### Dynamic Routing

**Definition:** Dynamic routing allows routers to automatically discover, exchange, and update routing information with neighboring routers using a routing protocol. When network topology changes, routes are updated automatically.

---

#### Dynamic Routing Protocols

| Protocol | Type | Algorithm | Scope | Description |
|---|---|---|---|---|
| BGP (Border Gateway Protocol) | Exterior Gateway Protocol (EGP) | Path-vector | Internet (between autonomous systems) | The routing protocol of the internet; used by ISPs and large organizations to exchange routes between autonomous systems. Makes routing decisions based on path attributes rather than simple metrics |
| OSPF (Open Shortest Path First) | Interior Gateway Protocol (IGP) | Link-state (Dijkstra) | Enterprise networks | Each router maintains a complete map of the network topology. Fast convergence and highly scalable; the most widely deployed enterprise routing protocol |
| EIGRP (Enhanced Interior Gateway Routing Protocol) | Interior Gateway Protocol (IGP) | Hybrid (distance-vector + link-state) | Enterprise networks (Cisco) | A Cisco-developed protocol combining features of both distance-vector and link-state protocols. Provides very fast convergence and efficient use of bandwidth |

---

### Route Selection Logic

When a router receives multiple routes to the same destination, it uses the following criteria in order to select the best path:

| Criteria | Definition | Rule |
|---|---|---|
| Administrative Distance (AD) | A value assigned to each routing source that represents its trustworthiness | Lower AD is preferred. Connected routes = 0, Static = 1, OSPF = 110, RIP = 120 |
| Prefix Length | The length of the subnet mask associated with a route | Longer prefix (more specific) wins. A /28 route is preferred over a /16 route to the same destination |
| Metric | A protocol-specific value representing the cost to reach a destination | Lower metric is preferred. Metrics vary by protocol: OSPF uses cost, EIGRP uses bandwidth and delay, RIP uses hop count |

---

### Address Translation

#### NAT (Network Address Translation)

**Definition:** NAT is a process performed by a router that modifies the source or destination IP address of packets as they pass through, typically translating private internal IP addresses to a public IP address for internet communication.

| Type | Description |
|---|---|
| Static NAT | A permanent one-to-one mapping between a specific private IP and a specific public IP |
| Dynamic NAT | Maps private IPs to a pool of public IP addresses on a first-come, first-served basis |
| PAT (Port Address Translation) | Also called NAT Overload; maps multiple private IP addresses to a single public IP address by differentiating connections using unique port numbers. This is the most common form of NAT used in home and enterprise networks |

---

### First Hop Redundancy Protocol (FHRP)

**Definition:** FHRP is a class of protocols that provides default gateway redundancy for end devices. If the primary gateway router fails, a standby router automatically assumes the gateway role, preventing network outages.

| Concept | Definition |
|---|---|
| Virtual IP (VIP) | A shared IP address configured on multiple routers as part of an FHRP group. End devices use the VIP as their default gateway rather than the physical IP of any single router |
| Active router | The router currently forwarding traffic for the VIP |
| Standby router | The backup router monitoring the active router and ready to take over if it fails |

**Common FHRP Protocols:** HSRP (Cisco proprietary), VRRP (open standard), GLBP (load-balancing variant).

---

### Subinterfaces

**Definition:** A subinterface is a logical subdivision of a single physical router interface, configured to operate as if it were a separate interface. Each subinterface is assigned to a different VLAN and IP subnet.

**Use Case:** Router-on-a-stick configurations, where a single physical router port connects to a switch trunk and routes traffic between multiple VLANs using one interface divided into subinterfaces.

---

## 2.2 Switching Technologies

### VLAN (Virtual LAN)

**Definition:** A VLAN is a logical grouping of network devices configured to communicate as if they were on the same physical network segment, regardless of their actual physical location. VLANs divide a single physical switch into multiple isolated broadcast domains.

| Component | Definition |
|---|---|
| VLAN Database | A table stored on a switch that records all configured VLAN IDs and their names |
| SVI (Switch Virtual Interface) | A virtual Layer 3 interface created on a switch and associated with a VLAN, used to provide inter-VLAN routing or management access to the switch |
| Native VLAN | The VLAN whose traffic is sent untagged across a trunk link. Both ends of a trunk must agree on the native VLAN to avoid security vulnerabilities |
| Voice VLAN | A dedicated VLAN configured on an access port to carry VoIP traffic, ensuring QoS policies can be applied separately from data traffic |

---

### 802.1Q VLAN Tagging

**Definition:** IEEE 802.1Q is the standard that defines how VLAN information is inserted into Ethernet frames. A 4-byte tag is added to the frame header, containing the VLAN ID (1–4094), allowing multiple VLANs to share a single trunk link.

---

### Link Aggregation

**Definition:** Link aggregation (also known as bonding or trunking at the port-channel level) combines multiple physical network links between two devices into a single logical link. This increases total bandwidth and provides redundancy — if one physical link fails, traffic continues over the remaining links.

| Standard | Description |
|---|---|
| IEEE 802.3ad (LACP) | Link Aggregation Control Protocol; dynamically negotiates and maintains aggregated links between devices |
| Static LAG | Links are manually configured without a negotiation protocol |

---

### Speed and Duplex

| Setting | Definition |
|---|---|
| Speed | The rate at which data is transmitted over a link, measured in Mbps or Gbps (e.g., 100 Mbps, 1 Gbps, 10 Gbps) |
| Full duplex | Data can be transmitted and received simultaneously on the same link; the standard for modern switched networks |
| Half duplex | Data can only flow in one direction at a time; associated with older hub-based networks and causes collisions |
| Auto-negotiation | Both ends of a link automatically agree on the highest mutually supported speed and duplex setting |

> **Best Practice:** Always configure speed and duplex manually on critical links. Mismatched duplex settings (one end auto, one end forced) are a common cause of poor performance and high error rates.

---

### Spanning Tree Protocol (STP)

**Definition:** STP (IEEE 802.1D) is a Layer 2 protocol that prevents switching loops in networks with redundant paths. It does this by placing ports into either a forwarding or blocking state, ensuring only one active path exists between any two network devices at a time.

| STP Variant | Description |
|---|---|
| STP (802.1D) | The original standard; slow convergence (30–50 seconds) |
| RSTP (802.1w) | Rapid Spanning Tree Protocol; significantly faster convergence (1–2 seconds) |
| MSTP (802.1s) | Multiple Spanning Tree Protocol; maps multiple VLANs to a single STP instance to reduce overhead |
| PVST+ | Cisco's Per-VLAN Spanning Tree Plus; runs a separate STP instance per VLAN |

---

### MTU (Maximum Transmission Unit)

**Definition:** The MTU is the largest size of a packet or frame that can be transmitted over a network link without fragmentation, measured in bytes.

| Type | Size | Use Case |
|---|---|---|
| Standard Ethernet MTU | 1500 bytes | Default for most Ethernet networks |
| Jumbo Frames | 9000 bytes (typical) | Used in data center and storage networks to improve throughput by reducing overhead per byte transferred |

---

## 2.3 Wireless Technologies

### Wireless Channels

| Concept | Definition |
|---|---|
| Channel width | The frequency range (in MHz) allocated to a Wi-Fi channel. Wider channels (e.g., 80 MHz, 160 MHz) provide higher throughput but increase susceptibility to interference |
| Non-overlapping channels | Channels that do not share frequency spectrum. In the 2.4 GHz band, channels 1, 6, and 11 are non-overlapping. Using overlapping channels causes co-channel interference and performance degradation |
| 802.11h (Regulatory) | An IEEE amendment that adds dynamic frequency selection (DFS) and transmit power control (TPC) to comply with regulatory requirements in the 5 GHz band |

---

### Wireless Frequency Bands

| Band | Speed | Range | Interference | Notes |
|---|---|---|---|---|
| 2.4 GHz | Lower | Longer | High (shared with Bluetooth, microwaves) | Better wall penetration; crowded spectrum |
| 5 GHz | Higher | Shorter | Lower | More available channels; less congestion |
| 6 GHz (Wi-Fi 6E) | Highest | Shortest | Very low | Introduced with 802.11ax; minimal interference due to exclusivity |

**Band Steering:** A feature on wireless controllers or APs that detects dual-band capable clients and encourages them to connect to the less congested 5 GHz or 6 GHz band instead of 2.4 GHz.

---

### Wireless Identifiers

| Identifier | Definition |
|---|---|
| SSID (Service Set Identifier) | The human-readable name of a wireless network broadcast by an access point |
| BSSID (Basic Service Set Identifier) | The MAC address of a specific access point radio; uniquely identifies a single AP within a wireless network |
| ESSID (Extended Service Set Identifier) | The shared SSID name used across multiple access points that form a single extended wireless network, allowing clients to roam seamlessly |

---

### Wireless Network Types

| Type | Definition |
|---|---|
| Infrastructure | The most common mode; clients connect to a centralized access point, which connects to the wired network |
| Ad hoc (IBSS) | Devices communicate directly with each other without an access point; suitable for temporary, peer-to-peer connections |
| Mesh | Multiple APs communicate wirelessly with each other to extend coverage; each AP can serve clients and relay traffic to the rest of the mesh network |
| Point-to-point | A dedicated wireless link between exactly two locations, often used to bridge buildings or campuses |

---

### Wireless Security

| Standard | Encryption | Description |
|---|---|---|
| WPA2 (Wi-Fi Protected Access 2) | AES-CCMP | The current enterprise standard; uses AES encryption which is robust and widely supported |
| WPA3 | AES-GCMP / SAE | The latest standard; replaces the WPA2 handshake with Simultaneous Authentication of Equals (SAE), which is resistant to offline dictionary attacks |

#### Authentication Methods

| Method | Description |
|---|---|
| PSK (Pre-Shared Key) | A single password shared by all users; suitable for small networks but offers no per-user identity tracking |
| Enterprise (802.1X) | Each user authenticates individually against a RADIUS server using credentials or certificates; provides granular access control and audit trails |
| Captive Portal | A web page presented to users before they can access the network; commonly used in guest and public Wi-Fi environments to accept terms of use or collect credentials |
| Guest Network | An isolated wireless network that provides internet access without access to internal network resources |

---

### Wireless Antennas

| Type | Pattern | Use Case |
|---|---|---|
| Omnidirectional | Radiates signal equally in all directions (360°) | General coverage in open areas; standard in most indoor APs |
| Directional (Yagi, Patch, Parabolic) | Focuses signal in a specific direction | Point-to-point links, long-distance outdoor connections, or coverage in a specific zone |

---

### Access Point Types

| Type | Description |
|---|---|
| Autonomous AP | A standalone access point that manages its own configuration, security, and RF settings independently; suitable for small deployments |
| Lightweight AP | A thin AP that relies on a centralized wireless LAN controller (WLC) for configuration, firmware, and RF management; suitable for large-scale deployments |

---

## 2.4 Physical Installations

### Distribution Frame Locations

| Location | Definition |
|---|---|
| IDF (Intermediate Distribution Frame) | A secondary wiring closet located on individual floors or sections of a building; aggregates cabling from end devices and connects back to the MDF |
| MDF (Main Distribution Frame) | The central point of a building's network infrastructure where all IDF connections terminate; typically houses the core network equipment and building entry connections |

---

### Rack Considerations

| Factor | Description |
|---|---|
| Rack units (U) | The standard unit of measure for rack-mounted equipment height; 1U = 1.75 inches. Racks are sized by total U capacity (e.g., 42U) |
| Airflow management | Equipment should be installed to maintain a front-to-back airflow pattern. Hot and cold aisles should be separated to maximize cooling efficiency |
| Cable management | Patch panels, cable managers, and proper labeling keep cabling organized and reduce troubleshooting time |
| Weight capacity | Racks must be rated to support the total weight of installed equipment |

---

### Cabling Infrastructure

| Component | Definition |
|---|---|
| Patch Panel | A mounted hardware assembly with multiple ports used to organize and manage cable connections. Provides a central termination point between wall jacks and network switches |
| Fiber Distribution Panel | A panel that houses fiber optic cable terminations, splices, and connectors, providing organized management of fiber infrastructure |

---

### Physical Security

| Measure | Description |
|---|---|
| Lockable racks | Cabinets with keyed or combination locks prevent unauthorized physical access to network equipment |
| Access controls | Badge readers or biometric systems restrict entry to network rooms and data centers |

---

### Power Infrastructure

| Component | Definition |
|---|---|
| UPS (Uninterruptible Power Supply) | A battery-backed device that provides emergency power to connected equipment during a power outage or voltage fluctuation, allowing for graceful shutdown or continued operation |
| PDU (Power Distribution Unit) | A device that distributes electrical power from a single source to multiple pieces of rack-mounted equipment; smart PDUs provide remote monitoring and per-outlet control |

| Power Concept | Definition |
|---|---|
| Power load | The total electrical power consumed by all devices connected to a circuit or UPS, measured in watts or volt-amperes (VA) |
| Voltage | The electrical potential difference driving current through a circuit; network equipment typically operates at 120V (North America) or 240V (international) |

---

### Environmental Factors

| Factor | Requirement | Risk if Uncontrolled |
|---|---|---|
| Temperature | Maintained within manufacturer specifications (typically 18–27°C / 64–80°F) | Overheating causes hardware failure, reduced component lifespan, and unexpected shutdowns |
| Humidity | Maintained between 40–60% relative humidity | Low humidity causes electrostatic discharge (ESD); high humidity causes condensation and corrosion |
| Fire suppression | Clean agent suppression systems (e.g., FM-200, Novec 1230) are used in data centers | Standard water-based sprinklers would destroy equipment; clean agents extinguish fires without damaging hardware |

---

## Summary Reference Table

| Topic | Key Concepts | Key Technologies / Standards |
|---|---|---|
| Static Routing | Manual routes, low overhead, no failover | Default route, next-hop configuration |
| Dynamic Routing | Auto-learned routes, protocol-based updates | BGP, OSPF, EIGRP |
| Route Selection | AD, prefix length, metric | Administrative distance table |
| Address Translation | Private-to-public IP conversion | NAT, PAT (NAT Overload) |
| FHRP | Default gateway redundancy | HSRP, VRRP, GLBP, Virtual IP |
| VLANs | Logical network segmentation | 802.1Q, SVI, native VLAN, voice VLAN |
| Link Aggregation | Bonded physical links | IEEE 802.3ad, LACP |
| STP | Loop prevention in switched networks | 802.1D, RSTP (802.1w), MSTP (802.1s) |
| MTU / Jumbo Frames | Packet size limits | 1500 bytes standard, 9000 bytes jumbo |
| Wireless Channels | Non-overlapping channels, channel width | 802.11h, channels 1/6/11 |
| Wireless Bands | 2.4 / 5 / 6 GHz tradeoffs | Band steering, 802.11ax (Wi-Fi 6E) |
| Wireless Security | WPA2 / WPA3, PSK, 802.1X | AES, SAE, RADIUS, captive portal |
| AP Types | Autonomous vs. controller-based | Lightweight AP, WLC |
| Physical Installations | IDF/MDF, rack design, cabling | Patch panel, fiber distribution panel |
| Power | UPS, PDU, load management | Voltage, wattage, VA ratings |
| Environment | Temperature, humidity, fire suppression | Clean agent systems, hot/cold aisle |
