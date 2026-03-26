# My 15-Day CEH v13 Study Plan

## Study Roadmap - How I'm Attacking CEH v13

I'm giving myself **15 focused days** to prepare for CEH v13, strictly using the official blueprint and domains as my map. CEH v13 still keeps the classic ethical hacking flow (recon -> scanning -> gaining access -> maintaining access -> covering tracks) but adds more weight on AI-driven threats, cloud, AD, ransomware, and IoT/OT.

### What the exam looks like (so I don't forget)

- 125 MCQs in 4 hours - so I can't afford to overthink every question.
- Passing score floats (roughly around 60-85% depending on the form).
- v13 brings in AI-related ethical hacking topics, modern ransomware, deepfakes, AD attacks, cloud and IoT/OT focus.

### My 15-Day Breakdown (High Level)

I'm touching every blueprint area, but I'm spending extra energy on recon, scanning/enumeration, system hacking, network/web attacks, and the new AI/cloud/AD pieces.

- Week 1 (Days 1-5): Build the foundation - understand the blueprint, master recon/scanning/enumeration, learn system hacking phases, and map vulnerabilities to attack paths.
- Week 2 (Days 6-10): Attack surfaces and defenses - cover network attacks, web exploitation, wireless/mobile/IoT/cloud security, and cryptography fundamentals.
- Week 3 (Days 11-15): Modern threats, consolidation, and exam readiness - tackle social engineering, AI-driven threats, full blueprint review, mock exams, and final prep.

**Day 1 - Foundations & Exam Orientation**
I align myself with the blueprint on Day 1: I read the CEH v13 brochure/blueprint, note the domains, and understand what weight each area has. I then revise core infosec basics (CIA triad, controls, threat actors, legal/ethical hacking) so the fundamentals are fresh. I also set up my OneNote structure (sections for domains, tools, labs, AI, and weak areas).

**Day 2 - Footprinting & Recon (including AI recon)**
On this day I go deep into recon: passive and active footprinting, OSINT, WHOIS, DNS, Google dorks, email harvesting, and social media footprinting. I also plug in how AI can help automate recon and OSINT. I practice basic recon on legal platforms and document everything in OneNote.

**Day 3 - Scanning & Enumeration**
I focus on Nmap and scanning concepts: TCP/UDP basics, port states, service and version detection, OS detection, and enumeration of users/shares/services. The goal is to map: "after recon, which exact scan would I run and why?" I write down my go-to Nmap commands and what they reveal.

**Day 4 - Vulnerability Analysis**
Here I learn to think like a vulnerability assessor: how to interpret Nessus/Qualys/OpenVAS-style outputs and connect vulnerabilities to attack paths. I'm not trying to become a full VA engineer in one day, just enough to understand how CEH expects me to reason about vulns and risk.

**Day 5 - System Hacking & Malware Basics**
On Day 5 I drill the classic phases of system hacking: gaining access, privilege escalation, maintaining access, and clearing tracks. I revise password attacks, credential dumping, malware types (Trojans, rootkits, keyloggers, etc.) and note common persistence techniques for Windows and Linux.

**Day 6 - Sniffing, DoS, and Session Hijacking**
This day is for network and perimeter attacks. I cover sniffing, ARP poisoning, MITM, DoS/DDoS theory, and session hijacking. I also note countermeasures like anti-sniffing techniques, secure protocols, and IDS/IPS/firewall evasion basics.

**Day 7 - Web Servers & Web Apps**
I focus on web server misconfigurations and the web app basics: HTTP, cookies, sessions, and authentication/authorization. Then I revise common web attacks like XSS, SQLi, CSRF, file inclusion, parameter tampering, and broken access control.

**Day 8 - SQL Injection & Advanced Web Hacking**
I break down SQL injection types (in-band, inferential, out-of-band) and practice thinking through payload logic rather than memorizing strings. I also get comfortable with Burp Suite basics (proxy, repeater, intruder concepts) and write a small "web attack flow" in my notes.

