# 19-bit CPU Design Project

A minimal, functional 19-bit computer system implemented using Logisim. This project explores the fundamental principles of computer architecture, focusing on the interaction between the CPU, memory, and control logic.

## 🚀 Features
- **19-bit Architecture**: Custom data width implemented across registers, buses, and the ALU.
- **Arithmetic Logic Unit (ALU)**: Supports core arithmetic and logical operations including Addition, Subtraction, AND, OR, XOR, and NAND.
- **Custom Instruction Set**: A minimal ISA designed for basic computation and control flow.
- **Multi-cycle Execution**: Implements a full fetch-decode-execute cycle managed by a central control unit.
- **Memory System**: Integrated main memory for storing both instructions and data.

## 🛠 Instruction Set Architecture (ISA)

The CPU supports the following operations:

| Instruction | Opcode | Description |
| :--- | :--- | :--- |
| `AND` | `0000` | Bitwise AND operation between registers |
| `ADD` | `0001` | Addition of two registers or register and immediate |
| `STO` | `0010` | Store register value into memory |
| `ISZ` | `0011` | Increment register and skip next instruction if zero |
| `BSB` | `0100` | Branch to subroutine (saves return address) |
| `BUN` | `0101` | Branch unconditionally |
| `HALT` | `0110` | Stop CPU execution |
| `LOAD` | `0111` | Load value from memory into register |
| `OR` | `1000` | Bitwise OR operation |
| `SUB` | `1001` | Subtraction of registers |
| `NAND` | `1010` | Bitwise NAND operation |
| `XOR` | `1011` | Bitwise XOR operation |

## 🏗 Architecture Overview

### ALU & Control
The system utilizes a 16-to-1 multiplexer for ALU control, decoding opcodes into specific ALU signals. Complex operations are handled via time-sequenced control signals in the control unit, coordinating the movement of data between the Accumulator (AC) and the Memory Buffer Register (MBR).

### Memory Mapping
The memory address is split to accommodate a 4-bit opcode in the MSB and a 6-bit address in the LSB, with the remaining bits handled as don't-cares.

## 📁 Project Structure
- `full_CPU_19_bit_multi_cycle.circ`: The complete integrated CPU system.
- `19-bit-ALU.circ`: The core arithmetic and logic unit.
- `control_unit.circ`: The timing and control logic.
- `memory.circ`: The main memory implementation.
- `Report.pdf`: Detailed technical documentation and design objectives.

## 💻 Simulation
The design was verified using Logisim simulation, testing various programs to ensure robustness in instruction execution and data flow.
