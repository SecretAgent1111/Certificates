# CSA - Study Roadmap
## Executive Summary

Over 12 days, I followed a focused study roadmap for my SOC Analyst v2 certification exam, using the official exam blueprint as my guide.

---

## The 12-Day Study Plan

### **Days 1-2: SOC Fundamentals & Operations**
- Security operations center (SOC) roles and responsibilities
- Daily SOC workflows and incident handling processes
- Key Performance Indicators (KPIs) and metrics
- Different SOC models and architecture
- Understanding the SOC analyst's role in the organization

### **Days 3-4: Threats, TTPs & Indicators of Compromise (IoCs)**
- Real-world threat landscapes and attack methodologies
- Tactics, Techniques, and Procedures (TTPs) across attack vectors:
  - Network-based attacks and lateral movement
  - Host/endpoint compromise indicators
  - Application-layer exploits
  - Email-based threats and phishing
  - Social engineering and credential theft
- Identifying and analyzing IoCs left behind by attacks

### **Days 5-6: Log Analysis & Centralized Logging**
- Operating System logs (Windows, Linux, macOS)
- Network device logs (firewalls, routers, proxies)
- Application logs (web servers, databases)
- Email server logs and messaging security
- Centralized logging architecture
- Log normalization and parsing for SIEM

### **Days 7-8: SIEM Concepts & Use Cases**
- SIEM architecture and components
- Data ingestion, correlation, and enrichment
- Use case development and alert logic
- - Practised 20+ SIEM use cases on Splunk (available in Home Labs section)
- Dashboards and visualization for quick insights
- Alert triage and prioritization

### **Days 9-10: Threat Intelligence & Threat Hunting**
- Types of threat intelligence (tactical, operational, strategic)
- Threat intel sources and platforms
- Integrating threat intelligence into detection strategies
- Threat hunting methodologies and frameworks
- Hunt tools and techniques (PowerShell, Yara, OSINT)
- Connecting hunts to incident response workflows

### **Day 11: Incident Response & Forensics**
- Incident response lifecycle:
  - Detection and analysis
  - Containment strategies
  - Eradication and recovery
  - Post-incident review and lessons learned
- Handling specific incident types:
  - Network intrusions
  - Malware infections
  - Insider threats
  - Application compromises
  - Email security incidents
- Incident response playbooks and automation
- EDR/XDR tools in modern incident response
- Digital forensics and malware analysis basics
- SOC operations in cloud environments:
  - Microsoft Azure and Azure Sentinel
  - AWS Security Hub and GuardDuty
  - Google Cloud Platform (GCP) security services

### **Day 12: Consolidation & Scenario-Based Practice**
- Domain-specific revision notes
- Scenario walk-throughs (practical decision-making)
- Real-world incident response simulations
- Thinking like an analyst, not memorizing theory
- Final exam readiness check

---

## The Study Approach Breakdown

I started with the basics of security operations and how a SOC actually runs day to day - roles, workflows, KPIs, and different SOC models - so I had a clear picture of where a SOC analyst fits in.

Then I moved into real-world threats and TTPs, looking at how attacks play out on the network, hosts, apps, email, and through social engineering, and what kind of IoCs they leave behind.

Once that foundation was set, I spent a couple of days just on logs: Windows/Linux/macOS, firewalls and routers, plus web, database, and email server logs, and how they all tie into centralized logging and a SIEM.

After that, I went deeper into SIEM concepts - architecture, use cases, correlation rules, dashboards, and alert triage - and built a few sample use-case ideas (brute force, data exfil, privilege abuse, etc.) that a SOC would realistically monitor for.

The next block was threat intelligence and threat hunting: I reviewed different types of threat intel, common sources and platforms, and how TI can actually drive better detections and incident response. I also walked through hunting ideas using things like PowerShell and Yara-style approaches, and tied all of that back into the incident response lifecycle: from initial detection to containment, eradication, recovery, and lessons learned.

Towards the end, I focused on how incidents are handled in practice (network, application, email, insider, malware), how playbooks structure the response, and where EDR/XDR tools fit in. I wrapped up by revising forensics and basic malware analysis concepts, plus how SOC work changes in cloud environments (Azure with Sentinel, AWS Security Hub, and GCP's security tooling).

On the final day, I condensed everything into short notes per domain and did a few scenario walk-throughs - "If I got this alert in a SOC, what would I actually do step by step?" - to make sure I wasn't just memorizing theory but thinking like an analyst.

---

## The Unspoken Truth: My Certification Journey

### **First Attempt (January - March 2025)**

From January to March 2025, I followed the same study structure, but I **didn't clear the exam on my first attempt**.

Before that, I had already gone through intensive focused training that included a lot of hands-on work with Splunk and other SOC tooling, which gave me a solid baseline but clearly **not enough exam-specific focus**.

### **The Gap & Recovery (Late 2025 - February 2026)**

In late 2025, my priority shifted heavily to my UK master's program, and certification preparation slipped into the background. Even then, between December and January I went back for another round of training to:
- Rebuild my confidence
- Sharpen my SIEM skills
- Close the gaps I'd identified from my first attempt

### **The Second Attempt (February 2026)**


Used this **structured 12-day blueprint-aligned roadmap** to pull everything together, and went into the exam with:- Understanding of SOC 
operations and workflows
- Practical knowledge of SIEM architectures and use cases
- Real-world incident response thinking
- Hands-on cloud SOC concepts (Azure, AWS, GCP)
- Confidence to think like an analyst, not just repeat theory

**Key Takeaway:** *The second attempt wasn't about studying harder - it was about studying smarter, with exam-specific focus and practical, scenario-based thinking.*
