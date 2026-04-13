
# Module 10: Denial-of-Service (DoS/DDoS)

## 1. DoS Attack

**Definition:**  
Attack preventing legitimate users from accessing services by overwhelming resources.

**Targets:**  
- CPU, Memory, Bandwidth, Threads  

**Single Source:** One attacker machine.  

**Mechanism:**  
```
Mass illegitimate requests → Resource exhaustion
→ Legitimate users denied service
```

**Examples:**  
- HTTP flood  
- DNS resolution attack  

**Impact:**  
- Financial loss  
- Reputation damage  
- Operational disruption  

---

## 2. DDoS Attack

**Definition:**  
**Distributed** DoS using **botnet** (multiple compromised systems).  

**Components:**  
```
Botmaster ← C2 Server ← Bots (zombies) → Target
```

**Working:**  
1. Malware infects devices  
2. Bots connect to C2  
3. **Simultaneous attack** → overwhelms target  

**Example:**  
**Mirai botnet** (IoT DDoS).  

---

## 3. DoS vs DDoS Comparison

| Feature | DoS | DDoS |
|---------|-----|------|
| **Source** | Single | **Multiple** |
| **Detection** | Easier | **Harder** |
| **Impact** | Moderate | **Severe** |
| **Mitigation** | Easier | **Complex** |

---

## 4. Botnet

**Definition:**  
Network of compromised computers controlled by attacker.  

**Lifecycle:**  
```
1. Malware creation/hosting
2. Infection (phishing/exploits)
3. C2 connection
4. Attack commands
5. DDoS execution
```

**Uses:**  
- DDoS, spam, data theft, extortion  

---

## 5. Scanning Methods (Malware Propagation)

| Method | Description | Example |
|--------|-------------|---------|
| **Random** | Probe random IPs | Internet worms |
| **Hit-list** | Predefined targets | Targeted servers |
| **Topological** | Use infected system data | Email contacts |
| **Subnet** | Scan local network | Corporate LAN |
| **Permutation** | Avoid duplicates | Coordinated bots |

---

## 6. Propagation Methods

1. **Central Source**  
   ```
   Attacker server → Victims download malware
   ```

2. **Back-Chaining**  
   ```
   Infected system → infects others
   ```

3. **Autonomous**  
   ```
   Self-spreading (WannaCry)
   ```

---

## 7. DoS/DDoS Attack Categories (CRITICAL)

### 1. Volumetric Attacks
**Target:** **Bandwidth**  
**Measurement:** **bps**  
```
UDP flood, ICMP flood, NTP amplification
```

### 2. Protocol Attacks
**Target:** **Network stack**  
**Measurement:** **pps**  
```
**SYN flood**, ACK flood, TCP state exhaustion
```

### 3. Application Layer Attacks
**Target:** **Application**  
**Measurement:** **RPS**  
```
HTTP flood, **Slowloris**, DNS query flood
```

**Difficulty:** Volumetric < Protocol < **Application (hardest)**

---

## 8. Countermeasures

**Detection:**  
- Traffic monitoring  
- **Anomaly detection**  
- NetFlow analysis  

**Mitigation:**  
```
• Rate limiting
• Traffic filtering
• Load balancing
• Blackholing
• CDN/Anycast
```

**Botnet Defense:**  
- Endpoint security  
- Network segmentation  

**ISP Protection:**  
- **Traffic scrubbing**  
- Upstream filtering  

**Tools/Services:**  
- **Cloudflare, Akamai**  
- **AWS Shield**  

---

## Attack Summary Table

| Category | Measurement | Examples | Countermeasure |
|----------|-------------|----------|----------------|
| **Volumetric** | **bps** | UDP/ICMP flood | **Bandwidth scrubbing** |
| **Protocol** | **pps** | **SYN flood** | SYN cookies, rate limiting |
| **Application** | **RPS** | HTTP flood, Slowloris | WAF, behavioral analysis |

**Most Critical:** **SYN Flood** + **Application Layer** (hardest to detect/mitigate)

