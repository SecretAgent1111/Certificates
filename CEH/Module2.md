# Module 2: Reconnaissance and Footprinting

## 1. Reconnaissance

**Definition:**  
Reconnaissance (Footprinting) is the initial phase of an attack where an attacker gathers as much information as possible about the target before launching an attack.

**Objective:**  
- Understand target environment  
- Identify attack surface  
- Reduce detection risk  

### Types of Reconnaissance

#### 1. Passive Reconnaissance

**Definition:**  
Gathering information without directly interacting with the target system.

**Techniques:**  
- OSINT (Open Source Intelligence)  
- Public records  
- Social media analysis  
- Third‑party databases  

**Examples:**  
- Searching company details on Google  
- LinkedIn employee enumeration  

**Advantages:**  
- Hard to detect  
- Low risk  

---

#### 2. Active Reconnaissance

**Definition:**  
Gathering information by direct interaction with the target.

**Techniques:**  
- DNS interrogation  
- Port scanning  
- Network scanning  
- Social engineering  

**Examples:**  
- Nmap scan on target IP  
- Banner grabbing  

**Disadvantages:**  
- Detectable  
- Can trigger alerts  

---

## 2. Footprinting Using Google Hacking (Google Dorking)

**Definition:**  
Using advanced Google search operators to find sensitive or hidden information.

**Purpose:**  
- Discover exposed data  
- Identify vulnerabilities  
- Find login pages, configs  

**Common Google Operators:**  

| Operator        | Purpose                          |
|-----------------|----------------------------------|
| `cache:`        | View cached pages               |
| `link:`         | Find pages linking to a site    |
| `related:`      | Find similar sites              |
| `info:`         | Info about a site               |
| `site:`         | Restrict search to domain       |
| `allintitle:`   | Keywords in title               |
| `intitle:`      | Specific keyword in title       |
| `allinurl:`     | Keywords in URL                 |
| `inurl:`        | Keyword in URL                  |
| `location:`     | Search by location              |

**Examples:**  
- `site:example.com filetype:pdf`  
- `inurl:admin login`  

**Real Attack Scenario:**  
Attacker finds an exposed `.env` file containing credentials.

---

## 3. Finding Domains & Subdomains

**Definition:**  
Identifying all domains and subdomains related to a target organization.

**Techniques:**  
- Search engines (Google, Bing)  
- Tools:  
  - Netcraft  
  - DNSdumpster  
  - Sublist3r  

**Purpose:**  
- Expand attack surface  
- Discover hidden assets  

**Example:**  
- Main domain: `example.com`  
- Subdomains:  
  - `admin.example.com`  
  - `dev.example.com`  

---

## 4. Extracting Website Information (archive.org)

**Definition:**  
Using archived versions of websites to gather historical data.

**Tool:**  
- Wayback Machine (`archive.org`)  

**Purpose:**  
- View old pages  
- Discover hidden endpoints  
- Find removed sensitive data  

**Example:**  
Old login panel still accessible.

**Tool Mentioned:**  
- Photon (extract archived URLs)  

---

## 5. Gathering Information from LinkedIn

**Definition:**  
Using social media for intelligence gathering.

**Tool:**  
- theHarvester  

**Information Collected:**  
- Employee names  
- Job roles  
- Locations  
- Technologies used  

**Use Case:**  
Target employees for phishing attacks.

---

## 6. WHOIS Lookup

**Definition:**  
WHOIS provides registration details of a domain.

**Information Obtained:**  
- Domain owner  
- Contact details  
- Name servers  
- Creation date  
- Expiry date  
- NetRange  

**Uses for Attackers:**  
- Social engineering  
- Network mapping  
- Identifying infrastructure  

**Organizations (RIRs):**  
- ARIN  
- RIPE NCC  
- APNIC  
- AFRINIC  
- LACNIC  

---

## 7. DNS Lookup with AI

**Concept:**  
Using AI tools (like ChatGPT) to automate DNS enumeration.

**Example Task:**  
Running DNSRecon for:
- Subdomains  
- DNS records  

**Output Includes:**  
- A records  
- MX records  
- NS records  

**Real‑World Use:**  
- Faster reconnaissance  
- Automation of enumeration  

---

## 8. Traceroute

**Definition:**  
A network diagnostic tool that identifies the path packets take to reach a destination.

**Protocols Used:**  
- ICMP  
- TCP  
- UDP  

**Types:**  
- **ICMP Traceroute** – Default in Windows  
- **TCP Traceroute** – Bypasses firewall restrictions  
- **UDP Traceroute** – Default in Linux  

**Purpose:**  
- Identify intermediate routers  
- Map network path  

---

## 9. Traceroute Analysis

**Explanation:**  
Analyzing traceroute output to identify:
- Routers  
- Firewalls  
- Internal network structure  

**Example Insight:**  
Last hops reveal:
- DMZ  
- Internal servers  
- Firewalls  

**Attack Value:**  
Helps map internal network layout.

---

## 10. Information Gathering via Physical/Social Techniques

1. **Eavesdropping**  
   - Listening to communication  
   - Example: Capturing WiFi traffic  

2. **Shoulder Surfing**  
   - Watching user input (passwords)  

3. **Dumpster Diving**  
   - Searching trash for sensitive info  

4. **Impersonation**  
   - Pretending to be an authorized user  

---

## 
