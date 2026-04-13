
# Module 5: Vulnerability Analysis and Assessment

## 1. Vulnerability Scoring Systems and Databases

### 1.1 Common Vulnerability Scoring System (CVSS)

**Definition:**  
CVSS is a standardized framework used to measure and communicate the severity of software vulnerabilities using a numerical score from 0.0 to 10.0.

**Explanation:**  
- Based on:  
  - Exploitability  
  - Impact  
  - Complexity  
- Helps prioritize vulnerabilities by risk level  

**CVSS Severity Ratings:**  

| Severity  | Score Range  |
|-----------|--------------|
| None      | 0.0          |
| Low       | 0.1 – 3.9    |
| Medium    | 4.0 – 6.9    |
| High      | 7.0 – 8.9    |
| Critical  | 9.0 – 10.0   |

**Example:**  
CVSS Score: 9.8 → Remote code execution → Urgent patching required.

---

### 1.2 Common Vulnerabilities and Exposures (CVE)

**Definition:**  
Public database of known vulnerabilities with unique IDs.

**Format:**  
`CVE-YYYY-XXXX`

**Maintained by:**  
MITRE  

**Provides:**  
- Standard naming  
- Vulnerability descriptions  

**Example:**  
`CVE-2021-44228` (Log4Shell) → Log4j vulnerability.

---

### 1.3 National Vulnerability Database (NVD)

**Definition:**  
U.S. government repository enhancing CVE data.

**Maintained by:**  
NIST  

**Adds to CVE:**  
- CVSS scores  
- Impact analysis  
- Fix recommendations  

**Used by:**  
- Security tools  
- Risk analysts  

---

### 1.4 Common Weakness Enumeration (CWE)

**Definition:**  
Classification system for software weaknesses (root causes).

**Examples:**  
- CWE-89 → SQL Injection  
- Buffer overflow  
- Improper input validation  

**Purpose:**  
- Helps developers prevent vulnerabilities  

---

## 2. Vulnerability Management Life Cycle

**Definition:**  
Structured process to identify, evaluate, remediate, and monitor vulnerabilities continuously.

**Phases:**  

1. **Identify Assets**  
   - Discover: systems, devices, applications  
   - Example: Server inventory, cloud resources  

2. **Create Baseline**  
   - Define normal/secure configuration  

3. **Vulnerability Scanning**  
   - Automated system scanning  

4. **Vulnerability Analysis**  
   - Remove false positives  

5. **Risk Assessment**  
   - Prioritize by CVSS + business impact  

6. **Remediation**  
   - Patch, reconfigure  

7. **Verification**  
   - Confirm fixes  

8. **Monitoring**  
   - Continuous vulnerability tracking  

---

## 3. Vulnerability Scanning and Analysis

### 3.1 Vulnerability Scanning

**Definition:**  
Analyzing systems, services, and configurations to identify vulnerabilities and design flaws.

**Targets:**  
- Operating systems  
- Applications  
- Network services  

**Detects:**  
- Misconfigurations  
- Outdated software  

**Example:**  
Outdated Apache server with known vulnerabilities.

---

### 3.2 Vulnerability Analysis

**Definition:**  
Identifying, evaluating, and prioritizing security weaknesses.

**Classification:**  
- **Severity:** Low/Medium/High  
- **Exploit Range:** Local/Remote  

**Goal:**  
- Understand vulnerability nature  
- Assess potential impact  
- Develop mitigation strategy  

**Example:**  
Remote access vulnerability → High severity.

---

## 4. Types of Vulnerability Scanning

1. **External Scanning**  
   - From outside network (attacker perspective)  
   - Identifies public exposures  

2. **Internal Scanning**  
   - Inside network  
   - Detects internal misconfigurations  

3. **Host-Based Scanning**  
   - Individual systems  
   - Checks: file systems, configurations, registry  

4. **Network-Based Scanning**  
   - Network infrastructure  
   - Identifies network-level issues  

5. **Application Scanning**  
   - Web applications  
   - Misconfigurations, outdated components  

6. **Credentialed Scanning**  
   - Uses valid credentials  
   - **Advantage:** Deep, accurate results  

7. **Non-Credentialed Scanning**  
   - No login access  
   - **Limitation:** Limited visibility  

8. **Manual Scanning**  
   - Human testing  
   - **Advantage:** High accuracy  

9. **Automated Scanning**  
   - Tools: Nessus, Qualys, GFI LanGuard  

---

## 5. Vulnerability Assessment Tools

### 5.1 Nessus Essentials

**Definition:**  
Popular vulnerability scanner for identifying vulnerabilities, misconfigurations, and malware.

**Features:**  
- Wide plugin support  
- CVE-based detection  
- Reporting capabilities  

**Use Case:**  
Enterprise vulnerability management.

---

### 5.2 GFI LanGuard

**Definition:**  
Network and device vulnerability scanner with patch management.

**Features:**  
- Patch management  
- Network auditing  

---

### 5.3 OpenVAS

**Definition:**  
Open-source vulnerability scanning framework.

**Features:**  
- Comprehensive scanning  
- Regular updates  

---

### 5.4 Nikto

**Definition:**  
Web server scanner.

**Detects:**  
- Dangerous files  
- Misconfigurations  
- Outdated software  

**Example:**  
Detects `/admin`, `/phpinfo.php`.

---

## 6. Vulnerability Assessment Reports

**Definition:**  
Structured document summarizing vulnerability assessment findings.

**Key Sections:**  

1. **Executive Summary**  
   - Objectives, scope, key findings  

2. **Risk Assessment**  
   - Severity classification  
   - Impact analysis  

3. **Assessment Overview**  
   - Methodology, tools, scope  

4. **Findings**  
   - Vulnerabilities  
   - Affected systems  
   - Evidence  

5. **Recommendations**  
   - Fix strategies  
   - Patch guidance  

6. **Appendices**  
   - Logs, technical data  

7. **Conclusion**  
   - Risk posture summary  

8. **Follow-Up Actions**  
   - Remediation timeline  
   - Re-testing plans  

9. **Glossary**  
   - Technical term definitions  
