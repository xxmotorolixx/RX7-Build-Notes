# RX-7 Build – Latest Planned Cooling System Todos

## RX-8 Fans on RX-7 – Custom Implementation

### Planned System Direction
- **Fan 1:** Low-temperature cooling
- **Fan 2:** High-temperature assist
- No OEM RX-8 relays or controllers used

### Electrical Setup
- **One relay per fan**
- **One inline fuse per fan**
- 12V **full-speed operation** (no resistor)
- Ground directly to chassis

### Trigger Strategy
- **Fan 1 ON:** ~85–90°C
- **Fan 2 ON:** ~95–100°C
- Controlled via:
  - Thermostatic switch or standalone controller
  - Optional manual override switch

### Electrical Sizing
- Typical running draw: ~8–12A per fan
- Startup spike slightly higher (~10–15A)
- Use:
  - 15–20A fuse per fan
  - 30–40A rated relays for safety
  - Proper gauge wiring (10–12 AWG recommended)

### Benefits of This Setup
- Simple and reliable compared to dual-speed voltage drop method
- No resistors generating excess heat
- Lower electrical load during normal operation
- Redundancy if one fan fails
- Can upgrade to PWM control in future if desired
