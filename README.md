# Computer-Processor-Simulator

## Overview
This project is a Java-based simulator for a basic CPU and its components, focusing on binary math operations, memory access, assembly language parsing, and caching mechanisms. The project is designed to simulate the core functionalities of a processor using binary operations and memory handling.

## Project Structure
The project is divided into multiple components, each focusing on specific aspects of processor simulation. Key classes include:

1. **Bit and Word Classes**: Represent single bits and 32-bit words, respectively. These are fundamental for bitwise operations across the processor simulation.
2. **ALU (Arithmetic Logic Unit)**: Performs basic arithmetic (addition, subtraction, multiplication) and bitwise operations (AND, OR, XOR, NOT).
3. **MainMemory**: Simulates DRAM memory access with methods to read and write values and load data.
4. **Processor**: Implements a basic processing loop for instruction fetch, decode, execute, and store operations.
5. **InstructionCache and L2Cache**: Manage fast-access memory to reduce access times and simulate cache hits/misses.
6. **Assembler and Lexer**: Parse and interpret assembly language instructions, generating appropriate tokens for processing.

## Components and Features

### Bit and Word Classes
- **Bit Class**: Represents a binary digit and supports basic operations (`set`, `toggle`, `clear`, `and`, `or`, `xor`, `not`).
- **Word Class**: A collection of 32 bits, allowing for binary arithmetic and bitwise operations, along with conversions between signed and unsigned representations.

### ALU (Arithmetic Logic Unit)
- **Operations**: Supports addition, subtraction, multiplication, and bitwise operations via `doOperation()`. Operations are chosen by specific bit patterns defined in the input.

### Memory Management
- **MainMemory**: Manages an array of 1024 Word objects, simulating memory addresses with support for loading binary data from a file.
- **Cache Layers**: `InstructionCache` and `L2Cache` layers reduce the cost of frequent memory access, tracking cycles for cache hits and misses.

### Processor
- Implements a loop for fetching, decoding, executing, and storing instructions, simulating a basic processor’s functionality.
- **Registers**: Utilizes 32 general-purpose registers (R0-R31) along with special registers such as `PC` (Program Counter) and `SP` (Stack Pointer).

### Assembly Language Parsing
- **Lexer**: Tokenizes assembly code into meaningful tokens, including registers, numbers, and instructions.
- **Parser**: Parses tokens into executable instructions, generating output in a format compatible with `MainMemory`.

### Instruction Set Architecture (ISA)
The project uses an instruction set with various formats for operation codes (opcodes), including:
- **3 Register**: Operations involving three registers.
- **2 Register**: Operations involving two registers and an immediate value.
- **Dest Only**: Operations with a single destination register.
- **No Register**: Operations that only require an immediate value.
