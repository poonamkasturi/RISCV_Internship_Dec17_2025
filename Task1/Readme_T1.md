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

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture2.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture3.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture4.png)


**Step 3: Clone and Run VSDFPGA Labs**
### VSDFPGA LABS
```
Repository: vsdfpga_labs
Lab: basicRISCV Firmware build
Generated riscv_logo.bram.hex successfully
Bitstream generation and FPGA flashing skipped
```

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture5.png)

