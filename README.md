# Breadboard Power Supply

A compact, dual-voltage linear power supply designed in **KiCad 9.0**, intended for electronics prototyping and breadboard applications.

The project converts a **12V DC input** into regulated **5V and approximately 3.3V outputs**, using LM7805 and LM317 linear voltage regulators.

The goal is to design a practical power supply while developing skills in electronic circuit design, schematic capture, PCB layout, and hardware prototyping.

## Project Overview

The power supply is designed to provide selectable voltage outputs for breadboards, microcontrollers, sensors, and other low-power electronic circuits.

### Main Features

- 12V DC input through a barrel jack connector
- ON/OFF power switch
- Fixed 5V output using the LM7805 voltage regulator
- Adjustable output targeting 3.3V using the LM317 voltage regulator
- LED power indicator
- Output voltage selection using jumper connectors
- Screw terminal connectors for external connections
- Common ground reference
- Through-hole components for easier assembly and soldering

## Technical Specifications

| Parameter | Description |
|---|---|
| Input voltage | 12V DC |
| Input connector | DC barrel jack |
| Voltage regulator 1 | LM7805 |
| Voltage regulator 2 | LM317 |
| Output voltage 1 | 5V DC |
| Output voltage 2 | ~3.3V DC (target) |
| Voltage selection | Jumper connectors |
| PCB design software | KiCad 9.0 |
| Assembly technology | Through-hole (THT) |
| Project status | In development |

**Note:** Maximum output current and thermal performance have not yet been validated.

## Circuit Design

The circuit is divided into three main sections.

### 1. Input and 5V Regulation

The circuit receives 12V DC through a barrel jack connector.

An ON/OFF switch controls the input power supplied to the voltage regulators.

The LM7805 converts the input voltage into a regulated 5V output.

Capacitors are used for input and output filtering, helping to reduce voltage fluctuations and electrical noise.

### 2. Adjustable 3.3V Regulation

The LM317 is an adjustable linear voltage regulator.

Its output voltage is determined by two external resistors according to:

\[
V_{out} \approx 1.25\left(1+\frac{R_2}{R_1}\right)
\]

The resistor values are selected to obtain an output close to 3.3V.

Unlike the LM7805, which provides a fixed voltage, the LM317 allows different output voltages by modifying the resistor network.

### 3. Output Voltage Selection

The circuit includes jumper connectors to select the desired output voltage.

The intended configuration is:

| Jumper Position | Output Voltage |
|---|---|
| Pins 2–3 | 5V |
| Pins 1–2 | 3.3V |

Each output selection network must remain electrically independent to prevent shorting the two regulated outputs together.

## Main Components

| Component | Description |
|---|---|
| LM7805 | Fixed 5V linear regulator |
| LM317 | Adjustable linear regulator |
| DC Barrel Jack | 12V power input |
| Slide Switch | Main power switch |
| LED | Power indicator |
| Resistors | Voltage adjustment and LED current limiting |
| Capacitors | Filtering and decoupling |
| Pin Headers | Output voltage selection |
| Screw Terminals | External power connections |

## Repository Structure

```text
breadboard-power-supply/
│
├── Breadboard_Power_Supply.kicad_pro
├── Breadboard_Power_Supply.kicad_sch
├── Breadboard_Power_Supply.kicad_pcb
├── .gitignore
└── README.md
```

### KiCad Files

- **`.kicad_pro`** — Project configuration
- **`.kicad_sch`** — Electrical schematic
- **`.kicad_pcb`** — PCB layout

## How to Open the Project

1. Install [KiCad](https://www.kicad.org/).
2. Clone this repository:

   ```bash
   git clone https://github.com/YOUR-USERNAME/breadboard-power-supply.git
   ```

3. Open `Breadboard_Power_Supply.kicad_pro`.
4. Use the Schematic Editor to inspect the circuit.
5. Use the PCB Editor to view or modify the board layout.

## Design Considerations

Because the project uses linear voltage regulators, part of the input power is dissipated as heat.

The approximate power dissipation is:

\[
P_D \approx (V_{in}-V_{out})I_{out}
\]

Thermal management, PCB layout, regulator operating limits, and component selection must be considered before hardware assembly.

The physical footprints must also be verified against the components selected for manufacturing.


## Tools

- **KiCad 9.0** — Schematic and PCB design
- **Git** — Version control
- **GitHub** — Project documentation and source management

## License

No license has been specified yet.

---

*Designed as a personal electronics engineering learning project.*
