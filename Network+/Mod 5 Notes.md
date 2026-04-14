Network+ Notes – Domain 5: Network Troubleshooting
🔍 5.1 Troubleshooting Methodology
Troubleshooting Methodology
🔹 Step 1: Identify the Problem
✅ Key Actions:
Gather information (logs, alerts)
Question users (what/when/how)
Identify symptoms (slow network, no connectivity)
Check recent changes
Try to reproduce the issue
Handle multiple issues separately
🔹 Step 2: Establish Theory of Cause
Approaches:
Top-to-Bottom (OSI) → Start from Application → Physical
Bottom-to-Top → Physical → Application
Divide and Conquer → Test middle layer (often Layer 3)

👉 Always question the obvious first

🔹 Step 3: Test the Theory
If correct → move to solution
If wrong → create new theory or escalate
🔹 Step 4: Plan of Action
Identify fix
Consider impact before applying
🔹 Step 5: Implement Solution
Apply fix or escalate
🔹 Step 6: Verify Functionality
Ensure system works fully
Add preventive measures
🔹 Step 7: Document Everything
Issue
Fix
Outcome
Lessons learned
🔌 5.2 Cabling & Interface Issues
🔹 Cable Issues
❌ Incorrect Cable Type
Single-mode vs multimode fiber
Cat5/6/7/8 mismatch
STP vs UTP
❌ Signal Degradation
Crosstalk → Signal interference
EMI (Interference) → External noise
Attenuation → Signal loss over distance
❌ Improper Termination
Bad crimping
Loose connectors
❌ TX/RX Transposed
Wrong transmit/receive alignment
🔹 Interface Issues
🔸 Interface Counters
CRC errors → Corrupted frames
Runts → Too small packets
Giants → Too large packets
Drops → Packet loss
🔸 Port Status
Error-disabled → Security violation
Administratively down → Manually shut
Suspended → VLAN or config issue
🔹 Hardware Issues
🔸 PoE (Power over Ethernet)
Power budget exceeded
Wrong PoE standard
🔸 Transceivers
Mismatch (SFP types)
Weak signal strength
🌐 5.3 Network Service Issues
🔹 Switching Issues
🔸 STP Problems
Spanning Tree Protocol
Network loops
Wrong root bridge
Incorrect port roles/states
🔸 VLAN Issues
Wrong VLAN assignment
Trunk misconfiguration
🔸 ACL Issues
Traffic blocked unintentionally
🔹 Routing Issues
Incorrect routing table
Missing default route
🔹 IP Issues
IP conflicts (duplicate IP)
Wrong subnet mask
Incorrect default gateway
🔹 DHCP Issues
Address pool exhaustion → No IP available
⚡ 5.4 Performance Issues
🔹 Network Problems
Congestion → Too much traffic
Bottleneck → One slow device
Bandwidth limits → Low capacity
🔹 Performance Metrics
Latency → Delay
Packet Loss → Dropped packets
Jitter → Variation in delay
📶 Wireless Issues
Interference → Signal clash
Channel overlap → Poor performance
Weak signal → Coverage issues
Client disconnection → Authentication/roaming issues
Roaming misconfiguration → Poor handoff
🧰 5.5 Troubleshooting Tools
🔹 Software Tools
🔸 Protocol Analyzer
Example: Wireshark
Captures packets
🔸 Command Line Tools
Tool	Purpose
ping	Connectivity test
traceroute	Path tracking
nslookup / dig	DNS query
tcpdump	Packet capture
netstat	Connections
ipconfig / ifconfig	IP config
arp	MAC-IP mapping
🔸 Nmap
Nmap
Network scanning & port detection
🔸 LLDP / CDP
Link Layer Discovery Protocol
Discover neighboring devices
🔸 Speed Tester
Measures bandwidth
🔹 Hardware Tools
Toner → Trace cables
Cable tester → Check wiring
TAP → Monitor traffic
Wi-Fi analyzer → Signal strength
Visual fault locator → Fiber faults
🔹 Device Commands (VERY IMPORTANT)
Command	Purpose
show mac-address-table	MAC table
show route	Routing table
show interface	Interface stats
show config	Running config
show arp	ARP table
show vlan	VLAN info
show power	Power/PoE
🧠 FINAL SUMMARY
Area	Key Focus
Methodology	Step-by-step troubleshooting
Cabling	Physical layer issues
Services	VLAN, routing, DHCP
Performance	Latency, packet loss
Tools	ping, traceroute, Wireshark
