
# Module 17: Mobile Platform Hacking

## 1. Mobile Attack Vectors

**Definition:** Paths exploiting mobile devices/apps/networks.

**Why Targeted:**  
```
• Sensitive data storage
• Always connected
• Multiple APIs/apps
```

**Vectors:**  
```
Malicious apps | Insecure Wi-Fi | SMS attacks
Bluetooth | OS vulnerabilities | Social engineering
```

---

## 2. OWASP Mobile Top 10 (2024)

| Risk | Description |
|------|-------------|
| **Improper Credentials** | Weak auth tokens |
| **Insecure Auth** | Poor login flows |
| **Insufficient Crypto** | Weak encryption |
| **Insecure Storage** | Unencrypted data |
| **Insecure Comm** | Plaintext traffic |
| **Code Tampering** | Modified apps |
| **Reverse Engineering** | App disassembly |
| **Misconfiguration** | Default settings |

---

## 3. Attack Lifecycle

```
1. Recon → Device/app intel
2. Delivery → Malicious app/SMS
3. Exploit → Vulnerability trigger
4. Install → Malware deployment
5. C2 → Attacker control
6. Exfil → Data theft
```

---

## 4. Key Attack Types

| Attack | Method | Impact |
|--------|--------|--------|
| **SMiShing** | Fake SMS links | **Credential theft** |
| **Agent Smith** | App replacement | Data + ads |
| **SS7** | Telecom protocol | **OTP intercept** |
| **Simjacker** | SIM toolkit | Location tracking |
| **Call Spoofing** | Fake caller ID | Social engineering |

---

## 5. Mobile Device Management (MDM)

**Architecture:**  
```
Devices ↔ Firewall/DMZ ↔ MDM Server ↔ Admin Console
```

**Benefits:**  
```
App deployment | Policy enforcement
Device monitoring | Data protection
```

---

## 6. BYOD Risks

```
Data leakage | Malware | No control
```

**Controls:**  
```
Device registration | Compliance checks
Access restrictions
```

---

## 7. Countermeasures

**User:**  
```
✅ Trusted app stores only
✅ OS updates
✅ Strong auth
❌ Avoid public Wi-Fi
```

**Admin:**  
```
✅ MDM deployment
✅ Encryption
✅ Monitoring
```

**OTP:**  
```
✅ App-based MFA (not SMS)
✅ SIM lock
```

---

## 8. Security Tools

| Category | Purpose |
|----------|---------|
| **Source Analysis** | Code vulnerabilities |
| **Reverse Engineering** | APK/IPA analysis |
| **App Repackaging** | Detect modifications |
| **Mobile Pentest** | Security testing |
| **Anti-Spyware** | Spyware detection |

---

## Attack Summary

| Vector | Attack | Defense |
|--------|--------|---------|
| **App** | **Fake apps** | **MDM + app vetting** |
| **SMS** | **SMiShing** | **App MFA** |
| **Network** | **Public Wi-Fi** | **VPN** |
| **SIM** | **SS7/Simjacker** | **SIM PIN** |
| **OS** | **Vulnerabilities** | **Patches** |

**Most Dangerous:** **SS7 + SMiShing** (bypass 2FA)

