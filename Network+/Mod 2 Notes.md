Network+ Notes – Domain 2: Network Implementation
🌐 2.1 Routing Technologies
🔹 Static Routing
Static Routing
📌 Definition:

Routes are manually configured by an administrator

✅ Characteristics:
No automatic updates
Low CPU usage
Highly secure (no route advertisements)
❌ Disadvantages:
Not scalable
No automatic failover

👉 Use Case: Small, stable networks

🔹 Dynamic Routing
Dynamic Routing
📌 Definition:

Routers automatically learn and update routes using protocols

🔸 BGP
Exterior Gateway Protocol (EGP)
Used on the internet (ISP level)
Path-based routing

👉 Example: Routing between countries

🔸 EIGRP
Hybrid protocol (distance + link-state)
Fast convergence
Cisco proprietary (mostly)
🔸 OSPF
Link-state protocol
Uses Dijkstra algorithm
Fast and scalable

👉 Most common in enterprise networks

🔹 Route Selection Logic
✅ Administrative Distance (AD)
Trustworthiness of route source
Lower = better
✅ Prefix Length
Longest prefix match wins
👉 Example: /24 preferred over /16
✅ Metric
Cost of route (depends on protocol)
Lower metric = preferred path
🔹 Address Translation
🔸 Network Address Translation
Converts private IP → public IP
Conserves IP addresses
🔸 Port Address Translation
Multiple devices share one public IP
Uses port numbers

👉 Most common NAT type

🔹 First Hop Redundancy Protocol (FHRP)
First Hop Redundancy Protocol
📌 Purpose:

Provides gateway redundancy

👉 If one router fails → another takes over

🔹 Virtual IP (VIP)
Virtual IP
Shared IP used by multiple devices
Clients use VIP as gateway
🔹 Subinterfaces
Subinterface
Logical interfaces on a physical interface
Used for VLAN routing (router-on-a-stick)
🔀 2.2 Switching Technologies
🔹 VLAN (Virtual LAN)
6
Virtual LAN
📌 Definition:

Splits a network into logical segments

🔸 VLAN Database
Stores VLAN configurations
🔸 SVI (Switch Virtual Interface)
Virtual interface for VLAN
Used for inter-VLAN routing
🔹 Interface Configuration
✅ Native VLAN
Untagged VLAN on trunk port
✅ Voice VLAN
Dedicated VLAN for VoIP traffic
✅ 802.1Q Tagging
IEEE 802.1Q
Adds VLAN tag to frames
✅ Link Aggregation
Link Aggregation
Combines multiple links into one
Improves bandwidth + redundancy
✅ Speed & Duplex
Speed → Mbps/Gbps
Duplex → Half / Full
🔹 Spanning Tree Protocol (STP)
Spanning Tree Protocol
Prevents switching loops
Disables redundant paths
🔹 MTU (Maximum Transmission Unit)
Maximum Transmission Unit
Maximum packet size
🔸 Jumbo Frames
Larger than standard MTU (1500 bytes)
Used in data centers
📶 2.3 Wireless Technologies
🔹 Channels
✅ Channel Width
Wider = more speed, more interference
✅ Non-overlapping Channels
Prevent interference (e.g., 1, 6, 11 in 2.4GHz)
✅ Regulatory (802.11h)
IEEE 802.11h
Controls power + frequency usage
🔹 Frequency Bands
2.4 GHz → Long range, slow
5 GHz → Faster, less interference
6 GHz → Newest, fastest
🔸 Band Steering
Moves devices to better frequency
🔹 SSID
Service Set Identifier
Network name
🔸 BSSID
MAC address of AP
🔸 ESSID
Multiple APs, same network
🔹 Network Types
Mesh → APs connected
Ad hoc → Device-to-device
Point-to-point → Direct link
Infrastructure → AP-based (most common)
🔐 Security
🔸 WPA2
AES encryption
🔸 WPA3
Stronger security
🔹 Guest Networks
Isolated network
🔸 Captive Portal
Login page before access
🔹 Authentication
PSK → Password-based
Enterprise → RADIUS authentication
🔹 Antennas
Omnidirectional → 360°
Directional → Focused signal
🔹 AP Types
Autonomous → Standalone
Lightweight → Controller-based
🏢 2.4 Physical Installations
🔹 Locations
🔸 Intermediate Distribution Frame
Local wiring closet
🔸 Main Distribution Frame
Central network hub
🔹 Rack Considerations
Size (rack units)
Airflow (front/back)
🔹 Cabling
Patch panel → Cable management
Fiber distribution panel → Fiber termination
🔹 Security
Lockable racks
🔌 Power
🔸 Uninterruptible Power Supply
Backup power
🔸 Power Distribution Unit
Distributes power
🔹 Concepts
Power load → total usage
Voltage → electrical level
🌡️ Environmental Factors
Humidity → avoid moisture damage
Temperature → cooling required
Fire suppression → protect equipments
