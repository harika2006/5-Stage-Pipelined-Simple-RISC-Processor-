# 5-Stage Pipelined Simple RISC Processor (MIPS32)

This project implements a 5-stage pipelined RISC processor based on a subset of the MIPS32 instruction set using Verilog HDL. The processor simulates the five classical pipeline stages: Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write Back (WB).

## Features

- Implements key MIPS32 instructions including arithmetic, logical, memory access, and branch instructions.
- Follows a 5-stage pipeline architecture.
- Includes inter-stage pipeline registers (`IF_ID`, `ID_EX`, `EX_MEM`, `MEM_WB`).
- Behavioral Verilog modeling for easier understanding and simulation.
- Includes testbenches to validate functional correctness with various examples.

## Pipeline Stages

1. **IF (Instruction Fetch)** – Fetches instruction from memory and updates PC.
2. **ID (Instruction Decode)** – Decodes instruction, reads operands, sign-extends immediates.
3. **EX (Execute)** – Performs arithmetic or address calculations.
4. **MEM (Memory Access)** – Accesses memory for load/store, resolves branches.
5. **WB (Write Back)** – Writes results back to the register file.

## Instructions Supported

- **Arithmetic and Logic:** `ADD`, `SUB`, `MUL`, `AND`, `OR`, `SLT`
- **Immediate Arithmetic:** `ADDI`, `SUBI`, `SLTI`
- **Memory Access:** `LW`, `SW`
- **Control Flow:** `BEQZ`, `BNEQZ`, `J`
- **Special:** `HLT`

## How to Simulate

1. Use a Verilog simulator such as Icarus Verilog or ModelSim.
2. Compile and run the testbench:

```bash
iverilog -o mips_sim pipe_MIPS32.v test_mips32.v
vvp mips_sim

