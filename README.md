# 220V AC to 10.2V DC Regulated Power Supply

## Overview
This repository contains the schematic, simulation files, and custom PCB layout for a regulated DC power supply. The circuit converts 220V AC mains electricity into a stable 10.2V DC output. This project was developed as part of the ECE211s Electronic Circuits I course at Ain Shams University. 

The design utilizes a Zener shunt regulation strategy and was fully simulated in Proteus 8 prior to hardware implementation.

## Circuit Architecture
The power supply is built using four primary functional blocks:
* **Step-Down Transformer:** A TRAN-2P2S transformer steps the 220V AC mains down to 12Vpk AC.
* **Bridge Rectifier:** Four 1N4007 diodes are arranged to provide full-wave rectification of the AC signal.
* **Capacitive Filter:** A 1000 µF electrolytic capacitor smooths the rectified waveform to minimize peak-to-peak ripple.
* **Shunt Regulator:** A 1N4740A Zener diode is used to clamp the output voltage to a stable 10.2V DC.

## Hardware Specifications & Performance

| Parameter | Value |
| :--- | :--- |
| **Input Voltage** | Mains 220V AC |
| **Target Output Voltage** | 10.2V DC |
| **Maximum Output Current** | 10mA |
| **Measured No-Load Voltage** | 10.66V |
| **Measured Max-Load Voltage** | 10.72V |
| **Load Regulation** | 0.69% |

## Bill of Materials (BOM)

| Component | Part Number | Quantity | Role |
| :--- | :--- | :--- | :--- |
| Transformer | TRAN-2P2S | 1 | Steps down mains AC voltage |
| Rectifier Diodes | 1N4007 | 4 | Bridge rectifier |
| Smoothing Capacitor | EC1000/25 V (1000 µF) | 1 | Smoothing filter |
| Zener Diode | 1N4740A (10 V) | 1 | Shunt regulator |
| Resistor (1 kΩ) | CF1/4W-102J | 1 | Load resistor |
| Resistor (100 Ω) | CF1/4W-101J | 1 | Current limiting |
| Resistor (3.9 kΩ) | CF1/4W-392J | 1 | LED current limiting |
| Indicator LED | LED-3MM-R (Red) | 1 | Power indicator |

## Repository Contents
* `Proteus_Simulation/`: Contains the `.pdsprj` source files for the circuit simulation.
* `PCB_Files/`: Contains the layout files and Gerbers for the custom PCB.
* `Docs/`: Contains the detailed hand analysis for component sizing, including filter capacitance and Zener series resistor calculations.
* `Images/`: Simulation waveforms, PCB layout renders, and photos of the final soldered board under testing.

## Testing & Validation
The circuit was validated using a digital multimeter under different load conditions. A 1 kΩ load resistor was used to emulate the maximum 10mA current draw. The physical implementation successfully demonstrated a load regulation of 0.69%.
