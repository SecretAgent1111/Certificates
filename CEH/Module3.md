
# Module 3: Scanning Networks

## 1. TCP Communication Flags

**Definition:**  
TCP flags are control bits in the TCP header used to manage communication between systems [file:2].

**TCP Header Fields:**  
- Source Port  
- Destination Port  
- Sequence Number  
- Acknowledgment Number  
- Flags  
- Window Size  
- Checksum  

**TCP Flags:**  
1. **SYN (Synchronize)**  
   - Initiates a TCP connection  
   - Example: Client → Server: "Can we start communication?"  

2. **ACK (Acknowledgment)**  
   - Acknowledges received data  

3. **FIN (Finish)**  
   - Gracefully terminates a connection  

4. **RST (Reset)**  
   - Abruptly terminates a connection  

5. **PSH (Push)**  
   - Sends data immediately without buffering  

6. **URG (Urgent)**  
   - Marks urgent data to be processed immediately [file:4]  

**TCP Three-Way Handshake:** [file:3]  
1. SYN → Client sends request  
2. SYN-ACK → Server responds  
3. ACK → Client confirms  

**TCP Termination (4-Way Handshake):**  
1. FIN → Client  
2. ACK → Server  
3. FIN → Server  
4. ACK → Client  

---

## 2. Host Discovery Techniques

**Definition:**  
Techniques used to identify live/active hosts in a network [file:2].

**Techniques:** [file:2]  
1. **ICMP Ping Scan**  
   - Sends ICMP Echo Request  
   - Fast but often blocked  
   - Command: `nmap -PE <target IP>`  

2. **ARP Ping Scan**  
   - Uses ARP protocol  
   - Works in local network  
   - Command: `nmap -PR <target IP>`  

3. **UDP Ping Scan**  
   - Sends UDP packets  
   - No response = host alive  
   - Command: `nmap -PU <target IP>`  

4. **TCP Ping Scan**  
   - Uses TCP packets  
   - **SYN Ping:** `nmap -PS <target IP>`  
   - **ACK Ping:** `nmap -PA <target IP>`  

5. **IP Protocol Ping**  
   - Uses different IP protocols  
   - Command: `nmap -PO <target IP>`  

**Ping Sweep Tools:**  
- Angry IP Scanner  
- SolarWinds Engineer's Toolset  
- NetScanTools Pro  
- Colasoft Ping Tool  
- Advanced IP Scanner  
- OpUtils [file:2]  

---

## 3. Port Scanning Techniques

**Definition:**  
Process of identifying open, closed, or filtered ports [file:3].

**Port States:**  
- **Open** – Accepts connections  
- **Closed** – No service running  
- **Filtered** – Blocked by firewall  

**TCP Scanning Techniques:** [file:3]  
1. **TCP Connect Scan (Full Open)**  
   - Completes full handshake  
   - Easy to detect  
   - Command: `nmap -sT <target>`  

2. **SYN Scan (Half-Open/Stealth)**  
   - Sends SYN, receives SYN-ACK, sends RST  
   - Harder to detect  
   - Command: `nmap -sS <target>`  

3. **FIN Scan**  
   - Sends FIN packet  
   - Command: `nmap -sF <target>`  

4. **NULL Scan**  
   - No flags set  
   - Command: `nmap -sN <target>`  

5. **Xmas Scan**  
   - FIN + URG + PSH  
   - Command: `nmap -sX <target>`  

6. **ACK Scan**  
   - Used to detect firewall rules  
   - Command: `nmap -sA <target>`  

7. **Window Scan**  
   - Uses TCP window size  
   - Command: `nmap -sW <target>`  

**UDP Scanning:**  
- Command: `nmap -sU <target>`  

**IP6 Scanning:**  
- Command: `nmap -6 <IPv6>` [file:3]  

---

## 4. Stealth Scan (Half-Open Scan)

**Definition:**  
A scan that does not complete the TCP handshake [file:5].

