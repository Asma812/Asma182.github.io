---
layout: page
title: Lesson 9: Satellite Communications
permalink: /lesson9/
---
Advanced optional topic.

**Key Concepts:**
- GEO / MEO / LEO
- Link budget
- VSAT
- Satellite internet (e.g., Starlink)

**Why It Matters:** Powerful for global connectivity.

**Labs/Practice:** Calculated link budgets; simulated satellite links.

**Tools Used:** MATLAB, NS3.

# Lesson 9: Tools You MUST Learn 🛠  
**The practical toolkit that turns telecom theory into employable skills**

This section covers the **essential tools** every serious telecommunications engineer should master in 2025–2026. Knowing theory is good — being able to **simulate**, **capture**, **deploy**, and **troubleshoot** real systems is what gets you interviews and jobs.

## Why These Tools Matter
- Most telecom technical interviews include practical / tool-based questions  
- Open-source 4G/5G stacks let you build real private networks at home → huge CV differentiator  
- Tools bridge Lessons 1–8 into visible, demonstrable projects (see Lesson 12)  
- Daily usage in operator, vendor, R&D, and integration roles

## Tool Priority & Recommendation Path

| Priority | Tool              | Core Usage Area                          | Difficulty | Resume Impact | First Project Suggestion                           |
|----------|-------------------|------------------------------------------|------------|---------------|-----------------------------------------------------|
| ★★★★★    | **Wireshark**     | Protocol analysis (SIP, RTP, GTP, Diameter) | Easy–Medium | Extremely high | Capture & dissect a VoLTE call flow                |
| ★★★★★    | **Linux**         | Base operating system & scripting        | Medium     | Extremely high | Comfortable CLI + basic Bash automation            |
| ★★★★☆    | **MATLAB** / Octave | Signal processing, modulation, BER sims | Medium–High | Very high     | QPSK/16-QAM BER vs SNR waterfall plot              |
| ★★★★☆    | **srsRAN** + **Open5GS** | Real 4G/5G RAN + Core deployment     | Hard       | Extremely high | Private 5G network with commercial phone registration |
| ★★★☆☆    | **GNS3**          | Network emulation (routing, MPLS, QoS)   | Medium     | High          | OSPF + VLAN backhaul network                       |
| ★★★☆☆    | **GNU Radio**     | Software-Defined Radio prototyping       | Medium–Hard | Medium–High   | Simple FM receiver or GSM signal capture           |
| ★★★☆☆    | **ns-3**          | Large-scale network & mobility simulation| Medium–Hard | Medium–High   | LTE handover or 5G interference scenario           |
| ★★☆☆☆    | **Bash / Python** | Automation, log parsing, quick scripts   | Easy–Medium | High          | Parse srsRAN logs or automate lab startup          |

## 1. Protocol & Traffic Analysis

**Wireshark** – The #1 daily tool for any telecom engineer

```text
Common filters I use every week:
- sip or diameter           → VoLTE/IMS signaling
- rtp                       → voice/video media flow
- gtp                           → 4G/5G tunneling (GTP-U / GTP-C)
- http2                     → 5G core SBA (HTTP/2 based)
- wlan.fc.type_subtype == 0x08   → Wi-Fi beacons