**Day 9 - Wireless, Mobile, IoT/OT, and Cloud**
This is a multi-topic day: wireless encryption and common attacks (Evil Twin, deauth, WPS issues), mobile risks, IoT/OT/SCADA security, and cloud basics with common misconfig attacks. I don't try to master each platform exhaustively; I focus on how CEH typically frames questions around these domains.

**Day 10 - Cryptography & PKI**
I revise symmetric vs asymmetric crypto, hashing, digital signatures, PKI, and TLS. I also note crypto-related attacks (weak ciphers, downgrade attacks, poor key management, brute force) and how they might show up in the exam.

**Day 11 - Social Engineering, Physical Security, Reporting**
This day is about the "human and process" side: social engineering techniques, physical security concepts, and how a professional report is structured. I make a simple template in my notes for a pentest report (exec summary, methodology, findings, risk, remediation).

**Day 12 - AI-Driven Ethical Hacking & Modern Threats**
Because v13 explicitly mentions AI, I explore both sides: AI for attackers (automated recon, malware, phishing) and AI for defenders (anomaly detection, log analysis). I also revise modern topics like ransomware, AD attacks, deepfake threats, and critical infrastructure/IoT risks.

**Day 13 - Full Blueprint Review + Tools Sheet**
I do a fast pass through all domains, then build a master tools sheet in OneNote: each tool, its category, purpose, key flags, and where it fits in the hacking lifecycle. I also do a short timed question set (30-40 questions) and mark weak areas.

**Day 14 - Full Practice Exam & Error Log**
I attempt a full-length mock exam under timed conditions using legitimate practice questions, not dumps. Then I go question by question on my mistakes and categorize them as concept gaps, tool gaps, misreads, or time pressure issues.

**Day 15 - Light Revision & Exam-Day Prep**
I don't learn anything new on Day 15. I only revise my notes, tools list, and error log, and mentally rehearse my exam strategy. I also check logistics (ID, time, location, sleep, food) so I'm not stressed by non-technical issues.

---

## The Study Approach Breakdown - How I'm Actually Studying

If someone asks me "How exactly are you studying each day?", this is what I'd say.

Every day, I follow a simple pattern that keeps theory, tools, and questions connected.

- First 1-1.5 hours: I go through theory from CEH v13 materials, good YT/tuts, or my training content for that day's domain.
- Next 1-2 hours: I try to touch tools or labs related to that domain (even small labs are fine) - Nmap, Burp, Wireshark, Metasploit, or cloud/AD tools depending on the topic.
- Final 30-45 minutes: I solve questions from legit practice sources and immediately review why each wrong answer is wrong.

### How I use OneNote

OneNote is basically my CEH brain now. For each blueprint domain I have:

- A short definition in my own words.
- The key steps/phases (e.g., recon steps, system hacking phases).
- Typical exam question patterns I've seen.
- A mini playbook for that domain (for example: "Web app hacking: recon -> mapping -> fuzzing -> exploit -> post-exploit").

I also maintain a separate "Tools" section. For every tool I encounter, I note its purpose, basic syntax/flags, sample command, and which phase it belongs to. That way, when the exam question says "You are in the enumeration phase with a Windows server exposed on port 445," my brain already knows which tools are realistic.

### Mapping content to the CEH v13 blueprint

Whenever I study something, I ask: "Which blueprint domain is this and how would EC-Council test it?" That keeps me from randomly consuming content. I highlight high-weight domains like system hacking, network/perimeter attacks, web applications, and recon/scanning because they're likely to contribute a big chunk of the questions.

---

## The Unspoken Truth: My Certification Journey

If I'm being honest, I didn't respect CEH enough the first time.

Before February 2025, I was "preparing" for about three months, but in reality I was mixing CSA-style SOC content with CEH, trusting my general security knowledge and hands-on experience to carry me. My master's workload was heavy, I was stretched between assignments and labs, and I still walked into the CEH exam overconfident, assuming I'd clear it because "I'm already in security."

