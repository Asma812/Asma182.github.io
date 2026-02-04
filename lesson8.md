---
layout: page
title: Lesson 8: Telephony & VoIP
permalink: /lesson8/
---
Voice communication systems.

**Key Concepts:**
- PSTN, SS7
- SIP, RTP
- VoIP architecture, Softswitches

**Why It Matters:** Still foundational for voice services in modern networks.

**Labs/Practice:** Set up VoIP calls; analyzed SIP packets.

**Tools Used:** Wireshark, OpenVPN.

# Lesson 8: Satellite Communications (Optional but Powerful)

Satellite communications is a high-growth niche in telecommunications, especially with the rise of LEO mega-constellations like Starlink, Amazon Kuiper, and OneWeb. It enables global broadband, backhaul for 5G, direct-to-device connectivity, maritime/aviation comms, and integration with NTN (Non-Terrestrial Networks) in 5G/6G standards.

## Why Satellite Communications Matters

- Provides coverage where terrestrial networks cannot reach (oceans, deserts, remote areas, disaster zones)
- Rapid deployment for emergency response and rural connectivity
- Low-latency LEO systems now compete with fiber in many use cases (20–50 ms RTT)
- Growing role in 5G/6G NTN and mobile backhaul
- Increasing demand for satellite engineers in operators, vendors, and space-tech companies

## 1. Satellite Orbits

| Orbit Type | Altitude          | Latency (RTT) | Coverage per Satellite | Number of Satellites Needed | Key Use Cases                     |
|------------|-------------------|---------------|------------------------|-----------------------------|-----------------------------------|
| **GEO**    | ~35,786 km        | 500–700 ms    | ~1/3 of Earth          | 3–4                         | TV broadcast, traditional VSAT, maritime |
| **MEO**    | 8,000–20,000 km   | 100–150 ms    | Regional/global        | Dozens                      | High-throughput backhaul, aviation |
| **LEO**    | 300–2,000 km      | 20–50 ms      | Small footprint        | Thousands                   | Broadband internet, IoT, D2D      |

### GEO vs MEO vs LEO Coverage & Latency Comparison
![GEO/MEO/LEO orbit comparison and coverage footprints](https://via.placeholder.com/800x400?text=GEO+MEO+LEO+Coverage+Comparison)  
*(Replace with actual image path or URL in your repo: e.g., images/orbits-comparison.png)*

### Typical LEO Constellation Layout
![Dense LEO satellite constellation for continuous global coverage](https://via.placeholder.com/800x400?text=LEO+Constellation+Swarm)  
*(images/leo-constellation.png)*

### LEO Satellite Visibility Geometry
![Elevation angles and slant range geometry for LEO satellites](https://via.placeholder.com/800x400?text=LEO+Visibility+Geometry)  
*(images/leo-visibility-geometry.png)*

## 2. Link Budget – The Most Important Calculation

The link budget determines whether communication is possible by balancing transmitted power, gains, and all losses.

**Basic Link Budget Equation (in dB):**
Received Power (dBm) = Tx Power + Tx Antenna Gain – Tx Losses – FSPL – Atmospheric Losses + Rx Antenna Gain – Rx Losses + Other Gains


Key terms:
- **EIRP** = Tx Power + Tx Antenna Gain
- **FSPL** (Free Space Path Loss) = 20 log₁₀(d) + 20 log₁₀(f) + 147.55 (d in km, f in GHz)
  - GEO at Ku/Ka band: ~190–205 dB
  - LEO at 12 GHz: ~140–160 dB
- **G/T** = Rx antenna gain / system noise temperature
- Rain fade, gaseous absorption, scintillation (especially >10 GHz)
- Margin: typically 3–10 dB

### Example Satellite Link Budget Waterfall
![Cumulative gains and losses in a satellite link budget](https://via.placeholder.com/800x400?text=Satellite+Link+Budget+Waterfall)  
*(images/link-budget-waterfall.png)*

### Typical Gains/Losses Breakdown
![Bar chart or diagram of major contributors in satellite link budget](https://via.placeholder.com/800x400?text=Link+Budget+Gains+and+Losses)  
*(images/link-budget-components.png)*

## 3. VSAT (Very Small Aperture Terminal)

Traditional fixed satellite access using small dishes (0.6–2.4 m).

Components:
- Outdoor Unit (ODU): Parabolic dish + LNB (receive) + BUC (transmit)
- Indoor Unit (IDU): Satellite modem/router
- Hub/Gateway: Central station for traffic aggregation

### Classic VSAT Terminal
![Traditional parabolic VSAT dish installation](https://via.placeholder.com/800x400?text=Classic+VSAT+Parabolic+Dish)  
*(images/classic-vsat-dish.png)*

### Modern Maritime/Convertible VSAT
![Flat or stabilized VSAT antenna for maritime use](https://via.placeholder.com/800x400?text=Modern+Maritime+VSAT+Antenna)  
*(images/maritime-vsat-antenna.png)*

## 4. Modern Satellite Internet – Starlink & Beyond

**Starlink (SpaceX)** – Leading LEO broadband constellation in 2026:
- >7,000 satellites in orbit
- Laser inter-satellite links (ISL) for global routing
- User terminal: Flat phased-array antenna ("Dishy") – no moving parts
- Performance: 100–300+ Mbps down / 20–50 Mbps up, 20–40 ms latency
- Direct-to-cell capability (for unmodified phones in remote areas)

### Starlink User Terminal (Gen 2 / Gen 3)
![Starlink flat phased-array user dish and router](https://via.placeholder.com/800x400?text=Starlink+User+Terminal+Gen+3)  
*(images/starlink-dish-gen3.png)*

### Starlink Portable Kit Comparison
![Side-by-side older circular vs newer rectangular Starlink dishes](https://via.placeholder.com/800x400?text=Starlink+Dish+Generations+Comparison)  
*(images/starlink-dish-comparison.png)*

## Key Takeaways

- LEO constellations revolutionized satellite broadband with low latency and high capacity
- Link budget engineering is the foundation of satellite system design
- Phased-array antennas replaced mechanical dishes for user terminals
- Satellite now plays a growing role in 5G NTN, rural connectivity, and mobile backhaul

This lesson completes the physical-layer and access-network part of the telecom roadmap — next we move into the essential tools every telecom engineer must master.
