# 02: Systolic array for matrix multiply

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🟡 Intermediate | Stage 2 · Track A | 2–3 weeks | Verilator, cocotb, NumPy, Yosys (optional: SCALE-Sim) |

## Goal

Build a parameterised N×N weight-stationary systolic array that multiplies INT8 matrices, the same structure at the core of Google's TPU. Then measure how well it is used.

## What you'll learn

- How systolic arrays move data and why they need so little memory bandwidth
- Weight-stationary dataflow and input skewing
- Tiling a large matrix multiply onto a fixed-size array
- Measuring utilisation and comparing it with an analytical model

## Prerequisites

- [Project 01](01-int8-mac-unit.md), or an equivalent MAC unit
- Roadmap [Stage 1](../README.md#stage-1-ml-foundations-for-hardware-engineers) milestones

## Specification

- Parameter `N` (array size): must work for at least N = 4 and N = 8.
- Processing elements (PEs) built from your INT8 MAC; weights are loaded into the PEs before compute.
- Inputs stream in from one edge (skewed in time); partial sums flow through the array.
- Result: `C = A × B` with INT8 inputs and INT32 outputs.
- A simple control interface: load weights, start, done.

## Suggested steps

1. Draw the array on paper for N = 2 and trace the first few cycles by hand.
2. Write a cycle-level Python model of the array (not just `A @ B`) so you can debug timing.
3. Implement a single PE, then a 2×2 array, and match the Python model cycle by cycle.
4. Generalise to N×N with generate loops; add input skew and output de-skew logic.
5. Add a tiling driver in the testbench to multiply matrices larger than N×N (e.g. 64×64 on an 8×8 array).
6. Count cycles and compute utilisation (useful MACs ÷ (N² × cycles)).

## Done when

- [ ] Random INT8 matrices of several sizes match `numpy` exactly for N = 4 and N = 8.
- [ ] A 64×64 multiply runs on an 8×8 array through tiling.
- [ ] You report cycles and utilisation, and explain where the idle cycles come from (fill and drain).
- [ ] Your README includes a diagram of the dataflow and a table of N vs. area (Yosys) vs. cycles.

## Stretch goals

- Add double-buffered weight registers so the next tile's weights load during compute.
- Implement an output-stationary variant and compare utilisation.
- Compare your cycle counts with [SCALE-Sim](https://github.com/scalesim-project/SCALE-Sim) for the same configuration.

## Resources

- [In-Datacenter Performance Analysis of a Tensor Processing Unit](https://arxiv.org/abs/1704.04760)
- [Efficient Processing of Deep Neural Networks: A Tutorial and Survey](https://arxiv.org/abs/1703.09039)
- [Gemmini](https://github.com/ucb-bar/gemmini) as a reference implementation
- More in [resources/accelerator-design.md](../resources/accelerator-design.md)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
