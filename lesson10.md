---
layout: page
title: Lesson 10: Telecom Security
permalink: /lesson10/
---
Blending security with telecom.

**Key Concepts:**
- SS7 vulnerabilities
- LTE/5G security
- IMS security
- SIM authentication
- Network monitoring
- IDS/IPS for telecom
- Lawful interception

**Why It Matters:** Your cybersecurity background makes you unique—telecom + security is in-demand.

**Labs/Practice:** Simulated SS7 attacks; hardened telecom networks.

**Tools Used:** Wireshark, OpenSSL, Ansible.
# Lesson 10: Telecom Security – Your BIG PLUS 🔐

**The rare & high-demand combination: Deep telecom knowledge + Security expertise**

This is one of the **highest-value niches** in telecommunications in 2026. Operators, vendors, governments, consultancies, and cybersecurity firms are actively searching for people who truly understand both **signaling protocols** and **modern attack surfaces**.

## Why Telecom Security Stands Out on a Resume

- Critical infrastructure → regulated & high-stakes target
- Legacy protocols (SS7, Diameter) still in wide use → notoriously insecure
- 5G introduces **new attack vectors** while improving some old ones
- Very few engineers combine deep telecom domain knowledge with offensive/defensive security skills
- High-paying roles: Telecom Security Engineer, Threat Intelligence Analyst, Red Teamer for telcos, Security Architect

## 1. Legacy Attack Surface – SS7 & Diameter (Still Very Relevant)

SS7 remains heavily used for international roaming, SMS delivery, number portability, and supplementary services.

### Major SS7 Attack Classes (most still possible in 2026 if no protection)

| Attack Type               | Technique/Example                              | Impact                              | Mitigation (GSMA FS.07/FS.11)          |
|---------------------------|------------------------------------------------|-------------------------------------|------------------------------------------|
| Location Tracking         | ProvideSubscriberInfo, AnyTimeInterrogation    | Real-time cell-ID / GPS             | Block ATI/PSI from foreign networks      |
| SMS Interception          | SendRoutingInfoForSM + forwardSMS              | Bank OTPs, 2FA codes                | Home Routing for SMS                     |
| Call Interception         | InsertSubscriberData + UpdateLocation          | Man-in-the-middle voice calls       | Whitelist allowed MAP operations         |
| Subscriber Impersonation  | Fake InsertSubscriberData with IMSI            | Identity hijacking, fraud           | Strong authentication checks             |
| Denial of Service         | Flood with SRI-SM / ATI queries                | HLR/HSS overload                    | Rate limiting + anomaly detection        |

**Access in 2026**: grey interconnects, compromised partners, dark-web purchased access (prices have dropped but still exist).

![SS7 network architecture overview](https://via.placeholder.com/800x400/1e3a8a/ffffff?text=SS7+Architecture+Diagram)  
*Typical SS7 signaling network – SSP ↔ STP ↔ SCP*

## 2. 4G / 5G Security – Improvements & New Risks

### 4G (LTE / EPC) – Better than 2G/3G but still vulnerable

- Mutual authentication (EPS-AKA)
- Remaining issues:
  - IMSI catchers (rogue eNodeBs / Stingrays)
  - Unauthenticated NAS signaling → DoS
  - GTPv2-C spoofing

### 5G – Much Stronger Security Foundation

| Feature                        | Benefit                                                                 | Still Possible Attack Vector                     |
|--------------------------------|-------------------------------------------------------------------------|--------------------------------------------------|
| SUCI / SUPI encryption         | Prevents plain IMSI over the air                                        | Rogue gNB before authentication                  |
| 5G-AKA (stronger than EPS-AKA) | Better key derivation & protection against bidding-down attacks        | Misconfigured home network                       |
| HTTP/2 + TLS 1.3 mandatory     | SBI (Service Based Interface) encryption & integrity                    | API abuse if NEF poorly secured                  |
| SEPP (Security Edge Protection Proxy) | Encrypted & integrity-protected interconnect traffic               | Insider threats at interconnect                  |
| Network Slicing security       | Slice isolation, dedicated authentication & authorization              | Cross-slice leakage if misconfigured             |

![5G security architecture overview](https://via.placeholder.com/800x450/065f46/ffffff?text=5G+Security+Architecture+with+SEPP+and+SBA)  
*5G Service-Based Architecture with mandatory security elements*

## 3. Defensive Techniques You Should Know

- SS7 / Diameter firewalls (GSMA FS.07, FS.11, FS.19)
- Home Routing for SMS in roaming
- TLS 1.3 everywhere + strong cipher suites
- Signaling anomaly detection (ML-based)
- Zero-trust in 5GC: least privilege per NF
- Continuous monitoring & SIEM for signaling spikes
- Lawful Interception must be secured (encrypted delivery + audit logs)
