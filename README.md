### **1. Introduction**

The objective of this project is to design and simulate a **single-stage audio amplifier** using the **2N2222 NPN transistor** in a **Common Emitter (CE)** configuration. This circuit is designed to take a low-power audio signal (such as from a mobile phone jack) and amplify it to a level sufficient to drive a small loudspeaker.

---
# 2N2222 Common Emitter Audio Amplifier

![Status](https://img.shields.io/badge/Status-Prototype-orange)
![License](https://img.shields.io/badge/License-MIT-blue)

An implementation of a single-stage **Common Emitter (CE) Audio Amplifier** using the 2N2222 NPN transistor. This project focuses on signal amplification from low-power sources (e.g., mobile devices) to drive an 8Ω speaker load.

## 📌 Circuit Overview
The circuit leverages the common-emitter configuration to achieve high voltage gain. It includes a voltage-divider biasing network for stability and coupling capacitors to isolate DC stages.

### Technical Specifications
- **Voltage Supply:** 12V DC
- **Input Sensitivity:** 50–100 mV AC @ 1 kHz
- **Output Impedance:** 8Ω (Typical)
- **Configuration:** Class A Amplifier

## 🛠 Component List

| Reference | Component | Value | Description |
| :--- | :--- | :--- | :--- |
| **Q1** | 2N2222 | NPN Transistor | Primary amplifying device. |
| **BAT1** | Power Supply | 12V | Provides DC operating voltage. |
| **RV1** | Potentiometer | 10kΩ | Fine-tunes the base bias point. |
| **R2** | Resistor | 470Ω | Fixed part of the biasing network. |
| **R3** | Resistor | 100Ω | Emitter resistor for thermal stability. |
| **R4** | Resistor | 100Ω | Collector resistor to develop AC output. |
| **C1** | Electrolytic Cap | 1000µF | Emitter bypass (maximizes AC gain). |
| **C2** | Electrolytic Cap | 100µF | Input DC blocking/coupling. |
| **C3** | Electrolytic Cap | 470µF | Output DC blocking/coupling. |
| **C4** | Ceramic Cap | 100nF | Supply decoupling/noise filtering. |
| **LS1** | Speaker | 8Ω | Output transducer. |

## ⚙️ Functional Description

### 1. Biasing & Stability
The **Biasing Network (RV1 & R2)** sets the Q-point of the transistor. This ensures the 2N2222 operates in the **Active Region**, preventing signal clipping. **R3** provides negative feedback to prevent thermal runaway.

### 2. Signal Coupling
- **Input (C2):** Blocks DC from the source while passing the audio signal to the base.
- **Output (C3):** Passes the amplified AC signal to the speaker while blocking the 12V DC rail.

### 3. Gain Optimization
The **Emitter Bypass Capacitor (C1)** is essential for high gain. It provides a low-impedance path for AC signals to bypass R3, ensuring the AC voltage gain is roughly calculated by:
$$A_v \approx \frac{R_C}{r_e}$$

### 4. Power Integrity
**C4 (100nF)** is placed across the supply rails to filter out high-frequency switching noise and stabilize the DC input.

## 🚀 Getting Started
1. Clone the repository.
2. Refer to the `/schematics` folder for the wiring diagram.
3. Apply 12V to the power rails.
4. Adjust **RV1** until the output audio is clear and undistorted.

---
*Developed for educational electronics experimentation.*
