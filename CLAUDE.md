# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a KiCad electronic design project focused on SPICE simulation, named "spice-hello-world". It demonstrates basic SPICE simulation capabilities within KiCad using a simple half-wave rectifier circuit.

### Circuit Components
- Sinusoidal voltage source (1V, 1kHz)
- Diode for rectification
- 0.1μF capacitor for filtering
- 1kΩ resistor as load
- SPICE ground reference nodes

## Simulation Configurations

The project includes three simulation types configured in the workbook (.wbk):

1. **Operating Point Analysis**
   - Commands: `.op`, `.save all`, `.probe alli`, `.probe allp`
   - Purpose: Calculate DC voltage and current at each node

2. **AC Analysis**
   - Commands: `.ac dec 20 1 1G` (Frequency sweep from 1Hz to 1GHz)
   - Traces: Voltage gain and phase at diode anode and cathode

3. **Transient Analysis**
   - Commands: `.tran 1u 100m` (1μs step size over 100ms)
   - Traces: Voltage at diode anode and cathode

## Working with KiCad

### Opening the Project
To open the project in KiCad:
```
kicad spice-hello-world.kicad_pro
```

### Working with Schematic
To open the schematic directly:
```
eeschema spice-hello-world.kicad_sch
```

### Running Simulations
Simulations must be run from within KiCad's schematic editor:
1. Open the schematic
2. Launch the simulator tool
3. Select and run the desired simulation type

### SPICE Commands
Common SPICE commands that might be useful when modifying simulations:
- `.op` - Operating point analysis
- `.tran <step> <end_time>` - Transient analysis
- `.ac <type> <points> <start_f> <end_f>` - AC analysis
- `.save all` - Save all node voltages and branch currents
- `.probe` - Enable probing of specific values

## Project Images
The project includes the following image files:
- `images/schematic.png` - Circuit schematic diagram
- `images/ac_analysis.png` - Bode plot from AC analysis
- `images/transient_analysis.png` - Time domain plot from transient analysis

## Note on PCB Design
This project focuses on simulation rather than physical implementation. The PCB file exists but is empty.