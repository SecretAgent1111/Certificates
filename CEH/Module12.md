
# Module 12: Evading IDS, Firewalls, and Honeypots

## 1. IDS vs IPS

| Feature | IDS | IPS |
|---------|-----|-----|
| **Action** | **Detect + Alert** | **Detect + Block** |
| **Placement** | Monitor | Inline |

**Detection Engines:**  
1. **Signature** → Known attack patterns  
2. **Anomaly** → Baseline deviations  
3. **Protocol** → RFC violations  

**Flow:**  
```
Traffic → Signature → Anomaly → Protocol → Action (Drop/Alert)
```

---

## 2. IDS Detection Types

### Signature (Misuse)
```
Known malware hashes
SQL injection patterns
```
**Limitation:** Zero-days  

### Anomaly
```
10K req/sec from one user
```
**Issue:** False positives  

### Protocol Anomaly
```
Malformed TCP headers
```

---

## 3. IDS Types

| Type | Scope | Example |
|------|-------|---------|
| **NIDS** | **Network-wide** | Gateway monitoring |
| **HIDS** | **Single host** | File integrity |

---

## 4. IDS Alerts

| Alert Type | Attack | Detection |
|------------|--------|-----------|
| **True Positive** | ✅ | ✅ |
| **False Positive** | ❌ | ✅ |
| **False Negative** | ✅ | ❌ **DANGEROUS** |
| **True Negative** | ❌ | ❌ |

---

## 5. Firewall Architecture

| Type | Description |
|------|-------------|
| **Bastion Host** | Hardened internet-facing system |
| **Screened Subnet (DMZ)** | Public services isolated |
| **Multi-Homed** | Multiple interfaces |

---

## 6. IDS/IPS Tools

**IDS:**  
- **Suricata** (real-time DPI)  
- Zeek, OSSEC, Samhain  

**IPS:**  
- **Trellix IPS**  
- Check Point, Cisco NGIPS  

---

## 7. IDS/Firewall Evasion (15 Techniques)

| # | Technique | Method |
|---|-----------|--------|
| 1 | **Firewalking** | TTL mapping |
| 2 | **Banner Grabbing** | Service fingerprinting |
| 3 | **IP Spoofing** | Fake source IP |
| 4 | **Source Routing** | Path manipulation |
| 5 | **Tiny Fragments** | Fragment reassembly bypass |
| 6 | IP vs URL | Avoid DNS filtering |
| 7 | **Proxy Servers** | Hide origin |
| 8 | **ICMP Tunneling** | Data in ping |
| 9 | ACK/HTTP Tunneling | Allowed protocols |
| 10 | **SSH/DNS Tunneling** | Covert channels |
| 11 | External Systems | Third-party relay |
| 12 | **MITM** | Traffic interception |
| 13 | **Content/XSS** | Script injection |
| 14 | HTML Smuggling | Browser payload |
| 15 | **Windows BITS** | Legit service abuse |

---

## 8. NAC/Endpoint Evasion (Key Techniques)

**Network:**  
- VLAN hopping  
- Pre-auth device  
- Ghostwriting  

**Execution:**  
```
• Dechaining macros
• LOLBins (living-off-land)
• CPL sideloading
• AMSI bypass
• Process injection
```

**Advanced:**  
- **Signed binary proxy**  
- Shellcode encryption  
- **Sandbox escape**  

---

## 9. Honeypot Concepts

**Definition:**  
**Decoy system** attracting attackers for study.  

**Types:**  
| Type | Risk | Intelligence |
|------|------|--------------|
| **Low Interaction** | **Low** | **Limited** |
| **High Interaction** | **High** | **Rich** |

**Tools:**  
- **Honeyd, Dionaea, Cowrie**  

**Detection (Attacker View):**  
- Low activity  
- Fake services  

---

## 10. Countermeasures

**IDS Evasion:**  
```
• Traffic normalization
• Fragment reassembly
• Anomaly detection
```

**Firewall:**  
```
• Deep packet inspection
• Block tunneling
```

**Endpoint:**  
```
• EDR + behavioral analysis
• Memory scanning
```

**Honeypot Defense:**  
```
• Multiple honeypots
• Deception networks
```

---

## Evasion Summary Table

| Target | Technique | Countermeasure |
|--------|-----------|----------------|
| **IDS** | Fragmentation | **Reassembly** |
| **Firewall** | **Tunneling** | DPI + protocol filtering |
| **Endpoint** | **LOLBins** | Behavioral EDR |
| **NAC** | VLAN hopping | **Port security** |

**Most Dangerous:** **False Negatives** + **Advanced tunneling**

