# PondSense: Bill of Materials (BOM)

Target Budget: **Under ₹2,000 per node** (India market pricing via ROBU.in, Evelta, QuartzComponents)

| # | Component | Model / Spec | Interface / Role | Est. Price (INR) | Source |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Microcontroller | ESP32-WROOM-32 (30-pin DevKit) | Core MCU (ADC, SPI, Sleep modes) | ₹380 | ROBU.in |
| 2 | LoRa Transceiver | SX1276 / Ra-02 (865 MHz ISM) | SPI long-range radio (2–10 km) | ₹350 | ROBU.in / Evelta |
| 3 | Water Temp Sensor | DS18B20 (Waterproof probe) | 1-Wire digital temperature | ₹95 | ROBU.in |
| 4 | Turbidity Sensor | TS-300B Analog Turbidity Module | Analog output (0–4.5V) | ₹240 | QuartzComponents |
| 5 | pH Sensor Probe | Analog pH Sensor Kit v1.1 | Analog voltage probe | ₹520 | ROBU.in |
| 6 | Power: Battery | 18650 Li-Ion Cell (3.7V 2600mAh) | Primary power storage | ₹140 | Local / ROBU.in |
| 7 | Solar Panel | 5V 1.5W Monocrystalline Panel | Daylight battery harvesting | ₹130 | ROBU.in |
| 8 | Solar Charger | TP4056 with DW01A Protection | Li-Ion charge controller | ₹25 | QuartzComponents |
| 9 | Enclosure Hardware | M3 SS Screws + Silicone O-Ring + PG7 Gland | Watertight sealing | ₹80 | Hardware store |
| 10 | 3D Filament | PETG / ASA filament (~250g) | UV & water-resistant buoy hull | ₹150 | Indian RepRap |
| **Total** | | | | **~₹2,110** | *(Competitive vs ₹40,000+ commercial systems)* |

> *Note: For Dissolved Oxygen (DO), commercial industrial probes exceed ₹5,000. For PondSense v1, we evaluate an affordable galvanic DO probe circuit or galvanic DO proxy cell to maintain the sub-₹2,000 target.*
