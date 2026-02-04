---
layout: page
title: Lesson 7: Cellular Networks (Critical)
permalink: /lesson7/
---
Core of mobile telecom.

**Key Concepts:**
- Evolution: 2G (GSM), 3G (UMTS), 4G (LTE), 5G (NR)
- Architecture: RAN, Core Network, IMS, EPC, 5G Core (AMF, SMF, UPF)
- Concepts: Handover, Roaming, QoS, Network slicing, Massive MIMO, Beamforming

**Why It Matters:** Vital for careers in telecom operators.

**Labs/Practice:** Simulated LTE/5G handovers; deployed virtual 5G cores.

**Tools Used:** Open5GS, srsRAN, NS3.

# Lesson 7: Telephony & VoIP

This lesson covers the world of **voice services** — still one of the most revenue-critical parts of telecom networks in 2026.  
Even with messaging apps dominating daily use, operators continue to earn significant revenue from voice minutes (especially international roaming, enterprise PBX, contact centers, and emerging markets).  

VoIP (Voice over IP) has completely replaced traditional circuit-switched telephony in modern networks:  
- 4G → **VoLTE**  
- 5G → **VoNR**  
- Fixed networks → **IMS-based VoIP**

Understanding both legacy PSTN/SS7 and modern all-IP voice architectures is essential for telecom engineers, especially in core network, IMS, VoIP engineering, and telecom security roles.

## Why Telephony & VoIP Still Matter

- Major revenue stream for many mobile operators  
- VoLTE / VoNR is now mandatory on almost all smartphones  
- Enterprise UCaaS, SIP trunking, cloud PBX market is growing rapidly  
- SS7 and Diameter/HTTP/2 signaling remain major attack surfaces (telecom security specialization)  
- Voice is just another “application” running over 5G Core + IMS

## 1. Legacy Telephony – PSTN & SS7

**PSTN (Public Switched Telephone Network)**  
- Circuit-switched: dedicated 64 kbps channel (DS0) end-to-end for each call  
- TDM hierarchy: E1 (30 channels), T1 (24 channels), SDH/SONET for aggregation  
- Switches: Class 4 (transit), Class 5 (local)  
- Signaling: mostly out-of-band via SS7

**SS7 (Signaling System No. 7)**  
The global out-of-band signaling network used for:  
- Call setup / teardown  
- SMS delivery  
- Roaming (MAP)  
- Number portability  
- Supplementary services (call forwarding, barring, etc.)

**SS7 architecture components**  
- SSP (Service Switching Point) — telephone exchange  
- STP (Signal Transfer Point) — SS7 router  
- SCP (Service Control Point) — intelligent database (prepaid, freephone)

**Protocol stack**  
MTP → SCCP → TCAP → MAP / ISUP / CAMEL / INAP

**Critical issue in 2025–2026**  
SS7 was designed in the 1970s–80s with almost no authentication → still widely exploited for:  
- Location tracking  
- Call & SMS interception  
- Fraud (Wangiri, IRSF, premium-rate scams)

## 2. VoIP & Modern All-IP Voice

**Core idea**  
Analog voice → digitized → compressed (G.711, G.729, AMR-WB, Opus) → packetized → sent over IP/UDP

**Main protocols**

### SIP (Session Initiation Protocol) – RFC 3261
- HTTP-like text-based signaling protocol  
- Responsibilities: registration, session setup, modification, termination

**Typical SIP flow (simplified)**  
