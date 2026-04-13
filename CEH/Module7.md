
# Module 7: Malware Threats

## 1. Introduction to Malware

**Definition:**  
Malware (Malicious Software) refers to programs designed to:  
- Damage/disrupt systems  
- Disable operations  
- Gain unauthorized access  
- Provide control to attackers  

**Purpose:**  
- Steal data (credentials, financial)  
- Espionage  
- Disrupt operations  
- Use systems for attacks  

**Types:**  
- Trojans, Backdoors, Rootkits  
- Ransomware, Adware, Viruses  
- Worms, Spyware, Botnets, Crypters  

**Examples:**  
- **WannaCry** → Healthcare disruption  
- **Zeus** → Banking credential theft  

---

## 2. Advanced Persistent Threats (APT)

**Definition:**  
Targeted, long-term cyberattack maintaining undetected access for data theft.

**Characteristics:**  
- **Advanced** → Sophisticated techniques  
- **Persistent** → Long-term access  
- **Threat** → Organized attackers  

**APT Lifecycle:**  
1. **Preparation** → Target research  
2. **Initial Intrusion** → Malware/C2  
3. **Expansion** → Privilege escalation  
4. **Persistence** → Backdoors  
5. **Exfiltration** → Data theft  
6. **Cleanup** → Hide traces  

**Example:**  
SolarWinds supply chain attack.

---

## 3. Trojan

**Definition:**  
Malicious code disguised as legitimate software.

**Characteristics:**  
- **No self-replication**  
- **User interaction required**  
- Delivered via: email, fake software  

**Capabilities:**  
- Delete/replace files  
- DoS attacks  
- Keylogging  
- Disable security  
- Backdoors, botnets  

**Example:**  
**DarkComet RAT** (Remote Access Trojan).

---

## 4. Common Trojan Ports

| Port | Trojan Examples |
|------|-----------------|
| 21   | Blade Runner, WinCrash |
| 22   | SSH RAT |
| 23   | Tiny Telnet Server |
| 25   | WinSpy, Terminator |
| 53   | Lazarus tools |
| 6666 | Killer RAT |
| 6969 | GateCrasher |
| 5001/5005 | Sockets de Troie |

**Key Insight:**  
Attackers use common ports to blend with legitimate traffic.

---

## 5. Viruses

**Definition:**  
Self-replicating programs attaching to legitimate files.

**Characteristics:**  
- **Requires host file**  
- Spreads via downloads/USBs/email  

**Infection Process:**  
1. Modifies file structure  
2. Inserts malicious code  
3. Alters execution flow  

**Indicators:**  
- System slowdowns  
- Crashes  
- Unusual pop-ups  

**Example:**  
**Melissa** (email-spreading virus).

---

## 6. Ransomware

**Definition:**  
Encrypts files, demands payment for decryption.

**Families:**  
- Phobos, LockBit, DarkSide  
- Conti, Cerber, REvil, Mallox  

**Targets:**  
- Windows systems  
- MS-SQL servers  

**Example:**  
**Colonial Pipeline** (DarkSide ransomware).

---

## 7. Fileless Malware

**Definition:**  
Malware operating in memory (RAM) without disk files.

**Techniques:**  
- PowerShell, WMI, Windows processes  

**Advantages:**  
- **Stealth** (no signatures)  
- **Persistence** without files  
- **Hard forensics**  

**Propagation:**  
- Phishing  
- Malicious scripts  
- Registry injection  

---

## 8. Fileless Malware Attack Flow

1. **Entry** → Phishing/malicious site  
2. **Execution** → Memory injection (PowerShell)  
3. **Persistence** → Registry/WMI tasks  
4. **Objectives** → Recon/exfiltration  

---

## 9. Malware Analysis

**Definition:**  
Studying malware to understand behavior and impact.

**Purpose:**  
- Identify attack methods  
- Extract IoCs  
- Support incident response  

---

## 10. Types of Malware Analysis

1. **Static Analysis**  
   - **No execution**  
   - File inspection, disassembly  
   - **Safe & quick**  

2. **Dynamic Analysis**  
   - **Controlled execution**  
   - Monitor behavior  
   - **Reveals hidden actions**  

---

## 11. Malware Analysis Lab Setup

**Steps:**  
1. Physical host + virtualization (VMware)  
2. **Network isolation** (Host-only)  
3. **INetSim** (fake internet)  
4. Disable shared folders  
5. Install tools  
6. Hash malware before transfer  

**Key Rule:**  
**Never analyze on production systems.**

---

## 12. Static Analysis: File Fingerprinting

**Purpose:**  
Identify malware via hash values.

**Algorithms:**  
- MD5, SHA-1, SHA-256, SHA-512  

**Tools:**  
- HashMyFiles  
- MD5sums  
- VirusTotal  

---

## 13. Static Analysis: Disassembly

**Definition:**  
Converting machine code to assembly.

**Purpose:**  
- Understand logic  
- Detect API calls (`CreateProcess`, registry ops)  

**Tools:**  
- **IDA Pro**  
- OllyDbg  
- **Ghidra**  
- WinDbg  

---

## 14. Dynamic Analysis: Registry Monitoring

**Purpose:**  
Track registry changes by malware.

**What Malware Does:**  
- Persistence (Run keys)  
- Startup entries  

**Tools:**  
- **Regshot** (before/after snapshots)  
- RegScanner  
- Registry Viewer  

**Example Key:**  
`HKCU\Software\Microsoft\Windows\CurrentVersion\Run`

---

## 15. Malware Countermeasures

**Categories:**  
- Anti-Trojan software  
- Antivirus  
- **Fileless detection**  
- EDR/XDR  
- **AI-powered tools**  

**Examples:**  
- Microsoft Defender  
- **CrowdStrike Falcon**  
- SentinelOne  

