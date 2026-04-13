
# Module 8: Sniffing

## 1. Network Sniffing

**Definition:**  
Capturing, monitoring, and analyzing network traffic passing through a network.

**Tools:**  
- Software: Wireshark, tcpdump  
- Hardware sniffers  

**Data Captured:**  
- Telnet/FTP passwords (plaintext)  
- Email credentials  
- HTTP web traffic  
- Chat sessions  
- DNS queries  

---

## 2. How Sniffing Works

**Core Concept:** **Promiscuous Mode**  
- NIC captures **ALL** packets (not just destined for it)  

**Switched Networks Challenge:**  
- Switches send traffic only to intended destination  
- Attackers must manipulate network  

---

## 3. Types of Sniffing

### A. Passive Sniffing
**Definition:**  
Monitoring without modifying traffic.  

**Environment:**  
Hub-based networks (broadcast all traffic)  

**Characteristics:**  
- No packet injection  
- **Hard to detect**  
- **Limited to hubs**  

### B. Active Sniffing
**Definition:**  
Manipulating switched networks to capture traffic.  

**Techniques:**  
- MAC flooding  
- **ARP poisoning**  
- DNS poisoning  
- DHCP attacks  
- Switch port stealing  

---

## 4. Sniffing in OSI Model

**Primary Layer:** **Data Link (Layer 2)**  
- Raw packet frames  
- **No encryption** at this layer  
- Upper layers unaware of Layer 2 sniffing  

---

## 5. SPAN Port (Port Mirroring)

**Definition:**  
Copies traffic from one port to another for monitoring.  

**Uses:**  
- Network admins  
- IDS/IPS  
- **Attackers** (if they gain access)  

**Example:**  
IDS monitors SPAN port → attacker compromises → sees all traffic.  

---

## 6. Detailed Sniffing Attacks

### 6.1 MAC Flooding Attack
**Definition:**  
Flooding switch with fake MAC addresses to overflow CAM table.  

**Mechanism:**  
```
CAM table full → Switch acts like hub
→ Broadcasts ALL traffic
```

**Attack Steps:**  
1. Send thousands of fake MACs  
2. CAM overflow  
3. Traffic broadcast  
4. **Sniff packets**  

**Tool:** `macof` (dsniff)  

**Countermeasures:**  
- Port security  
- MAC limits per port  

---

### 6.2 DHCP Attack

**A. DHCP Starvation:**  
- Exhaust IP pool with fake requests  
- **Result:** Legitimate users denied IPs  

**B. Rogue DHCP Server:**  
- Fake DHCP assigns malicious configs  
- Fake gateway/DNS → **MITM**  

**Countermeasures:**  
- **DHCP snooping**  
- Port authentication  

---

### 6.3 ARP Poisoning (CRITICAL)
**Definition:**  
Fake ARP replies poisoning victim ARP cache.  

**Attack Flow:**  
```
Victim thinks: "Attacker MAC = Gateway IP"
Gateway thinks: "Attacker MAC = Victim IP"
→ ALL traffic routes through attacker
```

**Tools:**  
- **Ettercap**  
- Arpspoof  

**Impact:**  
- MITM  
- Credential theft  
- Session hijacking  

**Detection:**  
- Duplicate MACs  
- ARP inconsistencies  

**Countermeasures:**  
- **Dynamic ARP Inspection (DAI)**  
- Static ARP entries  
- **HTTPS**  

---

### 6.4 DNS Poisoning
**Definition:**  
Fake DNS responses redirecting to malicious sites.  

**Types:**  
- Cache poisoning  
- DNS spoofing  

**Impact:**  
```
bank.com → fakebank.com (phishing)
```

**Countermeasures:**  
- **DNSSEC**  
- Secure DNS servers  

---

### 6.5 Switch Port Stealing
**Definition:**  
Attacker MAC overwrites victim MAC in switch CAM table.  

**Result:**  
Victim traffic redirected to attacker.  

**Countermeasures:**  
- **Port security** (sticky MAC)  

---

### 6.6 Spoofing Attacks
**Types:**  
- IP spoofing  
- MAC spoofing  

**Purpose:**  
Impersonate devices → intercept traffic.  

---

## 7. Sniffing Tools

| Tool | Purpose |
|------|---------|
| **Wireshark** | Packet capture/analysis |
| **Tcpdump** | Command-line capture |
| **Ettercap** | ARP poisoning/MITM |
| **Cain & Abel** | Password recovery |
| **Dsniff** | Protocol analysis |

---

## 8. Sniffing Countermeasures

**Technical:**  
```
• HTTPS/SSH/VPN encryption
• Switch port security
• DHCP snooping
• Dynamic ARP Inspection
• IDS/IPS monitoring
```

**Best Practices:**  
- **No plaintext protocols** (Telnet/FTP)  
- Secure authentication  
- Anomaly monitoring  

---

## Attack Summary Table

| Attack | Target | Tool | Countermeasure |
|--------|--------|------|----------------|
| **ARP Poisoning** | ARP cache | **Ettercap** | **DAI** |
| MAC Flooding | CAM table | macof | Port security |
| DHCP Starvation | IP pool | Yersinia | **DHCP snooping** |
| DNS Poisoning | DNS cache | dnsspoof | **DNSSEC** |
| Port Stealing | CAM table | macchanger | Sticky MAC |

**Most Critical:** **ARP Poisoning** (enables MITM attacks)  
