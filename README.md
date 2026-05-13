### **1. Introduction**

The objective of this project is to design and simulate a **single-stage audio amplifier** using the **2N2222 NPN transistor** in a **Common Emitter (CE)** configuration. This circuit is designed to take a low-power audio signal (such as from a mobile phone jack) and amplify it to a level sufficient to drive a small loudspeaker.

---

### **2. Component Specifications**

The following components were utilized in the circuit design:
Component,Label,Value / Model,Function
Transistor,Q1,2N2222 (NPN),The primary amplifying element.
Power Supply,BAT1,12V DC,Provides the energy for amplification.
Input Signal,V1,VSINE (50-100mV),Simulates the AC audio input.
Coupling Caps,"C2, C3","100µF, 470µF",Blocks DC offset while passing AC signals.
Bypass Cap,C1,1000µF,Increases AC gain by bypassing R3.
Resistors,"R2, R3, R4","470Ω, 10Ω*, 100Ω",Defines the DC bias and stabilization.
Potentiometer,RV1,10kΩ,Allows fine-tuning of the base bias.
Load,LS1,8Ω Speaker,Converts electrical signals to sound.
