
# Module 6: Malware Threats

## Note: 
This module covers malware types, infection vectors, analysis techniques, and countermeasures. Content structured from provided source material.

## Malware Types Overview

### 1. Viruses
**Definition:**  
Self-replicating programs that attach to legitimate files and spread when executed.

**Characteristics:**  
- Requires host file  
- Spreads via infected files  
- Platform-specific  

### 2. Worms
**Definition:**  
Self-replicating malware that spreads independently across networks.

**Characteristics:**  
- No host file required  
- Network propagation  
- Consumes bandwidth  

### 3. Trojans
**Definition:**  
Malicious programs disguised as legitimate software.

**Characteristics:**  
- User-initiated execution  
- Backdoor functionality  
- Multiple payloads  

### 4. Ransomware
**Definition:**  
Encrypts victim data and demands payment for decryption.

**Types:**  
- Crypto ransomware  
- Locker ransomware  

### 5. Rootkits
**Definition:**  
Malware that hides its presence and provides persistent access.

**Types:**  
- Kernel-level  
- User-level  
- Firmware  

### 6. Logic Bombs
**Definition:**  
Malicious code triggered by specific conditions (time, event).

### 7. Backdoors
**Definition:**  
Remote access mechanisms bypassing normal authentication.

## Infection Vectors

1. **Email Attachments**  
   - Macro-enabled documents  
   - Malicious PDFs  

2. **Drive-by Downloads**  
   - Malicious websites  
   - Exploit kits  

3. **USB/Media**  
   - Autorun infections  
   - Physical delivery  

4. **Social Engineering**  
   - Phishing  
   - Pretexting  

5. **Software Supply Chain**  
   - Compromised updates  
   - Malicious dependencies  

## Malware Analysis Types

### Static Analysis
**Definition:**  
Examining malware without execution.

**Techniques:**  
- Hash identification  
- String analysis  
- PE header inspection  
- Packer detection  

**Tools:**  
- VirusTotal  
- PEiD  
- Strings  
- IDA Pro (disassembler)  

### Dynamic Analysis
**Definition:**  
Executing malware in controlled environment.

**Environment:**  
- Virtual machines  
- Sandboxes  
- Network isolation  

**Monitoring:**  
- Process behavior  
- File system changes  
- Network traffic  
- Registry modifications  

**Tools:**  
- Process Monitor  
- Wireshark  
- Regshot  
- Cuckoo Sandbox  

### Behavioral Analysis
**Definition:**  
Analyzing malware runtime behavior and capabilities.

**Focus Areas:**  
- Persistence mechanisms  
- C2 communication  
- Payload delivery  
- Anti-analysis techniques  

## Anti-Analysis Techniques

1. **Environment Detection**  
   - VM artifacts  
   - Debugger detection  
   - Sandbox recognition  

2. **Obfuscation**  
   - Code packing  
   - Encryption  
   - Polymorphism  

3. **Time-based Evasion**  
   - Sleep calls  
   - Delayed execution  

## Malware Indicators

**File-based:**  
```
PE header anomalies
Packed executables
Suspicious strings
Embedded scripts
```

**Runtime Indicators:**  
```
Unknown processes
Network connections to C2
Persistence mechanisms
File/registry changes
```

**Network Indicators:**  
```
Domain generation algorithms (DGA)
Beaconing patterns
Unusual ports/protocols
```

## Malware Countermeasures

### Prevention
1. **Endpoint Protection**  
   - Next-gen AV  
   - EDR solutions  

2. **Network Security**  
   - Web filtering  
   - Email gateways  
   - DNS security  

3. **User Training**  
   - Phishing awareness  
   - Safe browsing  

### Detection
1. **Signature-based**  
2. **Behavior-based**  
3. **Reputation-based**  

### Response
1. **Isolation**  
2. **Forensic analysis**  
3. **Remediation**  
4. **Threat hunting**  

## Specific Malware Examples

### WannaCry Ransomware
**Date:** May 2017  
**Vulnerability:** EternalBlue (SMB)  
**Impact:** 200K+ systems worldwide  

### Emotet Trojan
**Capabilities:**  
- Banking theft  
- Downloader  
- Persistence  

### TrickBot
**Capabilities:**  
- Credential harvesting  
- Lateral movement  
- Ransomware delivery  

## Analysis Tools Summary

| Category | Tools |
|----------|-------|
| Static | VirusTotal, PEiD, IDA Pro, strings |
| Dynamic | VMWare, Wireshark, ProcMon, Regshot |
| Sandbox | Cuckoo, Any.Run, JoeSandbox |
| Disassembly | IDA Pro, Ghidra, Radare2 |

## Behavioral Analysis Checklist

```
[ ] Process creation/tree
[ ] File/registry modifications
[ ] Network connections (IPs, domains)
[ ] Persistence mechanisms
[ ] Anti-analysis techniques
[ ] Privilege escalation attempts
[ ] Payload extraction
[ ] C2 communication
```

## Network Analysis for Malware

**Traffic Patterns:**  
```
1. Initial beaconing
2. DGA domains
3. C2 callbacks
4. Data exfiltration
5. Lateral movement
```

**Protocols Used:**  
```
HTTP/HTTPS (most common)
DNS tunneling
ICMP tunneling
SMB (lateral movement)
```

## Advanced Persistent Threats (APTs)

**Characteristics:**  
- Long-term operations  
- Custom malware  
- Targeted attacks  
- Nation-state actors  

**Kill Chain:**  
```
Recon → Weaponization → Delivery → Exploitation → Installation → C2 → Actions
```

## Malware Evasion Techniques

1. **Obfuscation**  
   ```
   Packers: UPX, ASPack
   Crypters: Custom encryption
   ```

2. **Anti-VM**  
   ```
   Check VM artifacts
   Registry keys
   Hardware fingerprint
   ```

3. **Process Hollowing**  
   ```
   Inject into legitimate process
   svchost.exe, explorer.exe
   ```

## Detection Engineering

**YARA Rules** (signature creation)  
**Sigma Rules** (log-based detection)  
**IOC Hunting** (hashes, IPs, domains)  

## Summary Table: Malware Types

| Type | Replication | Host Required | Network Spread | User Interaction |
|------|-------------|---------------|----------------|------------------|
| Virus | Yes | Yes | No | Yes |
| Worm | Yes | No | Yes | No |
| Trojan | No | No | Varies | Yes |
| Ransomware | No | No | Varies | No |
| Rootkit | No | Yes | No | No |
