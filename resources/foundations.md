# Foundations

Resources for [Stage 0](../README.md#stage-0-hardware-foundations) and [Stage 1](../README.md#stage-1-ml-foundations-for-hardware-engineers).

## Stage 0: Hardware foundations

### Start here

- [FPGA-ASIC-Roadmap](https://github.com/m3y54m/FPGA-ASIC-Roadmap) - The complete beginner path into FPGA and ASIC engineering. If you are new to digital design, follow it first.

### Learn and practise

- 🎓 [HDLBits](https://hdlbits.01xz.net/) - Hundreds of small Verilog exercises checked in the browser. The fastest way to get fluent.
- 🎓 [Onur Mutlu Lectures](https://www.youtube.com/@OnurMutluLectures) - Full ETH Zurich courses on digital design and computer architecture, free on YouTube.
- 📘 *Digital Design and Computer Architecture, RISC-V Edition* (Harris & Harris) `(paid)` - Clear path from logic gates to a working RISC-V processor in HDL.
- 📘 *Computer Architecture: A Quantitative Approach* (Hennessy & Patterson) `(paid)` - The standard reference; its chapter on domain-specific architectures covers the TPU.
- 🧩 [Introduction to Computer Architecture Education Kit](https://github.com/arm-education/Introduction-to-Computer-Architecture-Education-Kit) - Arm's course with a 5-stage Verilog core and labs.
- 📄 [ZipCPU blog](https://zipcpu.com/) - Deep, practical articles on FPGA design, AXI and formal verification.
- 🛠️ [EDA Playground](https://www.edaplayground.com/) - Run Verilog, SystemVerilog and VHDL simulations in the browser, nothing to install.

### Open-source tools

- 🛠️ [Verilator](https://www.veripool.org/verilator/) - Fast open-source Verilog/SystemVerilog simulator.
- 🛠️ [Icarus Verilog](https://github.com/steveicarus/iverilog) - Simple event-driven Verilog simulator, great for learning.
- 🛠️ [cocotb](https://github.com/cocotb/cocotb) - Write testbenches in Python. Used throughout this roadmap.
- 🛠️ [Yosys](https://github.com/YosysHQ/yosys) - Open-source synthesis; see how your RTL maps to gates and LUTs.
- 🛠️ [Amaranth](https://github.com/amaranth-lang/amaranth) - Modern Python-based HDL and toolchain.
- 🛠️ [Chisel](https://www.chisel-lang.org/) - Scala-based hardware construction language used by Chipyard and Gemmini.

### Reference designs

- 🧩 [SERV](https://github.com/olofk/serv) - The tiny bit-serial RISC-V CPU; great for understanding a core end to end.
- 🧩 [darkriscv](https://github.com/darklife/darkriscv) - Compact, readable RISC-V core in Verilog.
- 🧩 [NEORV32](https://github.com/stnolting/neorv32) - Well-documented RISC-V microcontroller SoC; a good host for custom accelerators later.
- 🧩 [pulp-platform/axi](https://github.com/pulp-platform/axi) - Production-quality AXI SystemVerilog IP with verification infrastructure.
- 🧩 [basic_verilog](https://github.com/pConst/basic_verilog) - Collection of must-have Verilog/SystemVerilog building blocks (FIFOs, CDC and more).

## Stage 1: ML foundations for hardware engineers

### Learn the concepts

- 🎓 [3Blue1Brown: Neural Networks](https://www.3blue1brown.com/topics/neural-networks) - Visual intuition for neural networks, backpropagation and transformers.
- 🎓 [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) - Andrej Karpathy builds networks from scratch in code, up to a GPT.
- 🎓 [Practical Deep Learning for Coders](https://course.fast.ai/) - Hands-on, top-down course from fast.ai.
- 🎓 [CS231n course notes](https://cs231n.github.io/) - Stanford's notes on CNNs; excellent on convolution and layer shapes.
- 📘 [Dive into Deep Learning](https://d2l.ai/) - Free interactive book with runnable PyTorch code.
- 📘 [Deep Learning](https://www.deeplearningbook.org/) (Goodfellow, Bengio & Courville) - The classic textbook, free online.
- 📄 [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) - The clearest visual walkthrough of attention.
- 🎓 [Made With ML](https://github.com/GokuMohandas/Made-With-ML) - From ML fundamentals to production pipelines.

### Tools

- 🛠️ [PyTorch tutorials](https://pytorch.org/tutorials/) - Official tutorials; start with "Learn the Basics".
- 🛠️ [ONNX](https://onnx.ai/) - The open model format most hardware toolchains import.
- 🛠️ [Netron](https://netron.app/) - Visualise any model's layers, shapes and weights in the browser.

### Thinking like a hardware engineer about ML

- 📄 [Roofline: An Insightful Visual Performance Model for Multicore Architectures](https://doi.org/10.1145/1498765.1498785) (Williams, Waterman & Patterson, 2009) - The paper behind the roofline model used in the Stage 1 milestones.
- 📄 [Efficient Processing of Deep Neural Networks: A Tutorial and Survey](https://arxiv.org/abs/1703.09039) (Sze et al.) - Bridges ML and hardware: what networks compute and how hardware can do it efficiently.
