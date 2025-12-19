###
**Step 1: Set up GitHub Codespace**

First set up the official Codespace environment using the reference repository below:
https://github.com/vsdip/vsd-riscv2

**Instructions**

Fork the vsd-riscv2 repository to your GitHub account.
Launch a GitHub Codespace from your fork.
Ensure the Codespace builds successfully and opens without errors.
This Codespace provides a known-good base environment that will be used throughout the internship

**Step 2: Verify RISC-V Reference Flow**

root@codespaces-41c123:/workspaces/vsd-riscv2# riscv64-unknown-elf-gcc --version

riscv64-unknown-elf-gcc (SiFive GCC 8.3.0-2019.08.0) 8.3.0

root@codespaces-41c123:/workspaces/vsd-riscv2# spike --version

spike: unrecognized option --version

Try 'spike --help' for more information.

root@codespaces-41c123:/workspaces/vsd-riscv2# spike --help

Spike RISC-V ISA Simulator 1.1.1-dev

root@codespaces-41c123:/workspaces/vsd-riscv2# iverilog -V

Icarus Verilog version 11.0 (stable) ()

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture1.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture2.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture3.png)

![](https://github.com/poonamkasturi/RISCV_Internship_Dec17_2025/blob/main/Task1/screenshots/Picture4.png)


**Step 3: Clone and Run VSDFPGA Labs**