**Working:** [file:5]  
1. Attacker sends SYN  
2. Target responds with SYN-ACK  
3. Attacker sends RST (no ACK)  

**Advantages:**  
- Bypasses logging mechanisms  
- Appears as regular traffic  

---

## 5. OS Discovery / Banner Grabbing

**Definition:**  
Technique to identify OS and services running on a system.

**Types:**  
1. **Active Banner Grabbing**  
   - Sends packets to target  
   - Analyzes responses  
   - Tools: Telnet, Netcat  

2. **Passive Banner Grabbing**  
   - Sniffs traffic  
   - Reads error messages  
   - Tool: Wireshark  

**Example:**  
Server returns: `Apache/2.4` → reveals web server version.

---

## 6. Identifying OS using TTL & Window Size

**Concept:**  
Different OS use different TTL values and TCP window sizes.

**Example Values:**  
| OS       | TTL  |  
|----------|------|  
| Linux    | 64   |  
| Windows  | 128  |  
| Cisco    | 255  |  

**Tools:**  
- Wireshark  
- Nmap (`nmap -O`)  

---

## 7. Packet Fragmentation

**Definition:**  
Splitting packets into smaller fragments to bypass IDS/firewalls.

**Purpose:**  
- Evade detection  
- Avoid packet inspection  

**Example:**  
`nmap -f <target>`  

---

## 8. Source Port Manipulation

**Definition:**  
Changing source port to trusted ports (e.g., 80, 53).

**Purpose:**  
Bypass firewall rules that trust common ports.

**Example:**  
`nmap --source-port 80 <target>`  

---

## 9. IP Address Decoy

**Definition:**  
Using multiple fake IPs to hide the real attacker IP.

**Example:**  
`nmap -D RND:10 <target>`  

**Purpose:**  
Confuse IDS and defenders.

---

## 10. IP Address Spoofing

**Definition:**  
Changing source IP to impersonate another system.

**Limitation:**  
Cannot complete TCP handshake (no SYN-ACK response).

**Tools:**  
- Hping3  

---

## 11. MAC Address Spoofing

**Definition:**  
Changing MAC address to impersonate another device.

**Tool:**  
`nmap --spoof-mac 0 <target>`  

**Purpose:**  
Bypass MAC filtering in LAN.

---

## 12. Proxy Servers

**Definition:**  
Intermediate system that hides attacker identity.

**Uses:**  
- Hide IP address  
- Bypass firewalls  
- Chain multiple proxies  

---

## 13. Ping Sweep Countermeasures

**Controls:**  
- Block ICMP Echo Requests  
- Use IDS/IPS  
- Monitor ICMP traffic  
- Limit ICMP rate  
- Use Access Control Lists (ACLs)  

---

## 14. Port Scanning Countermeasures

**Controls:**  
- Firewall rules blocking scans  
- IDS/IPS detection  
- Router ACL filtering  
- Firmware updates  
- Block unused ports  
- Anti-spoofing rules  

---

## 15. Banner Grabbing Countermeasures

**Techniques:**  
1. Disable unnecessary banners  
2. Modify HTTP headers  
3. Hide file extensions  
4. Mask server software details  

**Example:**  
Remove `Server: Apache/2.4` from HTTP response headers.

---

## 16. IP Spoofing Detection

**TCP Flow Control Method:**  
Spoofed packets cannot respond to SYN-ACK or follow proper TCP flow.

**Indicators:**  
- No response to SYN-ACK  
- No TCP window scaling  
- Abnormal sequence numbers  

---

## 17. IP Spoofing Countermeasures

**Controls:**  
- Encryption (TLS, IPsec)  
- Multiple firewalls  
- Avoid IP-based authentication  
- Randomize TCP sequence numbers  
- **Ingress filtering** (block spoofed inbound)  
- **Egress filtering** (block spoofed outbound) [file:5]  
