## TASK 1 - Environmenrt setup and RISC-V reference validation
___
### ENVIRONMENT
Github Codespace(LINUX)
___

**Step 1: Set up GitHub Codespace**

official Codespace environment was set using the reference repository below:
https://github.com/vsdip/vsd-riscv2

**Instructions Followed**

```
1. Fork the vsd-riscv2 repository to your GitHub account.
2. Launch a GitHub Codespace from your fork.
3. Ensure the Codespace builds successfully and opens without errors.
```
This Codespace provides a known-good base environment that will be used throughout the internship
___
**CODESPACE was successfully launched**
___
____
**Step 2: TOOL INSTALLATION VERIFICATION**

**riscv64 version verification - riscv cross compiler**
```
root@codespaces-41c123:/workspaces/vsd-riscv2# riscv64-unknown-elf-gcc --version
riscv64-unknown-elf-gcc (SiFive GCC 8.3.0-2019.08.0) 8.3.0
```
**spike version verification - riscv ISA simulator**
```
root@codespaces-41c123:/workspaces/vsd-riscv2# spike --version
spike: unrecognized option --version
Try 'spike --help' for more information.
```
#### spike does not supports --version command
so --help command used to verify spike installation

```
root@codespaces-41c123:/workspaces/vsd-riscv2# spike --help
Spike RISC-V ISA Simulator 1.1.1-dev
```
**iverilog version verification - for RTL simulation and synthesis**
```
root@codespaces-41c123:/workspaces/vsd-riscv2# iverilog -V
Icarus Verilog version 11.0 (stable) ()
```
___

## RISC-V REFERENCE PROGRAM

**STEP 3 : Verify RISC-V Reference Flow**
```
Repository: vsd-risc-v2
Program Path: samples/
The reference program was successfully compiled and excuted using gcc and spike on codespace as well as noVNC
Output: "Sum from 1 to 9 is 45"
```
### Compare the output from a general gcc, GNU compiler and riscv compiler to verify the functionality of riscv compiler

```
from Desktop folder go to the folder where sum1ton.c file is
workspaces/vsd-riscv2/samples
```
#### step 3a
**execute the file using gcc command**
```
root@codespaces-41c123:/workspaces/vsd-riscv2/samples# gcc sum1ton.c
root@codespaces-41c123:/workspaces/vsd-riscv2/samples# ./a.out     TO CHECK THE OUTPUT
```
![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture1.png)

#### step 3b
**execute the same file in noVNC terminal using gcc command**

   from ports tab install the noVNC session 
   
   and run the execution of the code in noVNC

```
root@codespaces-41c123:/workspaces/vsd-riscv2/samples# gcc sum1ton.c
root@codespaces-41c123:/workspaces/vsd-riscv2/samples# ./a.out     TO CHECK THE OUTPUT
```

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture2a.png)

#### step 3c
**execute the same file using the riscv compiler and spike to view the output in noVNC terminal**
```
root@codespaces-41c123:/workspaces/vsd-riscv2/samples# riscv64-unknown-elf-gcc -o sun1ton.0 sum1ton.c
root@codespaces-41c123:/workspaces/vsd-riscv2/samples# spike pk sum1ton.o
```
![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture3a.png)

**edited the sum1ton.c file for a different number (1 to 30)**
![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture4a.png)

## Clone and Run VSDFPGA Lab Session 
### VSDFPGA LABS
```
Repository: vsdfpga_labs
Lab: basicRISCV Firmware build
Generated riscv_logo.bram.hex successfully
Bitstream generation and FPGA flashing skipped
```

**step 4: Flash riscv logo**

Clone vsdfpga_labs repository inside the same Codespace in the terminal window.
```
root@codespaces-41c123:/workspaces/vsd-riscv2# git clone https://github.com/vsdip/vsdfpga_labs
```

**Objective**
Execute the basicRISCV lab:
Generated BRAM hex from firmware for riscv logo and display on terminal
No FPGA hardware tools were used.
the hex code has been seen in the output and logo generated

**commands used**
change the path to /vsdfpga_labs/basic_RISCV/firmware
make the hex file
```
root@codespaces-41c123:/workspaces/vsd-riscv2# cd ./vsdfpga_labs/basic_RISCV/firmware
root@codespaces-41c123:/workspaces/vsd-riscv2/vsdfpga_labs/basic_RISCV/firmware# make riscv_logo.bram.hex
```

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture5.png)


Steps followed for logo generation and view the output
```
root@codespaces-41c123:/workspaces/vsd-riscv2/vsdfpga_labs/basic_RISCV/firmware# riscv64-unknown-elf-gcc -o riscv_logo.o riscv_logo.c
root@codespaces-41c123:/workspaces/vsd-riscv2/vsdfpga_labs/basic_RISCV/firmware# spike pk riscv_logo.o
```
## Codespace Image
![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture6.png)

## noVNC Image
![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture7.png)

___
### Understanding Check (Mandatory)


1.	Where is the RISC-V program located in the vsd-riscv2 repository?
   
   The RISC-V application resides in the **samples** folder within the **vsd-riscv2** repository.
  	
2.	How is the program compiled and loaded into memory?

   The source code is cross-compiled using the **riscv64-unknown-elf-gcc** toolchain and executed through the **Spike** simulator with the **proxy kernel** (pk), which handles loading the ELF binary into memory.
   
3.	How does the RISC-V core access memory and memory-mapped IO?
   The core uses standard RISC-V **load/store** instructions over the system bus, with peripherals accessed through **memory-mapped IO** addresses.
  	
4.	Where would a new FPGA IP block logically integrate in this system?
   A new FPGA IP block would integrate as a **memory-mapped peripheral** connected to the **SoC interconnect**, allowing the RISC-V core to communicate with it through defined **address ranges**.

