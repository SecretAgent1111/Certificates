
# Module 4: Enumeration

## 1. Enumeration Concepts

**Definition:**  
Enumeration is the process of actively extracting detailed information about a target system, network, or domain after initial scanning. It involves establishing connections and querying services to gather usernames, machine names, shares, services, and other sensitive data.

**Explanation:**  
- Enumeration comes after scanning (e.g., Nmap)  
- Unlike passive reconnaissance, enumeration is active and intrusive  
- Uses protocols like:  
  - NetBIOS  
  - SNMP  
  - LDAP  
  - DNS  
  - SMTP  

**Key Information Gathered:**  
- User accounts (valid usernames)  
- Group memberships  
- Network shares  
- Hostnames  
- Running services  
- Domain information  
- Password policies  

**Why Critical:**  
- Enables targeted attacks  
- Password attacks (brute force, credential stuffing)  
- Privilege escalation  
- Lateral movement  

**Example:**  
Attacker finds:  
- Username: admin, john  
- Open SMB shares  
→ Attempts SMB login brute force or accesses shared files.

---

## 2. NetBIOS Enumeration

**Definition:**  
Extracting network-related information from Windows systems using NetBIOS protocol.

**Explanation:**  
- Operates over TCP/IP (ports 137, 138, 139)  
- Used for file/printer sharing  
- Reveals:  
  - Computer names  
  - Shared resources  
  - Usernames  

**Data Extracted:**  
- NetBIOS name table  
- Logged-in users  
- Shared folders (SMB shares)  

**Tools:**  
- `nbtstat`  
- NetBIOS Enumerator  
- `enum4linux`  
- Nmap (nbstat script)  

**Example Command:**  
```
nbtstat -A <target IP>
```
**Output:**  
- Hostname  
- Workgroup/domain  
- MAC address  

**Attack Scenario:**  
Enumerates SMB shares → finds open share with sensitive files → gains credentials.

---

## 3. SNMP Enumeration

**Definition:**  
Extracting device/network management information from SNMP-enabled systems.

**Explanation:**  
- Uses UDP port 161  
- Community strings act like passwords:  
  - `public` (read-only)  
  - `private` (read-write)  
- Weak/default strings = major vulnerability  

**Information Retrieved:**  
- System name  
- Installed software  
- Running processes  
- Network interfaces  
- Routing tables  

**Tools:**  
- `snmpwalk`  
- `snmp-check`  
- Nmap SNMP scripts  

**Example:**  
```
snmpwalk -v2c -c public <target IP>
```

**Scenario:**  
Misconfigured SNMP reveals network structure → aids lateral movement.

---

## 4. LDAP Enumeration

**Definition:**  
Extracting directory services data from Active Directory environments.

**Explanation:**  
- Uses port 389  
- Central to Windows domains  
- Queries: users, groups, OUs  

**Data Extracted:**  
- Usernames  
- Group memberships  
- Domain structure  
- Password policies  

**Tools:**  
- `ldapsearch`  
- `enum4linux`  
- BloodHound  

**Example:**  
```
ldapsearch -x -h <target IP>
```

**Scenario:**  
Maps AD environment → targets admin users for credential attacks.

---

## 5. NTP Enumeration

**Definition:**  
Gathering time synchronization data and system details.

**Explanation:**  
- Uses UDP port 123  
- Reveals:  
  - System uptime  
  - Connected peers  

**Tools:**  
- `ntpq`  
- Nmap  

**Example:**  
```
ntpq -p <target IP>
```

**Security Impact:**  
Shows system uptime, network relationships.

---

## 6. NFS Enumeration

**Definition:**  
Identifying shared directories in Unix/Linux systems.

**Explanation:**  
- Uses port 2049  
- Misconfigurations allow remote file access  

**Information:**  
- Shared directories  
- Access permissions  

**Tools:**  
- `showmount`  
- Nmap  

**Example:**  
```
showmount -e <target IP>
```

**Scenario:**  
Open NFS share → attacker mounts and accesses files.

---

## 7. SMTP Enumeration

**Definition:**  
Identifying valid email users on a mail server.

**Explanation:**  
- Uses port 25  
- Commands: VRFY, EXPN, RCPT TO  

**Information:**  
- Valid email addresses  
- Mail server details  

**Tools:**  
- `telnet`  
- `smtp-user-enum`  

**Example:**  
```
VRFY admin
```

**Scenario:**  
Gathers emails → phishing/password attacks.

---

## 8. DNS Enumeration

**Definition:**  
Extracting domain-related information including subdomains.

**Explanation:**  
- Uses port 53  
- Techniques:  
  - Zone transfer  
  - Reverse lookup  
  - Brute-force subdomains  

**Information:**  
- Hostnames  
- Subdomains  
- IP addresses  

**Tools:**  
- `nslookup`  
- `dig`  
- `dnsenum`  
- `fierce`  

**Example:**  
```
dig axfr @<DNS server> <domain>
```

**Scenario:**  
Zone transfer reveals internal hosts → targets them.

---

## 9. Other Enumeration Techniques

**Protocols/Services:**  
- **RPC Enumeration**  
- **SMB Enumeration** (`enum4linux`)  
- **FTP Enumeration** (anonymous login)  
- **HTTP Enumeration** (`gobuster`, `dirb`)  

**Purpose:**  
Gather intelligence across all exposed services.

---

## 10. Enumeration Countermeasures

**Key Controls:**  

1. **Disable Unnecessary Services**  
   - NetBIOS (if unused)  
   - SNMP (or restrict access)  

2. **Strong Authentication**  
   - Strong passwords  
   - No default credentials  

3. **SNMP Hardening**  
   - Change community strings  
   - Use SNMPv3 (encrypted)  

4. **Disable Null Sessions**  
   - Prevent anonymous enumeration  

5. **DNS Hardening**  
   - Disable zone transfers  
   - Internal DNS segregation  

6. **SMTP Protection**  
   - Disable VRFY/EXPN  

7. **Network Segmentation**  
   - Limit lateral movement  

8. **Monitoring & Logging**  
   - Detect:  
     - Multiple failed logins  
     - SNMP queries from unknowns  
     - Enumeration patterns  
