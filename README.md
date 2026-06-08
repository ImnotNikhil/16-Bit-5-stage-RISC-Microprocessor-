# 16-Bit 5-Stage Pipelined RISC Microprocessor

A custom 16-bit 5-stage pipelined RISC microprocessor designed in Verilog HDL featuring a 32-instruction ISA, forwarding unit, hazard detection logic, centralized stall control, multi-cycle shift-add multiplication, restoring division, and complete RTL-to-GDSII ASIC implementation using Cadence Genus and Innovus in 90 nm technology.

## Overview

This project presents the design, verification, and ASIC implementation of a custom 16-bit pipelined RISC processor. The processor follows a classic 5-stage pipeline architecture consisting of:

* Instruction Fetch (IF)
* Instruction Decode (ID)
* Execute (EX)
* Memory Access (MEM)
* Write Back (WB)

The design supports arithmetic, logical, memory, control-flow, stack, and multi-cycle arithmetic operations while incorporating forwarding, hazard detection, and stall-control mechanisms to ensure correct instruction execution.

## Key Features

### Processor Architecture

* 16-bit custom RISC architecture
* 5-stage instruction pipeline
* 32-instruction ISA
* Program Counter (PC)
* Register File
* Instruction Memory
* Data Memory
* Branch and Control Logic

### ALU Features

* Addition
* Subtraction
* AND
* OR
* XOR
* CMP
* Rotate Right (ROR)
* NZCV Flag Generation

### Pipeline Control

* Forwarding Unit
* Hazard Detection Unit
* Branch Flush Logic
* Load-Use Hazard Handling
* Centralized Stall Controller

### Multi-Cycle Arithmetic Units

* Shift-Add Multiplier
* Restoring Divider
* Busy/Done Handshake Logic
* Pipeline Freeze Support

### ASIC Implementation

* RTL Design
* Functional Verification
* Logic Synthesis
* Floorplanning
* Placement
* Clock Tree Synthesis (CTS)
* Routing
* Static Timing Analysis (STA)
* DRC Verification
* LVS Verification
* GDSII Generation

## Processor Architecture

*Overall 16-bit 5-stage pipelined processor architecture.*

## Stall-Control Mechanism

The processor incorporates a centralized stall-control unit to manage long-latency multiplication and division operations.

When a multiplication or division operation is active:

1. Busy signal is asserted.
2. Global stall signal is generated.
3. Program Counter is frozen.
4. Pipeline registers are frozen.
5. Arithmetic unit completes execution.
6. Stall condition is removed.
7. Normal execution resumes.

This mechanism prevents dependent instructions from accessing incomplete arithmetic results.

## RTL Verification

The complete processor was verified using Verilog testbenches covering:

* Arithmetic Operations
* Logical Operations
* Memory Operations
* Branch Instructions
* Hazard Scenarios
* Forwarding Validation
* Multiplication Operations
* Division Operations
* Stall-Control Verification

## Results

| Parameter            | Value           |
| -------------------- | --------------- |
| Architecture         | 16-bit RISC     |
| Pipeline Stages      | 5               |
| ISA Support          | 32 Instructions |
| Technology Node      | 90 nm           |
| Operating Frequency  | ~100 MHz        |
| Core Area            | ~146k µm²       |
| Power Consumption    | ~4.68 mW        |
| Placement Density    | ~66.45%         |
| Post-CTS Worst Slack | +5.23 ns        |

## Tools Used

Xilinx Vivado, Cadence Genus, Cadence Innovus

### Design & Verification

* Verilog HDL
* Xilinx Vivado

### ASIC Flow

* Cadence Genus
* Cadence Innovus

### Technology

* 90 nm CMOS Standard Cell Library

## Author

**Nikhil Jindal**

Electronics and Communication Engineering
Chitkara University

LinkedIn: www.linkedin.com/in/nikhil-jindal-074a34218
