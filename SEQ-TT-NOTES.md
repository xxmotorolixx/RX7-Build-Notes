# RX-7 FD3S – Sequential Turbo Control Development Plan

## Project Overview

This vehicle was being converted to a **hybrid control strategy**:

- **Link G4X ECU**
  - Full primary turbo boost control (wastegate PWM)
  - Closed-loop boost management
- **ESP32 (Wemos D1 Mini)**
  - Controls sequential turbo support system only
  - Manages secondary turbo staging solenoids
  - Planned CAN integration with Link ECU
  - Planned auxiliary fan relay control

**Goal:**
- Maintain OEM-like sequential behavior
- Default to **safe parallel turbo mode if ESP32 fails**
- Keep primary boost control fully under Link ECU authority

---

## Electrical Architecture

### Controllers

**Link G4X ECU**
- Primary wastegate solenoid (PWM)
- Boost control strategy
- Engine management

**ESP32 – Wemos D1 Mini**
- Sequential solenoid controller
- Future CAN listener (RPM, TPS, MAP, coolant temp)
- Future fan relay trigger

---

## Solenoid Assignment (ESP32 Controlled)

### PWM-Controlled (1)
| Solenoid | ESP32 Pin | MOSFET | Function |
|----------|-----------|--------|---------|
| Secondary Turbo Control | GPIO 25 | LR7843 | Modulates vacuum/boost to secondary turbo actuator during staging |

### ON/OFF Solenoids (4)
| Solenoid | ESP32 Pin | MOSFET | Function |
|----------|-----------|--------|---------|
| Purge Vacuum | GPIO 14 | IRF520 | Dumps stored vacuum |
| Charge Control | GPIO 12 | IRF520 | Routes boost/vacuum during changeover |
| Charge Relief | GPIO 13 | IRF520 | Relieves pressure during transition |
| Air Bypass Valve | GPIO 27 | IRF520 | Manages airflow routing between turbos |

---

### Electrical Notes
- All solenoids: **12V automotive**
- Low-side switched via MOSFET
- Flyback diode required across each solenoid
- Common ground between:
  - ESP32
  - Link ECU
  - Chassis ground
- LR7843 recommended for PWM
- IRF520 acceptable for simple ON/OFF

---

## Vacuum & Boost Routing Plan

### Vacuum Source
- Intake manifold vacuum
- One check valve before distribution
- Single-port vacuum chamber used for reserve

**Vacuum layout**
