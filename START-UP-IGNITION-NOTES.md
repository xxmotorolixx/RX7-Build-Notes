# Mazda RX-7 FD3S (13B-REW) – Build Notes & Planned Upgrades

---

## 🔧 Internal Technical Build Documentation

### 1️⃣ Verify Engine Operation (Baseline Plan)

Run engine on OEM coils + OEM igniter. Confirm:

- Clean start  
- Stable idle  
- No misfire  
- Proper timing sync in Link G4X ECU  
- Validate base ignition timing with timing light  
- Confirm dwell and trigger settings in ECU  

---

### 2️⃣ LS D585 Coil Conversion (Planned Upgrade)

- Remove OEM igniter  
- Unplug and isolate OEM igniter  
- Do **not** reuse coil-side 4-pin sub-harness for triggers  
- Repurpose igniter-side harness:  
  - ECU ignition outputs from igniter connector → LS coil trigger wires  
- Route directly to individual LS coil trigger wires  

---

### 3️⃣ DIY LS Coil Harness Plan

**Power:**

- Switched +12V (Black/Red OEM wire)  
- Add 15–20A fuse  
- Run 14 AWG to LS coil power (shared pink wire)  

**Grounds:**

- 14 AWG from LS coils  
- Ring terminal to engine block  
- Do not ground through chassis alone  

**Trigger Wires:**

- 20 AWG from Link G4X IGN outputs  
- Connect to unique LS trigger wires: Red, Green, Blue, Pink (thin)  

**Wiring Specs:**

- Power: 14 AWG  
- Ground: 14 AWG  
- Trigger: 20 AWG  
- All unused OEM coil-side wires capped and isolated  
- Keep power and trigger wiring separated to reduce interference  

**Optional (Cleanest Approach):**

- Consider plug-and-play igniter-delete harness instead of full DIY splice  
- Maintain OEM harness integrity where possible  

---

### 4️⃣ ECU Configuration (After LS Install)

- Ignition Mode: Direct Spark  
- Ignition Type: Logic Level  
- Spark Edge: Falling  
- Dwell @ 14V: ~3.2–3.5 ms  
- Multi-spark: OFF  

---

### 5️⃣ Physical Mounting Plan

- Remote mount LS coils away from turbo heat  
- Custom bracket solution  
- Short, equal-length plug wires  
- Heat shielding as needed  

---

### 6️⃣ Validation Checklist

- Confirm spark on all four events  
- Verify tachometer signal behavior  
- Check dwell settings in ECU  
- Confirm clean idle + high-RPM stability  
- Monitor for misfire under boost  

---

## 🚀 Future Upgrade Roadmap (Buyer-Facing Overview)

**Ignition System Modernization:**

- Transition to LS smart coil setup  
- Stronger, consistent spark delivery  
- Modernized ignition architecture  
- Improved boost reliability  
- Cleaner engine bay wiring layout  

**Electrical Refinement:**

- Dedicated fused power circuit  
- Improved grounding strategy  
- Cleaner harness routing  
- Reversible integration (no OEM damage)  

**Reliability Focus:**

- Reduce ignition-related misfires  
- Improve high-RPM spark stability  
- Reduce dependency on aging OEM components  
- Increase tuning headroom  

**Long-Term Vision:**

- Prepare for standalone ECU compatibility  
- Modular electrical system design  
- Maintain serviceability  
- Preserve OEM integrity wherever possible  

---
