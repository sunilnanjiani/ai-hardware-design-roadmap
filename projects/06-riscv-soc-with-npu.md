# 06: RISC-V SoC with a custom NPU

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🔴 Advanced | Stage 3 · Tracks A + B | 1–2 months | NEORV32 or LiteX, RISC-V GCC toolchain, Verilator, cocotb; optional FPGA board |

## Goal

Integrate your accelerator into a RISC-V system-on-chip as a memory-mapped neural processing unit (NPU), drive it from C code, and verify the whole system.

## What you'll learn

- Hardware/software co-design: registers, interrupts and a minimal driver
- Bus interfaces (AXI4-Lite or Wishbone) and DMA
- System-level verification: firmware-driven tests on top of block-level tests
- Measuring speed-up of an accelerator over pure software

## Prerequisites

- [Project 02](02-systolic-array-matmul.md) (or [Project 05](05-cnn-accelerator-end-to-end.md) for the full network)
- Basic C and comfort with a RISC-V toolchain

## Specification

- Host: a RISC-V soft core SoC, for example [NEORV32](https://github.com/stnolting/neorv32) or a [LiteX](https://github.com/enjoy-digital/litex) SoC.
- NPU: your matrix-multiply array behind a memory-mapped register interface (control, status, addresses, sizes) on the SoC bus.
- Data movement: start with CPU-driven copies; then add a simple DMA that reads operands from and writes results to system memory.
- Software: a small C driver (`npu_matmul(A, B, C, M, N, K)`) and a benchmark comparing it with a plain C loop.

## Suggested steps

1. Bring up the SoC in simulation and run "hello world" firmware.
2. Wrap your array with a bus slave interface; verify the registers with a cocotb testbench.
3. Integrate into the SoC and write firmware that runs one small multiply via CPU copies.
4. Add DMA and an interrupt or done flag; update the driver.
5. Write firmware self-tests that compare NPU results with a software reference in C.
6. Benchmark matrix sizes from 8×8 up to 64×64 against the plain C loop.

## Done when

- [ ] Firmware self-tests pass in simulation for several matrix sizes.
- [ ] Block-level (cocotb) and system-level (firmware) tests are both automated.
- [ ] A speed-up table: NPU vs. software for each matrix size, including the data-movement cost.
- [ ] A write-up with the SoC block diagram, the register map and the driver API.

## Stretch goals

- Run the whole SoC on an FPGA board and benchmark on hardware.
- Run a small CNN (from Project 05) from C on the SoC.
- Add custom RISC-V instructions instead of memory-mapped registers and compare the two approaches.

## Resources

- [NEORV32](https://github.com/stnolting/neorv32), [LiteX](https://github.com/enjoy-digital/litex), [Chipyard](https://github.com/ucb-bar/chipyard)
- [Gemmini](https://github.com/ucb-bar/gemmini) as an example of an accelerator integrated with RISC-V
- More in [resources/advanced.md](../resources/advanced.md)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
