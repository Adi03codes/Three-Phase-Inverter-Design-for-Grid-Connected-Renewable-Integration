# Three-Phase-Inverter-Design-for-Grid-Connected-Renewable-Integration




## Project Overview

This project focuses on designing and simulating a three-phase inverter intended for grid-connected renewable energy systems such as solar PV or wind turbines. The inverter converts DC power from renewable sources into AC power synchronized with the grid, enabling efficient and stable integration of renewable energy into the electrical grid.

The design emphasizes:
- Efficient power conversion with minimal harmonic distortion,
- Stable synchronization with grid voltage and frequency,
- Protection mechanisms for fault conditions,
- Control strategies such as Pulse Width Modulation (PWM) for output regulation.

## Table of Contents
- [Background](#background)
- [Objectives](#objectives)
- [System Architecture](#system-architecture)
- [Key Features](#key-features)
- [Design Parameters](#design-parameters)
- [Simulation Setup](#simulation-setup)
- [Results and Analysis](#results-and-analysis)
- [Technologies Used](#technologies-used)
- [Usage Instructions](#usage-instructions)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Background

Renewable energy sources like solar and wind are inherently DC power sources or variable frequency AC sources. Integrating these into the conventional AC grid requires power electronics converters, particularly inverters that produce high-quality AC waveforms synchronized with the grid. This project simulates a three-phase inverter topology widely used in grid-tied renewable applications, focusing on efficiency and power quality.

---

## Objectives

- Design a three-phase inverter that converts DC input to a balanced three-phase AC output.
- Implement sinusoidal Pulse Width Modulation (SPWM) to control output voltage and frequency.
- Simulate grid synchronization and fault response.
- Analyze output voltage quality, Total Harmonic Distortion (THD), and inverter efficiency.
- Provide a modular and extensible model for further research and real-world application.

---

## System Architecture

The inverter system consists of:

| Component                | Description                                             |
|--------------------------|---------------------------------------------------------|
| DC Source                | Simulated renewable energy source providing DC voltage |
| Three-Phase Inverter     | Power electronics circuit with six IGBTs/MOSFETs        |
| SPWM Controller          | Generates PWM signals to drive inverter switches        |
| Grid Interface           | Three-phase AC grid model for synchronization            |
| Filters                 | LC filters to smooth output voltage and reduce harmonics |

---

## Key Features

- **Three-Phase Inverter Topology:** Uses a standard six-switch full-bridge inverter design.
- **Sinusoidal PWM Control:** Generates modulated signals for controlling the inverter switches with precise timing.
- **Grid Synchronization:** Phase Locked Loop (PLL) based synchronization with grid voltage and frequency.
- **Fault Handling:** Simulation of overcurrent and short circuit conditions to verify protection response.
- **Output Filtering:** LC filters designed to minimize high-frequency switching noise and harmonics.
- **Performance Metrics:** Real-time calculation and visualization of output voltage, current, power factor, and THD.

---

## Design Parameters

| Parameter             | Value          | Unit          | Description                             |
|-----------------------|----------------|---------------|---------------------------------------|
| DC Input Voltage       | 600            | V             | Nominal DC voltage from renewable source |
| Output Line Voltage    | 230            | V (RMS)       | Line-to-neutral RMS voltage            |
| Switching Frequency    | 10             | kHz           | PWM switching frequency                 |
| Output Frequency       | 50             | Hz            | Grid frequency                         |
| Inductance (L)         | 5              | mH            | Output filter inductance               |
| Capacitance (C)        | 20             | μF            | Output filter capacitance              |
| Load                   | 10             | Ω             | Resistive load connected to output    |

---

## Simulation Setup

The inverter is modeled and simulated in MATLAB/Simulink using the following approach:

1. **Modeling the Power Stage:** Six IGBTs/MOSFETs configured in a three-phase full-bridge arrangement.
2. **SPWM Generation:** Using a reference sine wave and a high-frequency carrier triangle wave.
3. **Grid Model:** Three-phase balanced AC source with parameters matching the local grid.
4. **Control System:** PLL for grid synchronization and PI controllers for voltage regulation.
5. **Fault Injection:** Introducing short circuit and overcurrent conditions to test protection.
6. **Data Logging:** Voltage, current, power, and harmonic distortion metrics logged for analysis.

---

## Results and Analysis

- The inverter successfully produces a balanced three-phase output synchronized with the grid.
- THD of output voltage maintained below 5%, meeting IEEE standards for grid connection.
- Protective measures engage correctly during simulated faults, isolating the inverter.
- Efficiency of power conversion measured above 95% under nominal conditions.

### Sample Output Waveform

![Output Voltage Waveform](docs/output_waveform.png)

### Harmonic Spectrum

![Harmonic Spectrum](docs/harmonic_spectrum.png)

---

## Technologies Used

- MATLAB
- Simulink
- Power Electronics Toolbox
- Signal Processing Toolbox

---

## Usage Instructions

1. Clone the repository:

```bash
git clone https://github.com/yourusername/three-phase-inverter-grid.git
cd three-phase-inverter-grid
