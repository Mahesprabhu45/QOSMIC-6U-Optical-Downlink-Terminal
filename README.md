# QOSMIC 6U CubeSat – 1 Gbps Optical Downlink Terminal

This repository documents the **design, architecture, and analysis of a 1 Gbps optical communication terminal** developed for a **6U CubeSat platform** under the QOSMIC Grand Challenge framework.

The project focuses on a **flight-qualified electronics subsystem** capable of high-speed optical downlink, precise pointing control, and reliable operation in a low Earth orbit (LEO) radiation environment.

---

## 📌 Project Overview

- **Mission Type:** CubeSat Optical Communication Payload  
- **Form Factor:** 6U CubeSat  
- **Downlink Data Rate:** 1 Gbps (OOK modulation @ 1550 nm)  
- **Orbit Assumption:** 500 km Sun-Synchronous Orbit (SSO)  
- **Operational Lifetime:** 5 years  
- **Power Budget:** < 20 W (EPS-compliant)

The system integrates **high-speed digital processing, optical receiver and transmitter electronics, fast steering mirror (FSM) control, radiation mitigation techniques, and flight-ready power and thermal design**.

---

## 🧩 System Architecture

The optical terminal consists of the following major subsystems:

### 1. Digital Processing
- Radiation-tolerant FPGA (Kintex UltraScale+ class)
- Implements:
  - Clock and Data Recovery (CDR)
  - 8b/10b encoding/decoding
  - Reed–Solomon FEC
  - Adaptive thresholding
  - SpaceWire communication
  - Pointing control logic

### 2. Optical Receiver Chain
- InGaAs APD detector with low-noise TIA
- High-speed ADC (>3 GS/s)
- Digital signal processing for centroiding and tracking

### 3. Optical Transmitter
- 1550 nm space-qualified laser module
- High-speed laser driver
- Power-controlled optical output for EPS safety

### 4. Pointing and Tracking
- MEMS Fast Steering Mirror (FSM)
- High-resolution DAC control
- Closed-loop bandwidth >1 kHz
- Achieves <5 µrad RMS pointing accuracy

### 5. Power and Thermal Management
- Radiation-tolerant DC–DC converters
- Controlled power sequencing
- Passive thermal design using copper inserts / IMS PCBs
- No active TEC required

---

## ⚡ Key Specifications

| Parameter | Value |
|--------|------|
| Downlink Rate | 1 Gbps |
| Wavelength | 1550 nm |
| Total Power (Nominal) | ~18.2 W |
| Total Power (Worst-case mitigated) | ~19.6 W |
| Pointing Accuracy | < 5 µrad RMS |
| Closed-loop Latency | ~202 µs |
| FPGA Utilization | < 30% |
| First Mechanical Mode | > 500 Hz |

---

## 🛡️ Reliability and Radiation Mitigation

Designed for long-duration LEO operation:

- Configuration memory scrubbing (10-minute interval)
- Triple Modular Redundancy (TMR) for critical logic
- SECDED ECC for memories
- Dual watchdog architecture
- Automatic recovery from SEU/SEFI events
- System-level reliability: **~0.97–0.98 over 5 years**

---

## 🧪 Testing and Validation

The design includes a comprehensive verification plan:

- Board-level bring-up and characterization
- Hardware-in-the-loop (HIL) optical simulation
- Thermal vacuum (TVAC) testing
- Random and sine vibration testing (NASA GEVS)
- EMI/EMC compliance
- Radiation testing (TID and SEE)

---

## 📁 Repository Contents

```text
├── docs/                 # Technical report, analysis, and design documentation
├── diagrams/             # System block diagrams and architecture figures
├── firmware/             # FPGA architecture descriptions (VHDL/Verilog concepts)
├── power-thermal/        # Power budget and thermal calculations
├── reliability/          # FMEA, MTBF, and radiation mitigation analysis
└── README.md
🚀 Applications

CubeSat optical downlink missions

Deep-space communication technology demonstrators

High-speed satellite payload electronics

Academic and research-oriented space systems

📜 Disclaimer

This repository represents a design study and engineering analysis intended for academic, research, and concept-demonstration purposes.
It does not include ITAR-restricted information or proprietary flight hardware designs.
