# NASSCOM RISC-V Based MYTH Program
This repository documents the work done during the RISC-V based MYTH program conducted by NASSCOM from 16/04/25 to 25/04/25.

## Day1: Introduction to RISC-V ISA and GNU compiler toolchain
In this section compiling and executing C-language as well as assembly language programs was introduced. Additionally, the usage of a debugger to efficiently debug program errors was also taught.

A summary of the commads used in this section along with their brief explanation is provided below:<br />
For compiling the program using a gcc compiler,<br />
`gcc <c-program-file-name>`<br />
To execute the compiled program,<br />
`./a.out`

When using a riscv compiler to compile a program several flags can be used for instance here we have used the -O1 flag,<br />
`riscv64-unknown-elf-gcc -O1 -mabi=lp64 march=rv64i -o  <c-program-file-name.o> <c-program-file-name.c>`<br />
While here we have used the -Ofast flag to compile a program,<br />
`riscv64-unknown-elf-gcc -Ofast -mabi=lp64 march=rv64i -o  <c-program-file-name.o> <c-program-file-name.c>`<br />
To execute the compiled program,<br />
`spike pk <c-program-file-name.o>`<br />

We can also see the assembly code of the C-program after the compilation by running,<br />
`riscv64-unknown-elf-objdump -d <c-program-file-name.o>`<br />
To see a more concise form of the assembly program generated,<br />
`riscv64-unknown-elf-objdump -d <c-program-file-name.o> | less`<br />
`spike -d pk <c-program-file-name.o>`<br />

The relevant files for this module can be found in the /Day1 directory.

## Day2: Introduction to ABI and basic verification flow
In this assignment we have seen that a function called inside a C-program can actually be implemented in assembly language in a separate file. In order to compile correctly we need to run,<br />
`riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o  <c-program-file-name.o> <c-program-file-name.c> <assembly-file-name.S>`<br />
To execute the compiled program,<br />
`spike pk <c-program-file-name.o>`<br />

The relevant files for this module can be found in the /Day2 directory.

## Day3: Digital Logic with TL-Verilog and Makerchip
For this assignment we had to develop a calculator that also has the features of both memory and recall in addition to performing the operations of sum, diffference, product and quotient. The schematic of the calclator designed is shown below. To refer to the code one can either access this link [calculator code](https://www.makerchip.com/sandbox/0DkfBhR9B/048hBnP#) or the file calc_lab.tlv in the /Day3 directory.

![alt text](images/calc_diagram.png)


## Day4: Basic RISC-V CPU micro-architecture
The task here was to implement a basic version of a subset of the instructions comprising the RISC-V ISA. The schematic of the RISC-V CPU microarchitecture designed is shown below. To refer to the code one can either access this link [basic riscv code](https://www.makerchip.com/sandbox/0XDfnh720/0X6hXRo) or the file basic_riscv.tlv in the /Day4 directory.

![alt text](images/riscv_unpipelined.png)


[comment]: <> (## Day5: Complete Pipelined RISC-V CPU micro-architecture)