In February 2025, the exam proved me wrong. I failed. I knew the buzzwords, but many questions blended tools, phases, and scenarios in ways I wasn't ready for. I realized I didn't have a clear mapping between "tool -> phase -> objective" in my head; I was thinking like a general security person, not a blueprint-driven ethical hacker.

After November 2025, I decided I wasn't ending my CEH story there. With v13 now live and AI-driven content added, I went back to proper training, similar to what I took in December 2024 but updated for CEH v13: same ethical hacking flow, but with AI-assisted recon, AD attacks, ransomware, cloud and IoT/OT emphasis, and a more modern threat landscape.

This time, I treated it like a project. I watched selected YouTube breakdowns, followed official EC-Council material, and went through AATP-style content - but I didn't just watch and move on. I documented everything in OneNote: every tool, every phase, every attack chain. If I learned a new command, it went into OneNote. If I saw a new attack path, I wrote down "how it works" and "where it fits in the kill chain."

The big difference now is that I'm not just "studying for a cert." I'm building my own CEH v13 playbook based on my failure, my labs, and my notes. When I sit for CEH again, I'm not going in as someone hoping their general knowledge is enough; I'm going in as someone who has mapped the exam blueprint to real tools, real phases, and real thinking.

---

## Exam Tips & Strategy - How I'll Tackle CEH v13 Questions

Here's exactly how I plan to approach questions in the exam hall.

### 1. Bottom-to-Top Reading

I first read the **last line** of the question to see what it wants: tool, phase, next step, mitigation, or concept. Then I quickly scan the answer options once. Only after that do I read the full scenario from the top. This keeps me from getting lost in a long story and helps me read the scenario with a clear target in mind.

### 2. Eliminate Hard, Then Compare

I don't hunt for the "perfect" answer right away. I first eliminate anything that's clearly wrong: wrong phase, wrong tool category, defensive action when they clearly asked for an offensive step, etc. Once I'm down to two options, I compare them against the phase and objective in the question and ask, "Which one fits the situation better?"

### 3. Follow the Keywords

I pay attention to keywords that scream domain/phase, for example:

- "WHOIS, DNS, Google dorks, social media" -> footprinting/recon.
- "Nmap, open port 445, banner grabbing" -> scanning/enumeration.
- "SQL errors, input fields, login bypass" -> SQLi/web exploitation.
- "Deauth frames, WPA handshake" -> wireless attacks.
- "Keylogging, privilege escalation, persistence" -> system hacking.
- "S3 bucket, security group, IAM" -> cloud security.

I ignore fluff like company names, dates, or non-technical story details that don't change the attack logic.

### 4. Think Like an Ethical Hacker

For every question, I ask: "If I were on an actual engagement, at this phase, what would I do next?" That automatically filters out unrealistic answers. I map the scenario to the five hacking phases (recon, scanning, gaining access, maintaining access, covering tracks) and choose the option that matches both the phase and the goal.

If the question mentions AI, I think in terms of automation and scale (AI-assisted recon, anomaly detection, pattern analysis, AI-supported malware) instead of treating AI as some magic black box.

### 5. Time Management - Flag and Move

With 125 questions in 4 hours, I aim to finish most questions in under a minute. If I'm stuck after 40-45 seconds, I make my best elimination-based choice, flag it, and move on. Later questions often refresh concepts, and I can come back with a clearer head.

### 6. Respect the High-Weight Areas

I know CEH v13 leans heavily on system hacking, network/perimeter attacks, web security, recon/scanning, and newer areas like cloud, AD, ransomware, and IoT/OT. During the exam, when questions from these domains appear, I slow down just enough to apply my full strategy instead of rushing and making silly mistakes.

---

## Thank You

Thank you for reading my CEH v13 study plan. This is my commitment to myself - to learn, to grow, and to become the ethical hacker I know I can be. Every page of notes, every lab, every failed attempt has been a step forward. See you on the other side of the exam.
