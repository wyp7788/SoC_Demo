# RISC-V cpu 

**RISC-V**(pronounced "risk-five") is a new instruction-set architecture(**ISA**) that was originally designed to support computer architecture research and education, but which we now hope will also become a standard free and open architecture for industry implementations.
My goals:
**Step by step to complete the design of the reduced instryction set CPU and FPGA impementation.**
This project include dirc below：
- risc-v knowledge
- Computer Architecture
- hardware
- script
- software
- spec

## My RISC cpu diagram

![datapath](https://raw.githubusercontent.com/wyp7788/blog_picture/main/blog_picture/datapath.jpg)

## Project Overview

- **hardware**
  - src
    - **z1top.v**: Top level module. The RISC_V CPU is instantiated here.
    - **riscv_core/Riscv151.v**: All of my CPU datapath and control should be contained in this file.
    - **io_circuits**: IO interface.
    - **EECS151.v**: EECS151-SP22 Library file of register and memory modules.
  - sim
    - **Riscv151_testbench.v** : Starting point for test CPU.  The testbench checks if  CPU can execute all the RV32I instructions (including CSR ones) correctly, and can handle some simple hazards. 
    - **assembly_testbench.v**: The testbench works with the software in software/assembly tests.
    - **isa_testbench.v**: The testbench works with the RISC-V ISA test suite in software/riscv-isa-tests.The testbench only runs one test at a time.
    - **echo_testbench.v**: The testbench works with the software in software/echo. The CPU reads a character sent from the serial rx line and echoes it back to the serial tx line.
    - **bios_testbench.v** : The testbench works with the BIOS program. The testbench checks if  CPU can execute the instructions stored in the BIOS memory. The testbench also emulates user input sent over the serial rx line, and checks the BIOS message output obtained from the serial tx line.
    - **software_testbench.v**: The testbench works with some software programs in software/.
    - **c_testbench.v** :The testbench works with the software in software/c test.

- **software**
