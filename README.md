# Branchline-Coupler

## Overview

This project involves the design and simulation of a **3 GHz, 50Ω Branchline Coupler** using **Keysight ADS**. The goal is to implement a two-metal-layer PCB layout with **copper** as the conductive material and **FR4** as the dielectric substrate (εr = 4.6). The Branchline Coupler, also known as a quadrature hybrid, achieves equal power division with a **90° phase difference** between the through and coupled ports. The design flow incorporates impedance line calculations, schematic simulations, and full electromagnetic (EM) simulations.

---

## Design Methodology

The design process is divided into four main phases:

### 1. Linecalc Analysis

- **Defined substrate parameters**:
  - Dielectric Constant (εr) = 4.6  
  - Substrate Height (H) = 10 mils  
  - Conductor Thickness (T) = 17 µm  
  - Dielectric Loss Tangent (TanD) = 0.02  

- **Transmission Line Calculations**:
  - 50Ω Line Width: 457.08 µm  
  - 35.35Ω Line Width: Derived using 50/√2 Ω requirement  
  - λ/4 Line Length: 13.2781 mm for 3 GHz

### 2. Schematic Simulation

- Designed schematic using T-line components in ADS
- Simulated over 1.5 GHz to 4.5 GHz range
- **Key Results**:
  - S11, S22, S33, S44 < -25 dB (low reflection)
  - S21 and S31 ≈ -3.5 dB (minimal insertion loss)
  - S41 < -40 dB (high isolation)
  - Phase difference between S21 and S31 ≈ 90°

### 3. Piecewise EM Simulation

- Simulated each transmission line segment individually
- Used **Controlled Impedance Line Designer (CILD)** to refine dimensions
- Verified:
  - 50Ω line: negligible insertion loss, reflection < -35 dB
  - 35.35Ω and 50Ω λ/4 lines: phase shift ≈ 90°, low loss

### 4. Total EM Simulation

- Assembled and simulated full layout in ADS
- Connected all elements using auto-layout feature
- **Results**:
  - Return Loss: Very low (S11 < -25 dB)
  - Insertion Loss (S21/S31): ~ -3.5 dB
  - Isolation (S41): < -40 dB
  - Phase difference (S21/S31): 90°, as expected

---

## Result Analysis

| Parameter            | Result              |
|----------------------|---------------------|
| Operating Frequency  | 3 GHz               |
| Return Loss (S11)    | < -25 dB            |
| Insertion Loss       | ~ -3.5 dB           |
| Isolation (S41)      | < -40 dB            |
| Phase Difference     | 90° (S21 vs S31)    |

---

## Tools and Technologies Used

- **Software**: Keysight Advanced Design System (ADS)  
- **Substrate**: FR4 (εr = 4.6)  
- **Conductor**: Copper  
- **Simulation Types**: Linecalc, Schematic S-parameter, EM Layout

---

📝 The full methodology, simulation results, and figures are detailed in the attached report:  
📄 [`Branchline Coupler Report`](./Branchline%20Coupler%20Report_Nishanth%20Kiruthivasan.pdf)
