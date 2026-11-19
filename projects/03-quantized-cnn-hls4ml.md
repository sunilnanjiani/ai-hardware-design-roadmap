# 03: Quantized CNN on FPGA with hls4ml

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🟡 Intermediate | Stage 2 · Track C | 2–3 weeks | PyTorch or Keras, QKeras or Brevitas, hls4ml, an HLS tool for synthesis reports |

## Goal

Take a small CNN from training to an FPGA implementation, and measure how quantization trades accuracy for hardware resources and latency.

## What you'll learn

- Post-training quantization (PTQ) vs. quantization-aware training (QAT)
- How bit width drives FPGA resources (DSPs, LUTs, BRAM) and latency
- How a model-to-hardware flow works, and where it needs your help
- Presenting trade-offs as a clear table or Pareto plot

## Prerequisites

- Roadmap [Stage 1](../README.md#stage-1-ml-foundations-for-hardware-engineers): you can train a small CNN in PyTorch or Keras
- Basic idea of what HLS does

## Specification

- Dataset: MNIST or Fashion-MNIST (small enough to fit on modest FPGAs).
- Model: a small CNN (two conv layers and one dense layer is plenty).
- Variants to compare: float baseline, PTQ INT8, QAT at 8, 6 and 4 bits.
- For each variant, report: accuracy, estimated latency, and FPGA resources from the HLS synthesis report.

## Suggested steps

1. Train the float baseline and record accuracy.
2. Follow the [hls4ml tutorial](https://github.com/fastmachinelearning/hls4ml-tutorial) end to end once with its own example.
3. Convert your float model with hls4ml and check that the C simulation matches the framework's predictions.
4. Apply PTQ, then retrain with QAT (QKeras or Brevitas) at several bit widths.
5. Synthesise each variant and collect resource and latency numbers.
6. Plot accuracy against resources and pick the variant you would ship.

## Done when

- [ ] At least four variants with accuracy, latency and resource numbers in one table.
- [ ] hls4ml's simulated output matches the framework's output for the chosen variant.
- [ ] A plot of accuracy vs. resource use, with your chosen design point marked and justified.
- [ ] You can explain why QAT holds accuracy better than PTQ at low bit widths.

## Stretch goals

- Try FINN with Brevitas for the same model and compare the two flows.
- Prune the model and measure whether resource use actually drops.
- Run the design on a real board with [PYNQ](https://www.pynq.io/) and measure real latency.

## Resources

- [hls4ml](https://github.com/fastmachinelearning/hls4ml), [QKeras](https://github.com/google/qkeras), [Brevitas](https://github.com/Xilinx/brevitas)
- [A White Paper on Neural Network Quantization](https://arxiv.org/abs/2106.08295)
- More in [resources/hardware-aware-ml.md](../resources/hardware-aware-ml.md)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
