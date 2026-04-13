
# Module 14: Web Application Hacking

## 1. Web Applications

**Definition:**  
Browser-accessed applications generating dynamic content via server-side processing.

**Security Issues:**  
- **SQL Injection**  
- **XSS**  
- **Session Hijacking**  

**Flow:**  
```
User → HTTP → Firewall → Web Server → App Server → DB → Response
```

---

## 2. OWASP Top 10 (2021)

| # | Risk | Examples |
|---|------|----------|
| **A01** | **Broken Access Control** | Directory traversal |
| **A02** | Cryptographic Failures | Cookie sniffing |
| **A03** | **Injection** | **SQLi, XSS** |
| A04 | Insecure Design | Logic flaws |
| **A05** | **Security Misconfig** | Directory listing |
| A06 | Vulnerable Components | Old libraries |
| A07 | Auth Failures | Session hijacking |
| A08 | Integrity Failures | Deserialization |
| A09 | Logging Failures | Undetected attacks |
| **A10** | **SSRF** | Internal scanning |

---

## 3. Web Application Attacks (20+)

| Attack | Description |
|--------|-------------|
| **Directory Traversal** | `../../etc/passwd` |
| **Hidden Field Manipulation** | Change price=1000 → 10 |
| **Pass-the-Cookie** | Reuse stolen cookies |
| **SQL Injection** | Query injection |
| **Command Injection** | OS command execution |
| **XSS** | Script injection (3 types) |
| **CSRF** | Unauthorized actions |
| **XXE** | XML parser exploit |
| **SSRF** | Internal requests |
| **Clickjacking** | Invisible iframe |

---

## 4. Hacking Methodology (14 Phases)

```
1. Footprinting
2. Web app analysis
3. Bypass client controls
4. Attack auth
5. Attack authorization
6. Session attacks
7. Injection attacks
8. Business logic
9. Shared env attacks
10. Database attacks
11. Client-side attacks
12. Web services
13. Automation
```

---

## 5. Web API/Webhooks

**API Risks:**  
- **IDOR**  
- Parameter pollution  

---

## 6. Security Testing

| Type | Method | Tools |
|------|--------|-------|
| **Manual** | Human | **Burp Suite** |
| **Automated** | Scripts | Ranorex |
| **SAST** | **Source code** | **Codacy** |
| **DAST** | **Runtime** | **Acunetix** |

**Fuzz Testing:** Random inputs → crash hunting.

---

## 7. Injection Defenses

**XSS:**  
```
Input validation
Output encoding
HttpOnly cookies
WAF
```

**CRLF:**  
```
Encode newlines
Input filtering
```

---

## 8. Key Countermeasures

| Attack | Defense |
|--------|---------|
| **CSRF** | **Tokens + SameSite** |
| **Session** | **Secure/HttpOnly + HTTPS** |
| Clickjacking | **X-Frame-Options** |
| **Username Enum** | Generic errors + CAPTCHA |

**Advanced:**  
- **RASP** (runtime protection)  
- **WAF**  
- **CSP headers**  

---

## OWASP Top Threats Summary

```
1. Access Control (A01)
2. Injection (A03) ← CRITICAL
3. Misconfig (A05)
4. SSRF (A10)
```

**Most Dangerous:** **Injection + Access Control**

