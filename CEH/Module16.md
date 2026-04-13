# Module 16: Wireless Networks

## 1. Wireless Networks

**Definition:**  
**IEEE 802.11** networks using RF signals (no cables).

**Components:**  
```
Access Point (AP) ↔ Clients ↔ Router/Internet
```

**Types:**  
- Wired extension  
- Multi-AP (campus)  
- LAN-to-LAN  
- **5G hotspot**  

---

## 2. Wireless Standards (802.11)

| Standard | Freq | Speed | Range |
|----------|------|-------|-------|
| **802.11** | 2.4GHz | 1-2Mbps | 20-100m |
| **802.11a** | **5GHz** | **54Mbps** | 35-100m |
| **802.11b** | 2.4GHz | 11Mbps | 35-140m |
| **802.11g** | 2.4GHz | 54Mbps | 38-140m |
| **802.11n** | 2.4/5GHz | **600Mbps** | ~70m |
| **802.11ac** | 5GHz | **1Gbps+** | ~35m |
| **802.11ax (Wi-Fi 6)** | 2.4-5GHz | **2400Mbps** | ~240m |

**Key:** **5GHz = faster but less range**

---

## 3. Authentication

**PSK (Personal):**  
```
Shared password → Home networks
Weak: Dictionary attacks
```

**RADIUS (Enterprise):**  
```
Client → AP → RADIUS Server → Auth
Strong: Individual credentials
```

---

## 4. Wireless Encryption

### WEP (Deprecated)
```
RC4 + 24-bit IV + CRC-32
**Broken**: IV reuse, easy cracking
```

### WPA2
```
**AES-CCMP**
Personal (PSK) | Enterprise (RADIUS)
KRACK vulnerability
```

### **WPA3** (Current)
```
**AES-GCMP-256 + SAE**
Password brute-force resistant
Forward secrecy
```

---

## 5. Wireless Threats

**Availability:**  
```
• Deauth attacks
• Beacon flooding
• AP theft
```

**Authentication:**  
```
• PSK cracking
• **KRACK** (key reinstall)
• Password guessing
```

---

## 6. Hacking Methodology

```
1. Discovery (airodump-ng)
2. Analysis (encryption type)
3. Attacks (deauth, rogue AP)
4. **Cracking** (handshake capture)
```

---

## 7. Countermeasures

**Encryption:** **WPA3**  
**Rogue AP:** **WIPS/WIDS**  
**Password:** Complex + rotate  
**Monitoring:** Wireless IDS  

**Limited Value:**  
```
❌ SSID hiding
❌ MAC filtering
```

---

## 8. Wireless Tools

| Tool | Purpose |
|------|---------|
| **airodump-ng** | **Discovery/capture** |
| **Kismet** | Wireless IDS |
| **Aircrack-ng** | Cracking |
| **NetStumbler** | Windows scanning |

---

## Attack Summary

| Attack | Target | Countermeasure |
|--------|--------|----------------|
| **Deauth** | Availability | **WIPS blocking** |
| **PSK Cracking** | **Password** | **WPA3-SAE** |
| **Rogue AP** | MITM | Certificate pinning |
| **KRACK** | Key reinstall | **Firmware patch** |

**Most Dangerous:** **Rogue AP + KRACK combo**

