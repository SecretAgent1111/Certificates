
# Module 15: SQL Injection

## 1. SQL Injection Concepts

**Definition:**  
Injecting malicious SQL via input fields to manipulate database.

**Root Cause:**  
```
No input validation + Dynamic query concatenation
```

**Example:**  
```
Normal: SELECT * FROM users WHERE id='10'
Injected: SELECT * FROM users WHERE id='' OR 1=1 --
→ Returns ALL users
```

**Impact:**  
- **Auth bypass**  
- Full DB access  

---

## 2. Affected Technologies

```
ASP.NET, PHP, JSP, Node.js, Python (Flask/Django)
```

---

## 3. HTTP POST Attack Vector

```
POST /login
username=admin&password=' OR 1=1 --
```

---

## 4. SQL Injection Types

| Type | Channel | Examples |
|------|---------|----------|
| **In-Band** | **Same channel** | **Error/Union-based** |
| **Blind** | **Indirect inference** | Boolean/Time-based |
| **Out-of-Band** | Separate channel | DNS/HTTP exfiltration |

---

## 5. Error-Based SQLi

**Uses DB errors** to extract structure:  
```
Error: Cannot connect via socket → MySQL
Error: OLE DB → SQL Server
```

**Techniques:**  
- **Parameter tampering** (`id=abc`)  
- **GROUP BY** (column enumeration)  
- **Type mismatch** (data type errors)  

---

## 6. UNION SQLi

**Combine queries:**  
```
?id=10 UNION SELECT username,password FROM users
```

---

## 7. Enumeration Queries

**Database:** `DB_NAME()`  
**Tables:** `sysobjects WHERE xtype='U'`  
**Columns:** `information_schema.columns`  
**Data:** `SELECT * FROM users`  

---

## 8. Blind SQLi

**Boolean:**  
```
?id=10 AND SUBSTRING(db_name(),1,1)='m'
Page loads → True
Page error → False
```

**Time-Based:**  
```
?id=10 AND IF(1=1,SLEEP(5),0)
Delay → True
```

---

## 9. Stored Procedure Injection

```
exec('SELECT * FROM users WHERE id=' + input)
```

---

## 10. Evasion Techniques (12 Methods)

| Technique | Example |
|-----------|---------|
| **Inline Comments** | `SELECT/**/id` |
| **Hex Encoding** | `0x61646d696e` |
| **Concatenation** | `'uni'+'on'` |
| **URL Encoding** | `%27OR%201=1` |
| **Case Variation** | `SeLeCt` |
| **Null Byte** | `%00` |

---

## 11. Countermeasures

**#1 Defense:** **Parameterized Queries**  
```
Prepared: SELECT * FROM users WHERE id=?
Safe: Input cannot alter structure
```

**Additional:**  
```
• Input validation (whitelist)
• Stored procedures (no dynamic SQL)
• ORM (Hibernate, Entity Framework)
• WAF rules
• Least privilege DB accounts
```

**Detection Indicators:**  
```
DB errors + slow queries + suspicious patterns
```

**Tools:**  
```
**SQLMap** (automated)
Havij, Burp Suite
```

---

## SQLi Attack Summary

| Type | Detection | Evasion | Tool |
|------|-----------|---------|------|
| **Error** | **Error messages** | Comments | SQLMap |
| **Union** | Multiple columns | Encoding | Burp |
| **Blind** | **No errors** | Time delays | Havij |
| **Stored Proc** | Dynamic SQL | Variables | Manual |

**Most Dangerous:** **Blind SQLi** (silent + persistent)

