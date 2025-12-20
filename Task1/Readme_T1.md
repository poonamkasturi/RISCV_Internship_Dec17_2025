## TASK 1 - Environmenrt setup and RISC-V reference validation
___
### ENVIRONMENT
Github Codespace(LINUX)
___

**Step 1: Set up GitHub Codespace**

First set up the official Codespace environment using the reference repository below:

https://github.com/vsdip/vsd-riscv2

**Instructions**

Fork the vsd-riscv2 repository to your GitHub account.

Launch a GitHub Codespace from your fork.

Ensure the Codespace builds successfully and opens without errors.

This Codespace provides a known-good base environment that will be used throughout the internship
___
**CODESPACE was successfully launched**
___
____
**Step 2: TOOL INSTALLATION VERIFICATION**

root@codespaces-41c123:/workspaces/vsd-riscv2# **riscv64-unknown-elf-gcc --version**

riscv64-unknown-elf-gcc (SiFive GCC 8.3.0-2019.08.0) **8.3.0**

root@codespaces-41c123:/workspaces/vsd-riscv2# **spike --version**

**spike: unrecognized option --version**

Try **'spike --help'** for more information.

root@codespaces-41c123:/workspaces/vsd-riscv2# **spike --help**

Spike RISC-V ISA Simulator **1.1.1-dev**

root@codespaces-41c123:/workspaces/vsd-riscv2# **iverilog -V**

Icarus Verilog version **11.0 (stable)** ()
___

### RISC-V REFERENCE PROGRAM

**Verify RISC-V Reference Flow**
```
Repository: vsd-risc-v2
Program Path: samples/
The reference program was successfully compiled and excuted using gcc and spike on codespace as well as noVNC
Output: "Sum from 1 to 9 is 45"
```

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture1.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture2a.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture3a.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture4a.png)


**Step 3: Clone and Run VSDFPGA Labs**
### VSDFPGA LABS
```
Repository: vsdfpga_labs
Lab: basicRISCV Firmware build
Generated riscv_logo.bram.hex successfully
Bitstream generation and FPGA flashing skipped
```

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture5.png)


Steps followed for logo generation
```
#riscv64-unknown-elf-gcc -o riscv_logo.o riscv_logo.c
#spike pk riscv_logo.o
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

