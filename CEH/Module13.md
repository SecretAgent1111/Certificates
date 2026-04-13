
# Module 13: Web Server Technologies & Attacks

## 1. Web Server Security Issues

**Why Vulnerable:** Publicly accessible despite protections.

**Top Issues:**  
1. **Improper permissions** → Config/DB exposure  
2. **Default files** (`/backup.zip`) → Credentials  
3. **Misconfigurations** (directory listing)  
4. **Software bugs** → RCE  
5. **Debug endpoints** → Internal info  
6. **Weak SSL** → MITM  

**Impact:**  
- Account compromise  
- **Defacement**  
- Data theft  
- **Root access**  

---

## 2. Apache Architecture

**Components:**  
```
HTTP Client → Apache Core → Application Server
              (mod_ssl, mod_auth, mod_rewrite)
```

**Modules:**  
- **mod_ssl** → HTTPS  
- mod_proxy → Reverse proxy  

**Flow:**  
```
Request → Modules → PHP → Response
```

---

## 3. Apache Vulnerabilities

| Vulnerability | Impact |
|---------------|--------|
| **HTTP Response Splitting** | XSS/cache poisoning |
| **HTTP/2 DoS** | Memory exhaustion |
| **mod_macro Buffer Overflow** | RCE |
| **DNS Rebinding** | Internal access |
| **Path Traversal** | `../../etc/passwd` |
| **SQL Injection** | Data theft |

---

## 4. IIS Architecture

**Layers:**  
```
Kernel: HTTP.sys
User: WAS + WWW Service + w3wp.exe (Worker Process)
Pools: Application isolation
```

**Key:** **HTTP.sys** (kernel-mode performance)

---

## 5. IIS Vulnerabilities

| Issue | Impact |
|-------|--------|
| **Trust Boundary Violation** | Unauthorized access |
| **Authentication Bypass** | No login required |
| **CRLF XSS** | Script injection |
| **Directory Traversal** | Arbitrary file access |

---

## 6. Nginx Architecture

**Key Features:**  
- **Event-driven** (non-blocking)  
- **Master + Worker processes**  

**Components:**  
```
Master → Workers → Backend/Load Balancer/Cache
```

---

## 7. Nginx Vulnerabilities

| Vulnerability | Impact |
|---------------|--------|
| **SSRF** | Internal scanning |
| **NULL Pointer (HTTP/3)** | Crash/RCE |
| **RCE** | Code execution |
| **OS Command Injection** | Shell access |

---

## 8. Attack Methodology

```
1. Info Gathering (robots.txt, Shodan)
2. Enumeration (users, directories)
3. Vulnerability Scanning
4. Exploitation
5. Privilege Escalation
6. Persistence
7. Covering Tracks
```

---

## 9. Common Attacks

| Attack | Description |
|--------|-------------|
| **DNS Hijacking** | Redirect traffic |
| **Directory Traversal** | Access restricted files |
| **Web Cache Poisoning** | Serve malicious content |
| **SSH/FTP Brute Force** | Credential guessing |
| **HTTP/2 Flood** | DoS |

---

## 10. Countermeasures

**Hardening:**  
```
• Patch regularly
• Secure configs
• Disable unused services
• Strong auth
• Network segmentation
```

**Monitoring:**  
- **SIEM**  
- Log analysis  
- **WAF/IDS**  

**Patching:**  
```
Identify → Test → Deploy → Verify
```

---

## Web Server Comparison

| Server | Strengths | Weaknesses |
|--------|-----------|------------|
| **Apache** | Modular | Complex config |
| **IIS** | Windows integration | MS-specific |
| **Nginx** | **Performance** | Limited modules |

**Most Targeted:** **Apache** (market share + modules)

