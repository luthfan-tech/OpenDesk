# Day 1: Project Blueprint, Architecture & Fusion 360 Orientation

- **Date:** Day 1
- **Focus:** Repository setup, system architecture, BOM planning, and Fusion 360 introduction.

---

## 1. What was done today
- Initialized the OpenDesk project repository and established the directory layout (`cad/`, `firmware/`, `web/`, `docs/`).
- Defined the core problem statement and system requirements for **OpenDesk v1**.
- Formulated the hardware Bill of Materials (BOM) centered around the ESP32 microcontroller.
- Installed and configured Autodesk Fusion 360:
  - Switched default design units to **millimeters (mm)**.
  - Practiced 3D canvas navigation (Pan, Orbit, Zoom).
  - Learned basic 2D sketching, constraints (Coincident, Horizontal/Vertical), and dimensioning.

---

## 2. System Architecture (v1)

```
[ DHT11 / DHT22 Sensor ] ---> (Temperature / Humidity) ---+
                                                          |
[ LDR Light Sensor ] --------> (Ambient Light Level) -----+---> [ ESP32 Controller ]
                                                                      |
                                                                      +---> [ Web Dashboard (HTTP/WebSockets) ]
                                                                      |
                                                                      +---> [ 5V Relay Module ] ---> [ Desk Lamp / Fan ]
                                                                      |
                                                                      +---> [ Status LEDs ]
```

---

## 3. Bill of Materials (BOM)

| Item | Component | Purpose |
| :--- | :--- | :--- |
| 1 | ESP32 DevKit V1 | Main microcontroller with built-in Wi-Fi |
| 2 | DHT11 / DHT22 | Ambient temperature and humidity monitoring |
| 3 | LDR Module / Photoresistor | Desk light level sensing |
| 4 | 5V Single Channel Relay Module | AC/DC switching for desk lighting or fan |
| 5 | LEDs & 220Ω Resistors | Local visual status indicators |
| 6 | Breadboard & Jumper Wires | Rapid circuit prototyping |

---

## 4. Key Learnings (Fusion 360)
- **Always anchor sketches to the Origin `(0,0,0)`** to keep sketches predictable and prevent accidental translation.
- **Constraints over raw dimensions:** Geometric constraints (like `Horizontal`, `Vertical`, `Equal`, and `Symmetric`) reduce the number of explicit numbers you have to maintain.
- **Blue vs. Black sketch lines:** Black lines mean the geometry is fully constrained in size and position. Blue lines mean the shape can still be distorted.

---

## 5. Next Steps (Day 2)
- 3D Extrusion and turning 2D sketches into solid 3D bodies in Fusion 360.
- Using Fusion 360 **User Parameters** (parametric design) so dimensions can be changed without breaking the model.
- Setting up the ESP32 development environment (VS Code + PlatformIO or Arduino IDE).
