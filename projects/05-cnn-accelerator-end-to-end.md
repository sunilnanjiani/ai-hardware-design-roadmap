# 05: CNN accelerator, end to end

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🔴 Advanced | Stage 3 · Tracks A + C | 1–2 months | PyTorch, Verilator, cocotb, Yosys; optional FPGA board and vendor tools |

## Goal

Run a complete quantized CNN on an accelerator you designed yourself, with results that match PyTorch bit for bit, and report honest performance numbers.

## What you'll learn

- Turning a trained model into integer-only arithmetic, including requantization
- Designing on-chip buffers and a simple controller around a compute array
- Mapping convolution layers onto hardware with tiling
- Building a golden model and debugging layer by layer
- End-to-end benchmarking against a CPU baseline

## Prerequisites

- [Project 02](02-systolic-array-matmul.md) (compute array)
- [Project 03](03-quantized-cnn-hls4ml.md) or equivalent quantization experience

## Specification

- Model: a LeNet-style CNN for MNIST or Fashion-MNIST, quantized to INT8 weights and activations.
- Accelerator:
  - Compute: your systolic array or a MAC array.
  - Buffers: on-chip memories for inputs, weights and outputs.
  - Post-processing: bias add, ReLU and requantization (scale and shift) in hardware.
  - Control: a sequencer or simple instruction stream that runs the network layer by layer.
- Golden model: a NumPy implementation of the integer-only network that matches the quantized PyTorch model.

## Suggested steps

1. Export the quantized model's integer weights, scales and zero points.
2. Write the integer-only NumPy golden model and check its accuracy against PyTorch on the test set.
3. Map one convolution layer onto your array (im2col or direct) and verify it alone.
4. Add post-processing and verify one full layer bit-exactly.
5. Add the sequencer and run the whole network; compare every layer's output with the golden model.
6. Measure cycles per inference, estimate throughput at a target clock, and compare with running the model on a CPU.

## Done when

- [ ] Every layer's output matches the golden model bit for bit.
- [ ] Classification accuracy on the full test set matches the quantized PyTorch model.
- [ ] You report cycles per inference, array utilisation per layer, and Yosys area (or FPGA resources).
- [ ] A write-up with a block diagram, results table and the three hardest bugs you fixed.

## Stretch goals

- Add double buffering so data movement overlaps with compute, and measure the speed-up.
- Run on a real FPGA board, streaming images in over UART or Ethernet.
- Model the same accelerator in [Timeloop](https://github.com/NVlabs/timeloop) and compare its estimates with your measurements.

## Resources

- [Quantization and Training of Neural Networks for Efficient Integer-Arithmetic-Only Inference](https://arxiv.org/abs/1712.05877)
- [Eyeriss project](http://eyeriss.mit.edu/) for buffer and dataflow ideas
- More in [resources/accelerator-design.md](../resources/accelerator-design.md) and [resources/advanced.md](../resources/advanced.md)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
