
# Module 11: Session Hijacking

## 1. Session Hijacking Concepts

**Definition:**  
Stealing/manipulating session ID to take control of active client-server session.

**Mechanism:**  
```
User login → Session ID created → Attacker steals ID
→ Impersonates user → Full access without credentials
```

**Example:**  
Banking site session cookie stolen → attacker transfers funds.

---

## 2. Why Successful

**Reasons:**  
1. **Weak session management** (predictable IDs)  
2. **HTTP** (unencrypted)  
3. **Poor cookies** (no HttpOnly/Secure flags)  
4. **No validation** (IP/User-Agent binding)  
5. **Client-side flaws** (XSS)  

---

## 3. Session Hijacking Process

```
1. User authenticates → Session ID issued
2. Session ID transmitted (cookies/URLs)
3. Attacker intercepts/predicts ID
4. Attacker uses stolen ID
5. Server treats attacker as legitimate user
```

---

## 4. Types of Session Hijacking

| Type | Description |
|-----|-------------|
| **Active** | Disrupt client, take over session |
| **Passive** | Silently monitor traffic |
| **Network-Level** | TCP/IP attacks |
| **Application-Level** | Cookie/token theft |

---

## 5. Packet Analysis (Local Hijack)

**Capture:** HTTP headers → Extract cookies  
```
Cookie: PHPSESSID=abcd1234
```
**Tool:** Wireshark  

---

## 6. Application-Level Attacks

### 6.1 Sniffing Session IDs
**HTTP traffic** → Wireshark captures cookies  

### 6.2 Predicting Tokens
**Weak randomization** → Sequential IDs  
```
user001, user002...
```

### 6.3 Man-in-the-Middle (MITM)
**ARP spoofing** → Intercept all traffic  

### 6.4 Man-in-the-Browser (MITB)
**Browser malware** → Real-time request modification  

### 6.5 CSRF
```
Authenticated user → Malicious request → Unauthorized action
```

### 6.6 Session Fixation
```
Attacker forces known session ID → Victim logs in → Attacker reuses
```

### 6.7 Session Replay
```
Captured session data reused
```

---

## 7. Network-Level Hijacking

### 7.1 TCP Session Hijacking
**Predict sequence numbers** → Inject packets  

### 7.2 IP Spoofing
**Fake source IP** → Impersonate trusted systems  

### 7.3 RST Hijacking
**TCP Reset packets** → Terminate + takeover  

### 7.4 Blind Hijacking
**No traffic visibility** → Guess sequence numbers  

### 7.5 UDP Hijacking
**No session control** → Easy spoofing  

---

## 8. Tools

| Tool | Purpose |
|------|---------|
| **Wireshark** | Packet capture |
| **Ettercap** | MITM |
| **Burp Suite** | Web proxy |
| **Bettercap** | Modern MITM |
| **Cain & Abel** | Password recovery |

---

## 9. Countermeasures

### 9.1 Prevention
```
HTTPS/TLS encryption
Strong random session IDs
HttpOnly + Secure cookies
Session timeout (15-30 min)
Regenerate ID after login
IP/User-Agent binding
CSRF tokens
```

### 9.2 Detection
```
Session anomaly monitoring
IP change detection
Traffic analysis (IDS)
WAF rules
```

### 9.3 Advanced
```
• Certificate pinning
• MFA
• Token binding
• IPsec VPN
```

### 9.4 User Practices
```
• Avoid public Wi-Fi
• Logout after use
• No suspicious links
```

---

## Attack Summary

| Attack Type | Method | Countermeasure |
|-------------|--------|----------------|
| **Sniffing** | HTTP capture | **HTTPS** |
| **Prediction** | Weak tokens | **Random IDs** |
| **MITM** | ARP spoofing | **VPN/IPsec** |
| **CSRF** | Malicious requests | **CSRF tokens** |
| **Fixation** | Forced session ID | **Regeneration** |

**Most Critical:** **MITM via ARP poisoning** + **Weak session management**

