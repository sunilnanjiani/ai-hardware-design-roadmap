# 01: Pipelined INT8 MAC unit

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🟢 Beginner | Stage 0 · Track A | 1 weekend | Verilator or Icarus, cocotb, Yosys |

## Goal

Build the multiply-accumulate (MAC) unit that sits at the heart of every AI accelerator, and verify it against a Python model. Every later project reuses it.

## What you'll learn

- Signed fixed-point arithmetic and choosing accumulator widths
- Pipelining a datapath and handling a valid signal through the pipeline
- Writing a cocotb testbench with a Python reference model
- Reading a Yosys synthesis report

## Prerequisites

- Basic Verilog or SystemVerilog
- Python basics

## Specification

- Inputs: `a` and `b`, signed 8-bit; `in_valid`; `clear` (reset the accumulator to zero).
- Output: `acc`, signed 32-bit accumulator; `out_valid`.
- Each valid input adds `a × b` to the accumulator.
- At least two pipeline stages (multiply, then accumulate), fully pipelined: one new input every cycle.
- Parameterise the input width (`DATA_W`) and the accumulator width (`ACC_W`).

## Suggested steps

1. Write a Python function that models the MAC, including the pipeline latency.
2. Write the RTL with a single register stage and get one directed test passing.
3. Add the second pipeline stage and the valid signal.
4. Add a randomised cocotb test: thousands of random signed inputs, random `clear` and gaps in `in_valid`, checked against the model.
5. Add corner cases: `-128 × -128`, long runs to approach overflow.
6. Synthesise with Yosys and note the cell count.

## Done when

- [ ] The randomised test passes for at least 10,000 inputs with gaps in `in_valid`.
- [ ] Corner cases are covered by directed tests.
- [ ] You can explain how many INT8 products a 32-bit accumulator can safely add in the worst case.
- [ ] The README of your project shows the block diagram, latency and Yosys cell count.

## Stretch goals

- Make the accumulator saturate instead of wrapping, controlled by a parameter.
- Build a 4-lane vector version (a dot-product unit) and compare its area with four separate MACs.
- Run it on an FPGA board and drive it from a simple UART or switches.

## Resources

- [cocotb](https://github.com/cocotb/cocotb) and [Verilator](https://www.veripool.org/verilator/)
- [HDLBits](https://hdlbits.01xz.net/) for Verilog practice
- More in [resources/foundations.md](../resources/foundations.md)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
