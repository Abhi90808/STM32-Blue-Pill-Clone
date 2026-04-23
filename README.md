# STM32 Blue Pill Clone

A custom recreation of the popular STM32F103C8T6 "Blue Pill" ARM Cortex-M3 development board, designed in KiCad 8 with improved layout, better decoupling, and optional USB support.

---

## Features
- STM32F103C8T6 ARM Cortex-M3 MCU @ up to 72MHz
- Onboard 8MHz crystal + 32.768kHz RTC crystal
- USB Full-Speed port (12Mbit/s)
- SWD debug/programming header
- Boot0/Boot1 jumpers
- All 37 GPIO pins broken out
- 3.3V LDO onboard
- Improved power decoupling vs original Blue Pill

## Specifications

| Parameter | Value |
|-----------|-------|
| MCU | STM32F103C8T6 |
| Core | ARM Cortex-M3 |
| Clock Speed | Up to 72MHz |
| Operating Voltage | 3.3V |
| USB Input | 5V via Micro USB |
| Flash Memory | 64KB |
| SRAM | 20KB |
| GPIO Pins | 37 |
| ADC Channels | 10 (12-bit) |
| PCB Layers | 2 |
| Designed With | KiCad 8 |

## Project Structure

```
├── Schematic/       # KiCad schematic (.kicad_sch, PDF)
├── PCB/             # PCB layout (.kicad_pcb, .kicad_pro)
├── Gerbers/         # Fabrication files
├── BOM/             # Bill of materials (CSV)
├── 3D/              # 3D model (.step)
└── Images/          # PCB renders and schematic screenshots
```

## How It Works

The STM32F103C8T6 is clocked by an 8MHz external crystal, which the internal PLL multiplies to 72MHz. Programming is done via the SWD header using ST-Link V2. The USB port supports DFU bootloader flashing without an external programmer.

## Programming Options

| Method | Tool |
|--------|------|
| SWD | ST-Link V2 + STM32CubeIDE / OpenOCD |
| USB DFU | STM32CubeProgrammer (Boot0 = 1) |
| Serial | UART1 + STM32CubeProgrammer (Boot0 = 1) |
| Arduino | Arduino IDE + STM32duino core |

## Bill of Materials (Summary)

| Component | Value | Qty |
|-----------|-------|-----|
| MCU | STM32F103C8T6 | 1 |
| Crystal | 8MHz | 1 |
| RTC Crystal | 32.768kHz | 1 |
| LDO Regulator | AMS1117-3.3V | 1 |
| USB Connector | Micro-B | 1 |
| SWD Header | 4-pin, 2.54mm | 1 |
| Decoupling Caps | 100nF | 8 |

## Fabrication

Gerber files are in `/Gerbers`, ready for JLCPCB, PCBWay, or similar.

## License

This project is licensed under the [CERN Open Hardware Licence Version 2 - Strongly Reciprocal (CERN OHL-S v2)](https://ohwr.org/cern_ohl_s_v2.txt).

## Author

**Abhi90808** — [GitHub Profile](https://github.com/Abhi90808)
