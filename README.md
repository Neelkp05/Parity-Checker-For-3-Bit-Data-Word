<div align="center">

# VLSI Design: 3-Bit Parity Checker
### CMOS Implementation & Layout Simulation using Microwind

<p align="center">
  <img src="https://img.shields.io/badge/Course-VLSI_Design-blue?style=for-the-badge&logo=intel" />
  <img src="https://img.shields.io/badge/Tool-Microwind-orange?style=for-the-badge&logo=c" />
  <img src="https://img.shields.io/badge/Technology-CMOS_120nm_%7C_180nm-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/University-Nirma_University-red?style=for-the-badge" />
</p>

</div>

---

## 📄 Abstract
This project presents the design, simulation, and layout analysis of a **Parity Checker for a 3-Bit Data Word**. Parity checking is a fundamental technique in digital communication for error detection to ensure data integrity.

The project moves from boolean optimization to transistor-level CMOS implementation, culminating in a physical layout designed and simulated using the **Microwind** VLSI CAD tool. The performance is evaluated across different technology nodes (120nm, 180nm, 350nm) by measuring rise and fall times.

## 👥 Author
* **Neel Patel** (22BEC076)
* **Department:** Electronics & Communication Engineering
* **Institute:** Institute of Technology, Nirma University
* **Course:** VLSI Design (3EC601CC24)

---

## 🛠 Tools & Technologies

<p align="left">
  <a href="#" target="_blank">
    <img src="https://img.shields.io/badge/DSCH-Schematic-blue?style=flat-square" alt="DSCH"/>
  </a>
  <a href="#" target="_blank">
    <img src="https://img.shields.io/badge/Microwind-Layout_&_Sim-teal?style=flat-square" alt="Microwind"/>
  </a>
  <a href="#" target="_blank">
    <img src="https://img.shields.io/badge/CMOS-Logic-orange?style=flat-square" alt="CMOS"/>
  </a>
</p>

| Category | Details |
| :--- | :--- |
| **Software** | Microwind, DSCH (Digital Schematic) |
| **Logic Family** | CMOS (Complementary Metal-Oxide-Semiconductor) |
| **Tech Nodes** | 120nm, 180nm, 350nm |
| **Input Specs** | 3-Bit Data Word (A, B, C) + 1 Parity Bit (P) |

---

## ⚙ Design & Logic

### Boolean Optimization
The optimized boolean equation for the **Even Parity Checker** is derived as follows:

$$P_{EC} = (A \oplus B) \oplus (C \oplus P)$$

Where:
* `A, B, C` represent the 3-bit message.
* `P` represents the received parity bit.
* `PEC` is the Parity Error Check output.

### Truth Table (Even Parity)
| A | B | C | P | PEC (Output) |
|:-:|:-:|:-:|:-:|:---:|
| 0 | 0 | 0 | 0 | **0** |
| 0 | 0 | 0 | 1 | **1** |
| 0 | 1 | 0 | 1 | **0** |
| 1 | 1 | 1 | 0 | **1** |
| 1 | 1 | 1 | 1 | **0** |
*(Refer to full report for complete truth table)*

### 📸 Schematics & Stick Diagrams

The design follows a hierarchical approach:
1.  **Gate Level:** XOR gate implementation.
2.  **Transistor Level:** CMOS construction using PMOS pull-up and NMOS pull-down networks.
3.  **Stick Diagram:** Euler path optimization for layout.

<div align="center"> 
  <img width="600" alt="CMOS Schematic" src="path/to/your/transistor_schematic_image.png" />
  <br>
  <em>Fig 1: Transistor Level CMOS Circuit</em>
</div>

<div align="center"> 
  <img width="600" alt="Stick Diagram" src="path/to/your/stick_diagram_image.png" />
  <br>
  <em>Fig 2: Stick Diagram Representation</em>
</div>

---

## 🔌 Layout & Simulation

The physical layout was drafted in **Microwind** with manual routing to optimize area and capacitance.

<div align="center"> 
  <img width="800" alt="Microwind Layout" src="path/to/your/microwind_layout_image.png" />
  <br>
  <em>Fig 3: Final Layout in Microwind (120nm)</em>
</div>

### Waveform Analysis
The simulation validates the logic by toggling inputs A, B, C, and P and observing the `Odd_Parity` and `Even_Parity` output nodes.

<div align="center"> 
  <img width="800" alt="Simulation Waveforms" src="path/to/your/waveform_image.png" />
</div>

---

## 📊 Performance Analysis

We compared the propagation delays (Rise Time `$t_{plh}$` and Fall Time `$t_{phl}$`) across three different technology nodes.

| Technology Node | $t_{phl}$ (Fall Time) | $t_{plh}$ (Rise Time) | Parity Mode |
| :--- | :--- | :--- | :--- |
| **120nm** | 41 ps | 49 ps | Odd Parity |
| **120nm** | 49 ps | 41 ps | Even Parity |
| **180nm** | 83 ps | 135 ps | Odd Parity |
| **180nm** | 135 ps | 83 ps | Even Parity |
| **350nm** | 50 ps | 184 ps | Odd Parity |
| **350nm** | 184 ps | 50 ps | Even Parity |

> **Observation:** As the channel length decreases (scaling down from 350nm to 120nm), the switching speed increases significantly, resulting in lower propagation delays.

---

## 📝 Conclusion
This project successfully demonstrated the VLSI design flow for an error detection circuit. The parity checker was verified for both even and odd parity modes. The simulation results in Microwind confirm the functionality and highlight the impact of technology scaling on circuit performance (speed).

## 📚 References
1. CMOS Digital Integrated Circuits by Sung-Mo Kang.
2. Nirma University Laboratory Resources.
