# High-Side MOSFET Solid-State Switch PCB Prototype

A discrete power electronics hardware layout and component validation project implementing a logic-level triggered, high-side power switching architecture for high-current DC loads, featuring strict front/back electrical layer isolation.

## Project Overview & Technical Scope
The goal of this design was to transition from mechanical switching arrays to solid-state load isolation topologies using KiCad EDA. The circuit employs a logic-level P-channel MOSFET paired with a small-signal N-channel MOSFET driver network to switch a high-current 12V DC barrel jack output line safely. This structure allows low-voltage, low-current microcontroller pins (3.3V/5V logic) to isolate and actuate heavy inductive or resistive DC peripheral loads without exposing control logic to high-power rails.

## Core Engineering Objectives
* **Double-Sided Power & Signal Isolation Layout:** Implemented a strict component separation strategy to optimize noise immunity and thermal performance. **High-current power delivery components are populated exclusively on the front layer**, while **low-power control signal elements are placed entirely on the back layer**. This distinct physical partitioning prevents high-current return loops from corrupting weak control logic lines.
* **Semiconductor Parametric Optimization:** Evaluated manufacturer datasheets to analyze critical transfer characteristics, balancing Gate-Source Threshold Voltage ($V_{GS(th)}$) and Static Drain-Source On-Resistance ($R_{DS(on)}$) curves. This ensures full channel saturation from weak logic inputs to prevent thermal runaway.
* **Over-Engineering & Safety Margin Analysis:** Practiced safe industrial power design methods by picking power components whose Drain-Source Voltage ($V_{DS}$) and continuous drain current ($I_D$) limits exceed maximum load requirements by a strict 2x engineering safety factor.
* **Thermal Architecture & Packaging Design:** Studied the thermal layout profiles of Through-Hole Technology (THT) vs. Surface Mount Devices (SMD). Addressed thermal dissipation constraints by comparing bulky TO-220 packages against compact DPAK/SOIC-8 footprints that utilize dedicated PCB copper pours as thermal heatsinks.
* **Geometric Power Trace Layout:** Configured high-current routing lines with widened trace cross-sections to minimize parasitic resistance and voltage drops across primary power delivery tracks.

## Project Status: Design Phase (Digital Prototype)
*Note: This project is maintained digitally within KiCad to validate custom design rules, trace geometries, and schematic-to-board footprint synchronizations prior to physical prototyping loops.*

---

## Design Visual Previews

### 1. Circuit Schematic Diagram
*Capture of the high-side power distribution configuration, small-signal control isolation layer, and input/output DC terminals.*
<img width="560" height="584" alt="High Side MOSFET Driver(Power Switch) Schematics " src="https://github.com/user-attachments/assets/04b2fac9-9685-4b0b-a8a2-e243f53c0040" />



### 2. 3D Visual Board Render (Front View - Power Stage)
*Complete 3D structural render showing power footprint clearances, structural trace widths, and heavy-current hardware components populated on the primary layer.*<img width="479" height="454" alt="High Side MOSFET Driver(Power Switch) 3D Viewer Front" src="https://github.com/user-attachments/assets/a4ce5a22-8d28-4ae7-bb05-034c9e3718fe" />


### 3. 3D Visual Board Render (Back View - Low Power Logic Stage)
*Complete 3D structural render showing the reverse side of the board dedicated entirely to clean, low-current logic and control signal traces.*<img width="480" height="453" alt="High Side MOSFET Driver(Power Switch) 3D Viewer Back" src="https://github.com/user-attachments/assets/dfa689c1-eb09-4639-8977-adb73eb3b9ea" />
