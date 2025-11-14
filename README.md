# LED-chaser-PCB
555 timer + CD4017 LED chaser PCB project built in KiCad 9.0
# LED Chaser PCB (555 Timer + CD4017)

> A simple, resume-ready hardware project that sequences LEDs using a 555 astable clock and a CD4017 decade counter. Built in KiCad 9.0 and tested with a multimeter & oscilloscope.

## 🎯 Objectives
- Practice schematic capture & PCB layout in KiCad 9.0
- Demonstrate troubleshooting to component level (DMM & scope)
- Document a complete build: design → fabricate → test → lessons learned

## 🧩 Overview
This board generates a square-wave clock using a 555 timer and advances a CD4017 counter to light LEDs sequentially.
It’s a classic beginner-to-intermediate project that shows placement, routing, decoupling, and test skills.

- Board size: **70 × 50 mm**, FR-4, 2-layer
- Ground: **dual planes** with via stitching
- Fabrication: **Gerber X2** + Excellon drill; JLCPCB lead-free HASL

## 📦 Bill of Materials (BOM)
| Qty | Part | Value / PN | Notes |
|---:|---|---|---|
| 1 | 555 timer | NE555 | Astable oscillator |
| 1 | Decade counter | CD4017 | Drives 10 outputs |
| 10 | LEDs | Red (or your choice) | With current-limit resistors |
| 10 | Resistors | e.g., 330 Ω | LED current limiting |
| 2 | Caps | e.g., 0.1 µF, 10 µF | Decoupling / timing |
| 1 | R (timing) | e.g., 10 kΩ | Sets clock freq |
| 1 | Pot (optional) | e.g., 50 kΩ | Adjustable speed |
| 1 | Power header | 5 V input | Bench supply or USB-5V |

*(Adjust values to your design.)*

## 🧠 Schematic
> Add your schematic image(s) below. Export PNG from KiCad.  
![Schematic](link-to-your-schematic.png)

### 555 Astable
- Duty & frequency set by R/C
- Output feeds CD4017 clock input

### CD4017
- Q0..Q9 outputs drive LEDs through resistors
- Reset pin tied appropriately; enable handled per design

## 🗺 PCB Layout
> Add board renders or photos here.  
![PCB Top](link-to-your-pcb-top.png)  
![PCB Bottom](link-to-your-pcb-bottom.png)

**Rules used**
- Clearance: **0.30 mm**; Min track: **0.25 mm**
- Vias: **0.60/0.30 mm**
- Thermal reliefs: **0.45/0.50 mm** on GND pads

## 🧪 Testing & Validation
**Bench Setup**
- Supply: 5 V (bench PSU)
- Tools: DMM for rails/continuity; Oscilloscope for clock and outputs

**What to Measure**
- 5 V rail at key nodes (DMM)
- 555 output: amplitude & frequency (scope)
- CD4017 outputs: verify sequence (scope or visual)

**Sample Results Table**
| Test Point | Expected | Measured | Pass/Fail |
|---|---|---|---|
| VCC | 5.00 V |  |  |
| 555 OUT | ~VCCpp, f≈? Hz |  |  |
| Q0..Q9 | Sequential toggle |  |  |

## 🔧 Troubleshooting Log
- YYYY-MM-DD – LED #n not lighting → continuity check found cold joint → reflowed → PASS  
- YYYY-MM-DD – No clock → swapped 555, verified timing caps → PASS

## 📸 Results
> Drop photos or a short GIF of the LEDs chasing.  
![Bench Photo](link-to-bench-photo.jpg)  
![Demo GIF](link-to-demo.gif)

## 📝 Lessons Learned
- Grounding & decoupling strategy matters (noise immunity)
- Systematic debug: **visual → DMM → scope**
- Keep silkscreen legible; align reference designators

## ▶️ Next Steps
- SMD variant
- Microcontroller-driven patterns (PWM dimming)
- Panelize for multi-board run

---

**Author:** Luis Morales Jr — [LinkedIn](https://www.linkedin.com/in/luis-morales-jr/)  
**Repo:** https://github.com/luis-morales-jr/led-chaser-pcb
