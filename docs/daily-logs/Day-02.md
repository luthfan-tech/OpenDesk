# Day 2: Ideation, Case Study & The Pivot to PondSense

- **Date:** 20 November 2026
- **Phase:** Research & Systems Engineering
- **Focus:** 10-idea comparative analysis, market problem identification in Indian aquaculture, and architectural specification of the PondSense buoy.
- **Primary Research Document:** [PondSense_Research_Log.pdf](../research/PondSense_Research_Log.pdf)

---

## 1. Why Pivot? The 4-Filter Evaluation

Yesterday's "smart desk" concept was formally discarded after testing it against four rigorous product criteria:
1. **Novel Framing:** Don't build "X because it's cool"; build "X because Y is broken in the real world."
2. **Visible Impact:** Demonstrable to a non-technical audience in under 60 seconds.
3. **Technical Depth:** Non-trivial intersection of mechanical CAD, RF engineering, embedded firmware, and software.
4. **Narratable:** A clear human story with an urgent, identifiable beneficiary.

---

## 2. Idea Evaluation & The Decision Matrix

Ten engineering concepts were developed and evaluated:

| # | Project Idea | Verdict | Key Takeaway |
| :--- | :--- | :--- | :--- |
| 1 | **Water / Aquaculture Intelligence Node** | **WINNER** | Real pain, high impact on fish farmers, visually dramatic, multi-domain |
| 2 | Open-Source Printable Microscope | REJECTED | Too similar to existing OpenFlexure project |
| 3 | Dangerous Space Mapping Robot | Shortlisted | High safety narrative, but complex mechanical locomotion |
| 4 | Personal Satellite Ground Station | REJECTED | Technically cool, but lacking a clear paying customer |
| 5 | Structural Health Vibration Monitor | REJECTED | Hard to validate without commercial structural test beds |
| 6 | ₹500 Brain-Computer Interface | REJECTED | High noise-to-signal ratio, low reliability on breadboard |
| 7 | Physical Penetration Testing Drone | Shortlisted | Great security alignment, but high regulatory & crash risk |
| 8 | Underground Soil Intelligence Network | Shortlisted | Strong agricultural impact, but harder to demonstrate visually |
| 9 | Acoustic Gunshot Localisation Network | REJECTED | Limited immediate civilian testing pathways |
| 10 | Cold Chain Audit Capsule | CONSIDERED | High supply chain complexity |

### Final Shortlist Matrix

| Project | Solves Real Problem | Visual / Social Appeal | Career Alignment | 30s Demo Viability | Verdict |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Water Node (#1)** | **Yes — Fish Farmers** | **High** | **Medium** | **Yes (Bucket test)** | **WINNER** |
| Dangerous Space Robot (#3) | Yes — Safety Workers | Medium | Medium | Hard | Runner-up |
| Pen-Test Drone (#7) | Yes — Security Teams | High | High | Yes | Runner-up |
| Soil Network (#8) | Yes — Crop Farmers | Medium | Low | Hard | Runner-up |

---

## 3. The Core Problem: The Dissolved Oxygen Crisis in Aquaculture

India's aquaculture sector is a **₹50,000 Crore** industry, primarily powered by small- and medium-scale rural farmers.

### The Overnight Kill Phenomenon
- In freshwater fish ponds, dissolved oxygen (DO) levels fluctuate drastically due to photosynthesis during the day and respiration/decomposition at night.
- Between **2:00 AM and 6:00 AM**, algal die-offs or temperature inversions can cause DO levels to drop below 3.0 mg/L.
- At these levels, commercial fish stocks (Rohu, Catla, Tilapia) suffocate and die within hours.
- A single overnight DO crash can wipe out an entire season's harvest, causing catastrophic financial losses.

### The Market Gap
- **Commercial water quality buoys:** Cost **₹20,000 to ₹80,000+**, far out of reach for smallholder farmers.
- **Current practice:** Manual chemical strip testing once a day, which completely misses overnight hypoxia events.
- **The Opportunity:** Build an autonomous, floating solar buoy under **₹2,000 (~$25 USD)** that monitors DO, pH, temperature, and turbidity continuously.

---

## 4. Architectural Decisions

```
+-------------------------------------------------------------+
|                     PondSense Buoy                          |
|  [ Solar Panel ] ---> [ TP4056 + 18650 LiPo (3.7V) ]         |
|                                |                            |
|  [ DO Sensor ]                 v                            |
|  [ pH Probe ] ------> [ ESP32 Microcontroller ]             |
|  [ DS18B20 Temp ]              |                            |
|  [ Turbidity ]                 v                            |
|                    [ SX1276 LoRa (865 MHz) ]                |
+--------------------------------|----------------------------+
                                 | RF Packet (2 - 10 km range)
                                 v
+-------------------------------------------------------------+
|                  Base Station / Gateway                     |
|  [ SX1276 LoRa Receiver ] ---> [ ESP32 / Raspberry Pi ]     |
|                                        |                    |
|                                        v (WiFi / Hotspot)   |
|                             [ Python Flask Backend ]        |
|                                        |                    |
|                                        v                    |
|                             [ Mobile Web Dashboard ]        |
+-------------------------------------------------------------+
```

### Why LoRa over Wi-Fi/GSM?
- **Range & Independence:** Ponds are typically 1–3 km away from farmhouses and lack Wi-Fi coverage.
- **Zero Ongoing Cost:** Operates on the license-free **865–867 MHz ISM band (India)** with no monthly cellular SIM recharge fees.
- **Low Power:** Allows the buoy to operate indefinitely on a modest solar panel and single 18650 LiPo cell.

---

## 5. 30-Day Execution Scope

Because the Autodesk Fusion 360 trial provides a strict 30-day window, the deliverables are cleanly segmented:

| Deliverable | In 30-Day Window? | Details |
| :--- | :---: | :--- |
| **Buoy Hull 3D CAD (Fusion 360)** | **Yes** | Hydrodynamic, waterproof floating enclosure with O-ring seal |
| **Internal Chassis CAD** | **Yes** | Modular sensor brackets, battery cradle, and electronics tray |
| **BOM & Supplier Sourcing** | **Yes** | Sourced from Indian vendors (ROBU.in, Evelta) under ₹2,000 |
| **Node Firmware (ESP32 C++)** | **Yes** | Sensor sampling, power saving / deep sleep, LoRa packet TX |
| **Gateway Code** | **Yes** | Packet decoding, CRC checks, local JSON forwarder |
| **Flask Dashboard** | **Yes** | Live metrics, alert thresholds, mobile UI |
| **Physical 3D Printing & Field Test** | Post-30 Days | Summer break / vacation fabrication and pond deployment |

---

## 6. Deliverable Artifact
The full 5-page research document is permanently archived in the repository:
- **File:** [docs/research/PondSense_Research_Log.pdf](../research/PondSense_Research_Log.pdf)
