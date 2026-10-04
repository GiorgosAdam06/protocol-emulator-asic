# Protocol Emulator ASIC

Open-source programmable protocol emulator ASIC being developed for the Jane Street Protocol Emulator ASIC Competition.

The goal is to design a small programmable hardware engine that can implement digital communication protocols through precise GPIO control and timing, rather than using separate fixed-function peripherals for each protocol.

## Team

- Giorgos Adam
- Armen Sam
- Martin Aguilera
- Maximillian Weinstein

## Project Goals

The initial protocol targets are:

- UART
- SPI
- I2C

The design will eventually use a programmable architecture that can execute protocol behavior in firmware or microcode, allowing the same hardware to support multiple communication protocols.

Possible future goals include additional protocols, protocol bridging, debugging capabilities, and other functionality enabled by the architecture.

## Target

- **Process:** IHP 130 nm CMOS5L
- **Platform:** Tiny Tapeout
- **Allocation:** 6x4 tiles
- **HDL:** SystemVerilog
- **Competition deadline:** January 18, 2027

## Current Status

The project is currently in the architecture exploration and learning phase.

Current work includes:

- Studying UART, SPI, and I2C
- Developing small protocol RTL projects
- Exploring possible processor and instruction-set architectures
- Setting up the Tiny Tapeout ASIC flow
- Developing the verification strategy

The RTL currently present in the repository is based on the Tiny Tapeout template and does **not yet represent the final protocol-emulator architecture**.

## Repository Structure

```text
src/        RTL source files
test/       Simulation and verification
docs/       Project documentation
info.yaml   Tiny Tapeout project configuration