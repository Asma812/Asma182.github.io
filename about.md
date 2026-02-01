---
layout: page
title: About Me
permalink: /about/
---

## Bio
Asma Neji, Junior Cybersecurity Engineer with expertise in telecommunications, networks, and AI. Experienced in building secure systems, threat intelligence, and AI-driven anomaly detection. Based in Tunisia.

LinkedIn: [linkedin.com/in/asma-neji](https://linkedin.com/in/asma-neji)  
GitHub: [github.com/Asma812](https://github.com/Asma812)  
Email: asmaneji20@gmail.com  
Phone: +216 97 322 007

[View CV]({{ site.baseurl }}/assets/cv/AsmaNEJI_CV.pdf) | [Download CV]({{ site.baseurl }}/assets/cv/AsmaNEJI_CV.pdf) (right-click > save as)

## Skills

| Category          | Key Skills                                                                 |
|-------------------|----------------------------------------------------------------------------|
| Networking       | Cisco Packet Tracer, Huawei eNSP, TCPDump, OpenVPN, NS3, Omnet++, Wireshark, OpenSSL |
| Systems          | Linux (Ubuntu, Kali), Windows Server                                              |
| Languages        | Python, Bash/Shell, SQL, C, C++, Java                                             |
| DevOps           | Ansible, Shell Scripting, Docker, SonarQube, Jenkins                              |

### Security Skills
- Threat intelligence
- Pentesting: Nmap, Burp Suite, OWASP ZAP, Metasploit, Nessus/OpenVAS
- Network security
- Infrastructure hardening
- Security automation
- Incident response
- Bug Bounty: Burp Suite, OWASP ZAP, Amass, Gobuster, Postman for APIs

## Education
- **2022-2025**: Higher Institute of Computer Science, Tunisia  
  Engineering in Computer Science, Engineering and Development of Communications Infrastructures and Services  
- **2019-2022**: Higher Institute of Information and Communication Technologies, Tunisia  
  Bachelor in Information and Communication Technologies, Telecommunications  

## Professional Experience

### Cyber Threat Intelligence Intern  
**TUDIGISEC by Nomios** — February 2025 – June 2025 (End-of-Studies Internship)

I took ownership of designing a full Cyber Threat Intelligence (CTI) system from the ground up, treating the organization’s scattered threat data sources as a disconnected puzzle that needed unification.

**Core Thinking & Architecture**  
I chose Neo4j as the central knowledge graph engine because traditional relational databases struggle with the highly relational nature of threat actors, campaigns, indicators, and infrastructure. The graph model allowed me to naturally represent attacker TTPs, victim assets, and enrichment sources as interconnected nodes and relationships.

The architecture followed a modular ingestion → processing → analysis → visualization pipeline:
- Multi-source ingestion: Social media streams, OSINT feeds, internal honeypots, and curated dark web datasets.
- Entity extraction layer: Custom regex + NLP pipelines (transformers for named entity recognition) to turn unstructured text into structured triples.
- Semantic enrichment: Mapped everything to MITRE ATT&CK framework using graph patterns to link tactics, techniques, and procedures across sources.
- Anomaly & trend detection: Combined graph algorithms (PageRank for influential actors, community detection for campaign clustering) with lightweight ML models for outlier scoring.
- Output layer: Real-time dashboard (Dash) for interactive exploration + Flask API for programmatic access and STIX 2.1 export.

**PoC Highlights**  
- Built a prototype that ingested sample dark-web paste data, extracted IOCs, linked them to known campaigns via ATT&CK, and visualized emerging clusters in under a week.
- Dockerized the entire stack (Neo4j + Python workers + Dash/Flask) for reproducible deployment and scalability testing.

This wasn't just data collection—it was turning noisy intelligence into actionable, graph-queryable knowledge that could support proactive defense decisions.

### DevSecOps Intern  
**ARRIBATT FZCO** — July 2024 – August 2024 (End-of-Year Internship)

I focused on bridging development speed with security without creating bottlenecks, designing a "shift-left" pipeline that caught issues early while maintaining developer velocity.

**Core Thinking & Architecture**  
Recognized that security checks needed to be automated, non-intrusive, and integrated into existing workflows. Built a Jenkins-based CI/CD pipeline with parallel security gates.

Key architectural choices:
- Static & dynamic analysis early: SonarQube for code quality + OWASP ZAP for DAST during build/test stages.
- Dependency & container scanning: Integrated OWASP Dependency-Check and container tools to prevent vulnerable components from reaching production.
- Runtime monitoring & response: Deployed and tuned Wazuh agents across environments for host log collection, file integrity monitoring, and active response.
- Incident orchestration: Connected Wazuh alerts to TheHive (case management), Cortex (analyzers/enrichment), and OpenCTI (threat intel sharing) to form a lightweight XDR-like loop.
- Automation glue: Used n8n for low-code workflows that triggered alerts, enriched data, and notified teams.

**PoC Highlights**  
- Created a demo pipeline that took a sample vulnerable app → ran SonarQube → blocked on critical issues → scanned dependencies → performed automated ZAP scans → forwarded findings to TheHive/OpenCTI.
- Configured Wazuh rules to detect common attack patterns and auto-quarantine suspicious processes.

The result was a pipeline that didn't just "add security"—it embedded it as a natural part of delivery, reducing mean-time-to-remediate through automation.

### Cyber Threat Intelligence Intern  
**SAMA PARTNERS BUSINESS SOLUTIONS SARL** — August 2023 (Summer Internship)

This short but intense internship gave me my first deep dive into the dark web as an intelligence source, shifting my mindset from reactive monitoring to proactive hunting.

**Core Thinking & Architecture**  
I approached the dark web not as a chaotic space but as a structured ecosystem with discoverable patterns (markets, forums, leak sites, paste services). The goal was to evaluate tools for scalable, ethical collection and classification.

Focused on the AIL (Analysis Information Leak) framework:
- Explored its modular crawler architecture for ingesting pastes, hidden services, and protected forums.
- Tested extraction logic for IOCs (credentials, hashes, domains) and classification (leak type, sensitivity).
- Analyzed how AIL handles unstructured streams → correlates items → flags high-value intelligence.

**PoC Highlights**  
- Ran controlled tests on sample paste sites and Tor onions → evaluated recall/precision for credential leaks and vulnerability mentions.
- Mapped dark web communication flows (onion routing, protocol behaviors) to understand evasion techniques.

This experience taught me how to think adversarially: understand attacker infrastructure to better defend against it.

### Cyber Security Intern  
**RIADVICE** — January 2022 – May 2022 (End-of-Studies Internship)

My first hands-on hardening project—focused on turning a standard server environment into a defensible one using open-source tools and automation.

**Core Thinking & Architecture**  
Adopted a layered defense model (CIS benchmarks as baseline) with emphasis on visibility, prevention, and response.

Key decisions:
- Central visibility: Deployed Wazuh as the SIEM core for log aggregation, FIM, rootkit detection, and active response.
- Web & host protection: Integrated ModSecurity (WAF rules), ClamAV (malware scanning), AIDE (file integrity), Tiger (security auditing), and Fail2Ban (brute-force blocking).
- Automation-first: Wrote Ansible playbooks to enforce configurations, deploy agents, and apply hardening policies consistently across servers.
- Alerting loop: Configured webhook-based alerts from Wazuh to external channels for rapid incident handling.

**PoC Highlights**  
- Built a hardened prototype server: Applied CIS Level 1 benchmarks → layered tools → simulated attacks (brute-force, web exploits) → verified blocks/alerts.
- Developed Ansible roles that idempotently managed authentication hardening (key-only SSH, password policies).

This internship solidified my belief in infrastructure-as-code for security: repeatable, auditable, and scalable hardening.

## Certifications
- [API Security Fundamentals (2025)](https://www.apisecuniversity.com/courses/api-security-fundamentals)<grok-card data-id="fe6c97" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  
- [Microsoft Certified: Azure Fundamentals (2024)](https://learn.microsoft.com/en-us/credentials/certifications/azure-fundamentals)<grok-card data-id="7a41b0" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  
- [Microsoft Certified: Security, Compliance, and Identity Fundamentals (2024)](https://learn.microsoft.com/en-us/credentials/certifications/security-compliance-and-identity-fundamentals)<grok-card data-id="9d4bf0" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  
- [Microsoft Certified: Azure Data Fundamentals (2024)](https://learn.microsoft.com/en-us/credentials/certifications/azure-data-fundamentals)<grok-card data-id="27135c" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  
- [Cisco CCNA (2024)](https://cp.certmetrics.com/cisco/en/public/verify/credential)<grok-card data-id="1c02b8" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  
- [Secure your network with VPNs and Firewalls - OpenClassrooms (2024)](https://openclassrooms.com/en/courses/7075956-secure-your-network-with-vpns-and-firewalls)<grok-card data-id="589757" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  
- [Secure your infrastructure - OpenClassrooms (2024)](https://openclassrooms.com/en/courses/8395341-secure-your-active-directory-and-windows-domains)<grok-card data-id="29cc36" data-type="citation_card" data-plain-type="render_inline_citation" ></grok-card>  

## Academic Projects
- [Intelligent Inventory Management System](https://github.com/Asma812/inventory-system): 

<grok-card data-id="acffe8" data-type="image_card" data-plain-type="render_searched_image"  data-arg-size="LARGE" ></grok-card>

 Python, C/C++, STM32, Nodemcu, ThingSpeak.  
- [Expert System for Disease Diagnosis](https://github.com/Asma812/disease-diagnosis): 

<grok-card data-id="d0bb11" data-type="image_card" data-plain-type="render_searched_image"  data-arg-size="LARGE" ></grok-card>

 Python, Tkinter.  
- [Drowsiness Detector with Image Processing and AI](https://github.com/Asma812/drowsiness-detector): 

<grok-card data-id="f4387d" data-type="image_card" data-plain-type="render_searched_image"  data-arg-size="LARGE" ></grok-card>

 Python, Raspberry Pi, API.  
- [Optimizing Virtualized 5G Network with SDN, NFV, AI, and Blockchain](https://github.com/Asma812/5g-optimization): 

<grok-card data-id="95e900" data-type="image_card" data-plain-type="render_searched_image"  data-arg-size="LARGE" ></grok-card>

 OpenDaylight, Open5GS, TensorFlow, Docker, Hyperledger Fabric, Prometheus, Grafana.  
- [Mobile App for Financial Management](https://github.com/Asma812/financial-app): 

<grok-card data-id="817bfb" data-type="image_card" data-plain-type="render_searched_image"  data-arg-size="LARGE" ></grok-card>

 Java.  
- [Web App for Library Management](https://github.com/Asma812/library-app): 

<grok-card data-id="5386a6" data-type="image_card" data-plain-type="render_searched_image"  data-arg-size="LARGE" ></grok-card>

 Java, MySQL.  

## Security Reports & Writeups
(Placeholder for future additions—add links to reports as you complete them)  
- Bug Bounty Report Example: [Link to report/writeup]  
- Pentest Report Example: [Link to report/writeup]  
- Hardening Project: [Link to writeup]

## Languages
- English, French, Arabic
