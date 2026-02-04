---
layout: page
title: Lesson 7: Telephony & VoIP
permalink: /lesson7/
---
Voice communication systems.

**Key Concepts:**
- PSTN, SS7
- SIP, RTP
- VoIP architecture, Softswitches

**Why It Matters:** Still foundational for voice services in modern networks.

**Labs/Practice:** Set up VoIP calls; analyzed SIP packets.

**Tools Used:** Wireshark, OpenVPN.

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
UE ── REGISTER ──→ P-CSCF ──→ S-CSCF ──→ HSS/UDM
UE ◄─ 200 OK (with service route) ────┘
UE ── INVITE ──→ P-CSCF ──→ I-CSCF ──→ S-CSCF ──→ ... terminating side


Common methods: REGISTER, INVITE, ACK, BYE, CANCEL, OPTIONS, MESSAGE (SMS over IP)

### RTP (Real-time Transport Protocol) – RFC 3550
- Carries the actual media (voice / video)  
- Runs over UDP (low latency, no retransmission)  
- Fields: sequence number, timestamp, SSRC, payload type  
- Companion: **RTCP** (provides QoS feedback: jitter, packet loss, delay)

### SRTP (Secure RTP)
- Mandatory in VoLTE / VoNR  
- Adds encryption + authentication to RTP packets

## 3. IMS (IP Multimedia Subsystem) Architecture

Standardized framework (3GPP) for delivering multimedia services over all-IP networks.  
Used for VoLTE, VoNR, RCS, fixed VoIP.

**Key IMS network functions**

- **P-CSCF** (Proxy-CSCF): first contact point, SIP compression, QoS policing  
- **I-CSCF** (Interrogating-CSCF): routes based on HSS/UDM lookup  
- **S-CSCF** (Serving-CSCF): main session control, service logic, charging  
- **HSS / UDM**: subscriber database & authentication  
- **TAS** (Telephony Application Server): call forwarding, conferencing, ringback tones  
- **MGCF / IM-MGW**: PSTN gateway (SIP ↔ ISUP translation)

**Simplified VoLTE call flow (high-level)**  
1. UE registers → IMS (AKA authentication)  
2. INVITE sent → routed through P/I/S-CSCF  
3. SDP negotiation (codecs, ports)  
4. 183 Session Progress / 180 Ringing  
5. 200 OK (answer) → ACK  
6. Bidirectional RTP/SRTP media  
7. BYE to end session

## 4. Modern Trends (2025–2026)

- **Cloud-native IMS**: Kubernetes-based, microservices (Nokia, Mavenir, Ericsson, Huawei)  
- **WebRTC**: browser-native voice/video (used in many UC platforms)  
- **RCS (Rich Communication Services)**: advanced messaging + voice/video over IMS  
- **5G VoNR**: native voice over 5G NR (lower latency than VoLTE)

## Practice & Portfolio Suggestions

- Set up **Asterisk** or **FreeSWITCH** PBX → make calls between softphones (Linphone / MicroSIP)  
- Capture & analyze real traffic with **Wireshark** (filter: `sip` or `rtp`)  
- Document: REGISTER flow, INVITE with SDP, jitter/buffer behavior  
- Bonus (advanced): integrate with Open5GS + srsRAN for private VoLTE lab

## Summary – Key Takeaways for Interviews

- PSTN = circuit-switched → VoIP = packet-switched (delay vs reliability trade-off)  
- SIP = signaling, RTP = media, SRTP = security  
- IMS = standardized VoIP/IMS architecture in mobile networks  
- SS7 vulnerabilities remain relevant (telecom security angle)

This knowledge directly connects to:  
- Telecom security (SS7/Diameter attacks)  
- Core network engineering  
- VoIP / IMS engineering roles  
- Practical projects (Wireshark analysis, private VoIP lab)
