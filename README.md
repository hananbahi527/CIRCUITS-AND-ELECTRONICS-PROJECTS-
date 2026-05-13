
# 2N2222 Common Emitter Audio Amplifier

## 📖 Table of Contents
* [ Circuit Overview](#-circuit-overview)
    * [Technical Specifications](#technical-specifications)
* [Component List](#-component-list)
* [⚙️ Functional Description](#️-functional-description)
    * [1. Biasing & Stability](#1-biasing--stability)
    * [2. Signal Coupling](#2-signal-coupling)
    * [3. Gain Optimization](#3-gain-optimization)
    * [4. Power Integrity](#4-power-integrity)
    * [5. Hardware Implementation](#5-Hardware-Implementation )
* [ Getting Started](#-getting-started)
An implementation of a single-stage **Common Emitter (CE) Audio Amplifier** using the 2N2222 NPN transistor. This project focuses on signal amplification from low-power sources (e.g., mobile devices) to drive an 8Ω speaker load.

##  Circuit Overview
The circuit leverages the common-emitter configuration to achieve high voltage gain. It includes a voltage-divider biasing network for stability and coupling capacitors to isolate DC stages.

### Technical Specifications
- **Voltage Supply:** 12V DC
- **Input Sensitivity:** 50–100 mV AC @ 1 kHz
- **Output Impedance:** 8Ω (Typical)
- **Configuration:** Class A Amplifier

## Component List

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

![Audio Amplifier](./Audio%20Amplifier.jpeg)

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

##  Hardware Implementation

![Audio Amplifier](./Audio%20Amplifier%20p.jpeg)

The physical build follows a compact layout to minimize parasitic capacitance and noise. Below is a breakdown of the key physical sections:

* **Q1 (Transistor):** Centrally mounted 2N2222 NPN transistor. Ensure the flat face is oriented correctly according to the pinout (E-B-C).
* **Input Stage (Left):** The **C2 (100µF)** capacitor is located near the input terminals to isolate the DC bias from the audio source immediately.
* **Bias Control:** The **RV1 (10kΩ Potentiometer)** is positioned for easy access, allowing real-time adjustment of the collector voltage to find the optimal Q-point.
* **Output Stage (Right):** The large **C3 (470µF)** and **C1 (1000µF)** capacitors dominate this area. C1 is placed parallel to the emitter resistor (R3) to shunt AC signals to ground.
* **Power Rails:** The 12V supply line is filtered by the **C4 (100nF)** ceramic disc capacitor, placed as close to the collector resistor (R4) as possible to stabilize the supply.

> [!NOTE]
> For best performance, use short jumper wires to prevent the circuit from acting as an antenna and picking up 50/60Hz mains hum.

---

## 🚀 Getting Started
1. **Connect Power:** Apply 12V DC to the designated power rails.
2. **Inject Signal:** Connect an audio source (mobile phone/PC) to the input via C2.
3. **Calibration:** While playing a 1kHz sine wave (or steady music), slowly turn **RV1** until the output at the speaker is loud and clear without "raspy" distortion.
4. **Monitor Heat:** The 2N2222 should remain cool to the touch during operation at these current levels.

---
*Developed for educational electronics experimentation.*
