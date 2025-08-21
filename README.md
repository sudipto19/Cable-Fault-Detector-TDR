# Cable Fault Detector using TDR

This project is a Cable Fault Detector based on Time Domain Reflectometry (TDR). It helps in identifying faults in cables by sending a pulse and analyzing the reflected signal.

## Circuit Diagrams

### Circuit 1
![Circuit 1](Images/Circuit%201.jpeg)

### Circuit 2
![Circuit 2](Images/Circuit%202.jpeg)

## Schematics

### Schematic 1
![Schematic 1](Images/Schematic%201.jpg)

### Schematic 2
![Schematic 2](Images/Schematic%202.jpg)

## How It Works

1. A pulse is sent down the cable.
2. If there is a fault, the pulse is reflected back.
3. The time taken for the reflection helps determine the location of the fault.

---

## Project Overview

A compact Time Domain Reflectometer (TDR) add-on for oscilloscopes, featuring two pulse generation methods:
- **Schmitt-trigger (74AC14) pulse generator** for coarse/long-range scans
- **Avalanche transistor + Cockcroft–Walton multiplier** for high-voltage, ultra-fast pulses and high-resolution fault localization

This README covers design intent, differences between pulse modules, calibration notes, safety warnings, and future improvements.

---

## Key Features

- Dual pulse sources for multi-resolution TDR testing (coarse scan and high-resolution probe)
- Simple oscilloscope interface
- Configurable resistive splitting/termination for high-impedance and 50 Ω setups
- Battery operation for low-voltage stage; compact voltage-multiplier for high-voltage stage

---

## Design Summary

### Circuit 1 — 74AC14 Schmitt-trigger Pulse Generator
- Generates square/short pulses using a hex inverter
- Low voltage operation (~4.5 V)
- Suitable for long, lossy cables and coarse fault location
- Simple, low-cost, compatible with common oscilloscopes

### Circuit 2 — Avalanche Transistor + Cockcroft–Walton Multiplier
- High-voltage, ultra-fast pulse generation for high spatial resolution
- Uses oscillator, flyback inductor, voltage multiplier, and avalanche transistor
- Suitable for short cable segments and fine fault localization
- Requires careful handling due to high voltages

---

## Connections & Usage Notes

- Use BNC T-piece and scope's high-impedance input for general testing
- For 50 Ω setups, use matched resistive splitter and terminated path
- Connect TRIG output to oscilloscope external trigger for stable traces

---

## Calibration & Typical Pulse Settings

| Pulse Length | Frequency (approx.) | Blind Spot | Practical Range |
|-------------:|--------------------:|-----------:|----------------:|
| 10 ns        | ~50 MHz             | ~4 m       | up to ~500 m    |
| 50 ns        | ~10 MHz             | ~8 m       | longer than 10 ns|
| 200 ns       | ~2.5 MHz            | ~30 m      | up to ~1.5 km   |
| 1 µs         | ~500 kHz            | ~100 m     | up to ~5 km     |
| 5 µs         | ~100 kHz            | ~600 m     | very long range |

**Note:** RG-58 is a 50 Ω coaxial cable; RG-59 is 75 Ω. Always match termination to cable impedance to avoid reflections.

---

## Safety & Handling

- High-voltage stage can reach several hundred volts; treat all high-voltage areas as live
- Discharge capacitors safely before handling
- Only work on high-voltage stage with proper experience and equipment
- Use proper grounding for oscilloscope probe

---

## Suggested Improvements / Future Work

- Improve pulse shaping for even higher resolution
- Add automated calibration routines
- Enhance safety features and enclosure design

---

## References

1. **Cockcroft, J. D., & Walton, E. T. S.** (1932). "Experiments with High Velocity Positive Ions." *Proceedings of the Royal Society of London*, Series A, 137(831), 229-242.

2. **Furse, C., & Haupt, R.** (2001). "Down to the wire." *IEEE Spectrum*, 38(2), 34-39.

3. **Smith, P., Furse, C., & Gunther, J.** (2005). "Analysis of spread spectrum time domain reflectometry for wire fault location." *IEEE Sensors Journal*, 5(6), 1469-1478.

4. **Agilent Technologies.** (2006). "Time Domain Reflectometry Theory." *Application Note AN-1287-2*.

5. **Nahman, N. S., & Guillaume, M. E.** (1980). "Deconvolution of time domain waveforms in the presence of noise." *NBS Technical Note 1047*, National Bureau of Standards.

6. **Andrews, J. R., & Bell, B. A.** (1982). "Broadband sampling oscilloscope techniques." *IEEE Transactions on Microwave Theory and Techniques*, 30(11), 1913-1920.

7. **Hippel, A. R.** (1954). *Dielectrics and Waves*. John Wiley & Sons, New York.

8. **Texas Instruments.** (2013). "74AC14 Hex Schmitt-Trigger Inverter Datasheet." *Literature Number: SCLS089J*.

**Note:** This project was developed independently, incorporating principles from the above references and standard TDR literature.

## Images

All images used in this project are located in the `Images` folder.
