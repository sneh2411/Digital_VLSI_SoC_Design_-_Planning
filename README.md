d# Digital_VLSI_SoC_Design_and_Planning
This repository is mainly to understand the basics of opensource EDA tools, OpenLANE and skywaterPDK. Here the focuus is on only the labs
# Table of Contents
- [Inception of open-source EDA OpenLANE and skywaterPDK](#inception-of-open-source-eda-openlane-and-skywaterpdk)
- [Good floorplan vs bad floorplan and introduction to library cells](#good-floorplan-vs-bad-floorplan-and-introduction-to-library-cells)

# Inception of open-source EDA OpenLANE and skywaterPDK 
Day 1 ::Learning Task:

The first objective of the workshop :
  1. Run the `picorv32a` design using Openlane flow
  2. Calculate flop ratio and its percentage of D Flip flop
Implementation of this task is presented in the form of screenshot

Basic commands in Linux are needed
`cd - change directory`
 `ls - list the files of directory`
`clear - clears the terminal`
`mkdir - make directory`
`pwd - present working directory`
`command --help - help for particular switches`

![Screenshot from 2024-04-12 10-55-51]

![Screenshot from 2024-04-12 10-56-16]

![Screenshot from 2024-04-12 11-05-17]

![Screenshot from 2024-04-12 11-27-01]

![Screenshot from 2024-04-12 11-50-15]

![Screenshot from 2024-04-12 11-43-23]
(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/c86271c4-c063-4413-bdce-3800fb7eec4d)
(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/bf0d45cd-a1fb-411a-9e0f-b02a34cebda5)
(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/c6905ddb-9148-4c3f-aa30-d24721674298)
![Screenshot from 2024-04-12 11-43-07](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/6848add4-ada0-4e2d-924f-da1335f08068)
![Screenshot from 2024-04-12 11-41-04](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/b063c8fc-eada-4ab4-8840-e0925dd528c1)
![Screenshot from 2024-04-12 11-40-21](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/fbe3a780-ef4d-499d-82b0-c3aab1f76475)
![Screenshot from 2024-04-12 11-37-17](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/f3b40450-db6c-47d2-8586-6920e2c7f690)
![Screenshot from 2024-04-12 11-36-07](https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/e550a6e9-a349-45bd-ae2b-6b83ff4bbf5c)

(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/c07032a2-8946-4057-905c-a676f1f25484)

(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/b235a5c3-d694-4916-ac49-52fcafa6303f)

(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/77b6a834-7f3e-4840-b0da-accb6698f705)




(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/59ede303-c58b-4c4c-9f0e-96bb48077d79)

(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/72f801bd-afcb-465d-a4b2-50875e301618)


(https://github.com/sneh2411/Digital_VLSI_SoC_Design_-_Planning/assets/46631767/a9481acf-21ff-4224-8571-f3cac1a3e884)
es/disassemble.png)
 ![disassemble](Images/disassemble.png)  
More details on Openlane can be obtained [here](https://github.com/efabless/openlane).

# Good floorplan vs bad floorplan and introduction to library cells

The GNU Toolchain is a set of programming tools in Linux systems that programmers can use to make and compile their code to produce a program or library. So, how the machine code which is understandable by processer is explained below.

  * Preprocessor - Process source code before compilation. Macro definition, file inclusion or any other directive if present then are preprocessed. 
  * Compiler - Takes the input provided by preprocessor and converts to assembly code.
  * Assembler - Takes the input provided by compiler and converts to relocatable machine code.
  * Linker - Takes the input provided by Assembler and converts to Absolute machine code.

Under the risc-v toolchain, 
  * To use the risc-v gcc compiler use the below command:

    `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o <object filename> <C filename>`

    More generic command with different options:

    `riscv64-unknown-elf-gcc <compiler option -O1 ; Ofast> <ABI specifier -lp64; -lp32; -ilp32> <architecture specifier -RV64 ; RV32> -o <object filename> <C      filename>`

    More details on compiler options can be obtained [here](https://www.sifive.com/blog/all-aboard-part-1-compiler-args)

  * To view assembly code use the below command,
    
    `riscv64-unknown-elf-objdump -d <object filename>`
    
  * To use SPIKE simualtor to run risc-v obj file use the below command,
  
    `spike pk <object filename>`
    
    To use SPIKE as debugger
    
    `spike -d pk <object Filename>` with degub command as `until pc 0 <pc of your choice>`

    To install complete risc-v toolchain locally on linux machine,
      1. [RISC-V GNU Toolchain](http://hdlexpress.com/RisKy1/How2/toolchain/toolchain.html)
      2. [RISC-V ISA SImulator - Spike](https://github.com/kunalg123/riscv_workshop_collaterals)
    
    Once done with installation add the PATH to .bashrc file for future use.

Test Case for the above commands [(Summation of 1 to 9)](codes/sum1ton.c),

  * Below image shows the disassembled file `sum1ton.o` with `main` function highlighted.

    ![disassemble](Images/disassemble.png)

  * To view the registers we can use command as `reg <core> <register name>`. 

    Below image shows how to debug the disassembled file using Spike simulator where a1,a2 register are checked before and after the instructions got executed.

    ![spike_debug](Images/spike_debug.png)

# Introduction to ABI

An Application Binary Interface is a set of rules enforced by the Operating System on a specific architecture. So, Linker converts relocatable machine code to absolute machine code via ABI interface specific to the architecture of machine.

So, it is system call interface used by the application program to access the registers specific to architecture. Overhere the architecture is RISC-V, so to access 32 registers of RISC-V below is the table which shows the calling convention (ABI name) given to registers for the application programmer to use.
[(Image source)](https://riscv.org/wp-content/uploads/2015/01/riscv-calling.pdf)

![calling_convention](Images/calling_convetion.png)

Test Case for ABI Call: [Summation of 1 to 9](codes/1to9_custom.c) through [assembly code](codes/load.S),

  * Below image shows the `main` function.

    ![main_ABI](Images/main_ABI.png)

  * Below image shows 2 sections from [load.S](codes/load.S) (one is load and other is loop).

    ![load_ABI](Images/load_ABI.png)

  * Below image shows the output of Summation from 1 to 9.

    ![compile_ABI](Images/compile_ABI.png)

# Digital Logic with TL-Verilog and Makerchip

[Makerchip](https://makerchip.com/) is a free online environment for developing high-quality integrated circuits. You can code, compile, simulate, and debug Verilog designs, all from your browser. Your code, block diagrams, and waveforms are tightly integrated.

All the examples shown below are done on Makerchip IDE using TL-verilog. Also there are other tutorials present on IDE which can be found [here](https://makerchip.com/sandbox/) under Tutorials section.

## [Combinational logic](codes/Combinational_Calculator.tlv)

Starting with basic example in combinational logic is an inverter. To write the logic of inverter using TL-verilog is `$out = ! $in;`. There is no need to declare `$out` and `$in` unlike Verilog. There is also no need to assign `$in`. Random stimulus is provided, and a warning is produced. 

Below is snapshot of Combinational Calculator.

![Combinational-Calculator](Images/Combinational_Calculator.png)

## [Sequential logic](codes/Sequential_Calculator.tlv)

Starting with basic example in sequential logic is Fibonacci Series with reset. To write the logic of Series using TL-Verilog is `$num[31:0] = $reset ? 1 : (>>1$num + >>2$num)`. This operator `>>?` is ahead of operator which will provide the value of that signal 1 cycle before and 2 cycle before respectively.

Below is snapshot of Sequential Calculator which remembers the last result, and uses it for the next calculation.

![Sequential-Calculator](Images/Sequential_Calculator.png)

## [Pipelined logic](codes/Cycle_Calculator.tlv)

Timing abstract powerful feature of TL-Verilog which converts a code into pipeline stages easily. Whole code under `|pipe` scope with stages defined as `@?`

Below is snapshot of 2-cycle calculator which clears the output alternatively and output of given inputs are observed at the next cycle.

![Cycle-Calculator](Images/Cycle_Calculator.png)

## [Validity](codes/Cycle_Calculator_Validity.tlv)

Validity is TL-verilog means signal indicates validity of transaction and described as "when" scope else it will work as don't care. Denoted as `?$valid`. Validity provides easier debug, cleaner design, better error checking, automated clock gating.

Below is snapshot of 2-cycle calculator with validity. 

![Cycle-Calculator-Validity](Images/Cycle_Calculator_validity.png)

# Basic RISC-V CPU micro-architecture

Designing the basic processor of 3 stages fetch, decode and execute based on RISC-V ISA.

## [Fetch](codes/Fetch.tlv)

* Program Counter (PC): Holds the address of next Instruction
* Instruction Memory (IM): Holds the set of instructions to be executed

During Fetch Stage, processor fetches the instruction from the IM pointed by address given by PC.

Below is snapshot from Makerchip IDE after performing the Fetch Stage.

![Fetch](Images/Fetch.png)

## [Decode](codes/Decode.tlv)

6 types of Instructions:
  * R-type - Register 
  * I-type - Immediate
  * S-type - Store
  * B-type - Branch (Conditional Jump)
  * U-type - Upper Immediate
  * J-type - Jump (Unconditional Jump)

Instruction Format includes Opcode, immediate value, source address, destination address. During Decode Stage, processor decodes the instruction based on instruction format and type of instruction.

Below is snapshot from Makerchip IDE after performing the Decode Stage.

![Decode](Images/Decode.png)

## [Register File Read and Write](codes/Register_File_Read.tlv)

Here the Register file is 2 read, 1 write means 2 read and 1 write operation can happen simultanously.

Inputs:
  * Read_Enable   - Enable signal to perform read operation
  * Read_Address1 - Address1 from where data has to be read 
  * Read_Address2 - Address2 from where data has to be read 
  * Write_Enable  - Enable signal to perform write operation
  * Write_Address - Address where data has to be written
  * Write_Data    - Data to be written at Write_Address

Outputs:
  * Read_Data1    - Data from Read_Address1
  * Read_Data2    - Data from Read_Address2

Below is snapshot from Makerchip IDE after performing the Register File Read followed by Register File Write.

![Register-File-Read](Images/Register_File_Read.png)

![Register-File-Write](Images/Register_File_Write.png)


## [Execute](codes/ALU.tlv)

During the Execute Stage, both the operands perform the operation based on Opcode.

Below is snapshot from Makerchip IDE after performing the Execute Stage.

![Execute](Images/ALU.png)

## [Control Logic](codes/Branches.tlv)

During Decode Stage, branch target address is calculated and fed into PC mux. Before Execute Stage, once the operands are ready branch condition is checked.

Below is snapshot from Makerchip IDE after including the control logic for branch instructions.

![Control-logic](Images/Control_Logic.png)

# Pipelined RISC-V CPU

Converting non-piepleined CPU to pipelined CPU using timing abstract feature of TL-Verilog. This allows easy retiming wihtout any risk of funcational bugs. More details reagrding Timing Abstract in TL-Verilog can be found in IEEE Paper ["Timing-Abstract Circuit Design in Transaction-Level Verilog" by Steven Hoover.](https://ieeexplore.ieee.org/document/8119264)

## [Pipelining the CPU](codes/Pipelining_the_CPU.tlv)

Pipelining the CPU with branches still having 3 cycle delay rest all instructions are pipelined. Pipelining the CPU in TL-Verilog can be done in following manner:
```
|<pipe-name>
    @<pipe stage>
       Instructions present in this stage
       
    @<pipe_stage>
       Instructions present in this stage
       
```

Below is snapshot of pipelined CPU with a test case of assembly program which does summation from 1 to 9 then stores to r10 of register file. In snapshot `r10 = 45`. Test case:
```
*passed = |cpu/xreg[10]>>5$value == (1+2+3+4+5+6+7+8+9);

```

![Pipelining_CPU](Images/Pipelining_CPU.png)

## [Load and store instructions and memory](codes/Load_Store.tlv)

Similar to branch, load will also have 3 cycle delay. So, added a Data Memory 1 write/read memory.

Inputs:
  * Read_Enable - Enable signal to perform read operation
  * Write_Enable - Enable signal to perform write operation
  * Address - Address specified whether to read/write from
  * Write_Data - Data to be written on Address (Store Instruction)

Output: 
  * Read_Data - Data to be read from Address (Load Instruction)

Added test case to check fucntionality of load/store. Stored the summation of 1 to 9 on address 4 of Data Memory and loaded that value from Data Memory to r17.
```
*passed = |cpu/xreg[17]>>5$value == (1+2+3+4+5+6+7+8+9);
```
Below is snapshot from Makerchip IDE after including load/store instructions.

![Load_Store](Images/Load_Store.png)

## [Completing the RISC-V CPU](codes/Final.tlv)

Added Jumps and completed Instruction Decode and ALU for all instruction present in RV32I base integer instruction set.

Below is final Snapshot of Complete Pipelined RISC-V CPU.

![Final](Images/Final.png)

# Acknowledgements
- [Kunal Ghosh](https://github.com/kunalg123), Co-founder, VSD Corp. Pvt. Ltd.
- [Steve Hoover](https://github.com/stevehoover), Founder, Redwood EDA
- [Shivam Potdar](https://github.com/shivampotdar), GSoC 2020 @fossi-foundation
- [Vineet Jain](https://github.com/vineetjain07), GSoC 2020 @fossi-foundation
