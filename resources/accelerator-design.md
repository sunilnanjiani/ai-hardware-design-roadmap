# Track A: AI accelerator design

Resources for [Track A](../README.md#track-a-ai-accelerator-design).

## Courses

- 🎓 [MIT 6.5930/1: Hardware Architecture for Deep Learning](http://csg.csail.mit.edu/6.5930/) - Sze and Emer's course on dataflows, sparsity and accelerator design, with lab exercises.
- 🎓 [Cornell ECE 5545: Machine Learning Hardware and Systems](https://abdelfattah-class.github.io/ece5545/) - Covers accelerators, quantization, compilers and FPGA ML.
- 🎓 [Advanced AI Hardware-Software Co-Design](https://github.com/arm-education/Advanced-AI-Hardware-Software-Co-Design) - Arm education course on quantization and on-device deployment.

## Books

- 📘 *Efficient Processing of Deep Neural Networks* (Sze, Chen, Yang & Emer) `(paid)` - The textbook for this track: dataflows, memory hierarchy, sparsity and evaluation.

## Key papers

- 📄 [In-Datacenter Performance Analysis of a Tensor Processing Unit](https://arxiv.org/abs/1704.04760) (Jouppi et al., ISCA 2017) - Google TPU v1: a large systolic array and why it wins on inference.
- 📄 [Eyeriss project](http://eyeriss.mit.edu/) - Row-stationary dataflow and energy-efficient CNN accelerator, with papers and tutorials.
- 📄 [Gemmini: Enabling Systematic Deep-Learning Architecture Evaluation](https://arxiv.org/abs/1911.09925) (Genc et al.) - An open, generator-based systolic accelerator integrated with RISC-V.

## Modelling and design-space exploration

- 🛠️ [Timeloop](https://github.com/NVlabs/timeloop) - Map workloads onto accelerator architectures and estimate performance.
- 🛠️ [Accelergy](https://github.com/Accelergy-Project/accelergy) - Energy estimation that pairs with Timeloop.
- 🧩 [Timeloop/Accelergy exercises](https://github.com/Accelergy-Project/timeloop-accelergy-exercises) - Guided exercises; the best way to learn both tools.
- 🛠️ [SCALE-Sim](https://github.com/scalesim-project/SCALE-Sim) - Cycle-accurate systolic array simulator for CNNs.
- 🛠️ [MAESTRO](https://github.com/maestro-project/maestro) - Analytical cost model for DNN dataflows.

## Open-source accelerators and reference designs

- 🧩 [Gemmini](https://github.com/ucb-bar/gemmini) - Berkeley's systolic array generator, part of Chipyard.
- 🧩 [NVDLA hardware](https://github.com/nvdla/hw) - NVIDIA's open deep learning accelerator RTL.
- 🧩 [Neural-Networks-on-Silicon](https://github.com/fengbintu/Neural-Networks-on-Silicon) - Curated list of accelerator papers from top architecture conferences.
- 🧩 [Embedded-Neural-Network](https://github.com/zssloth/Embedded-Neural-Network) - Papers on model compression and ASIC/FPGA ML accelerators.
- 🧩 [AI-Chip list](https://github.com/basicmi/AI-Chip) - Overview of commercial and research AI chips.

## High-level synthesis and FPGA platforms

- 🛠️ [Vitis Tutorials](https://github.com/Xilinx/Vitis-Tutorials) - AMD/Xilinx tutorials including Vitis HLS.
- 🛠️ [PandA-Bambu](https://github.com/ferrandi/PandA-bambu) - Open-source HLS framework.
- 🛠️ [PYNQ](https://www.pynq.io/) - Drive FPGA accelerators from Python and Jupyter on Zynq boards.
