# Simulink-Modeling
MATLAB/Simulink models and test results for a 142S4P battery pack, featuring a 15-second 50A pulse and rest cycle to evaluate voltage drop
# ASURT Powertrain Task: 142S4P Battery Pack Simulation

**Applicant:** Zeina Soliman  
**Sub-team:** Powertrain  

## Overview
This repository contains the digital twin simulation of a 142S4P battery accumulator designed for the ASURT Formula Student Powertrain technical task. The model evaluates the voltage response and internal resistance characteristics of the pack under a simulated 50A discharge stress test using MATLAB and Simulink.

## Pack Specifications
* **Cell Type:** Molicel P45B
* **Configuration:** 142 Series, 4 Parallel (142S4P)
* **Model Resolution:** Lumped (Module/Pack level evaluation)
* **Thermal & Balancing:** Disabled for this specific baseline test

## Test Parameters (Pulse Discharge)
The simulation accurately maps the pack's voltage sag and chemical relaxation phases:
1. **Initial Rest (0-2s):** Establishes the starting Open Circuit Voltage (OCV) at approximately 583V.
2. **Discharge Pulse (2s-17s):** A 50A continuous current draw for exactly 15 seconds, demonstrating the immediate Ohmic drop and polarization slope.
3. **Relaxation Phase (17s-75s):** The load is removed (0A), capturing the voltage recovery curve back toward its resting state.

## Repository Contents
* `142S4P_Molicel P45B.mat`: The exported battery pack parameters generated via MATLAB Battery Builder.
* `SimulinkModel_PulseTest.slx`: The main Simulink circuit model (exported for backward compatibility).

## How to Run
1. Load the `The .mat file 142S4P_Molicel P45B.mat` file into the MATLAB workspace.
2. Open `SimulinkModel_PulseTest.slx` in Simulink.
3. Run the simulation (Stop Time: 80.0s) and open the Scope block to view the voltage response curve.
