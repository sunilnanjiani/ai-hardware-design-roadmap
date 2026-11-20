# Hands-on projects

Reading builds understanding; building builds skill. These project briefs turn the [roadmap](../README.md) into things you can make, measure and show.

Each brief gives you a goal, a specification, suggested steps and a **"done when"** checklist. They do **not** give you the solution: working it out is the point. All projects can be done with free, open-source tools in simulation; an FPGA board is a bonus, not a requirement.

## Project list

| # | Project | Level | Stage / track | Time |
|---|---|---|---|---|
| 01 | [Pipelined INT8 MAC unit](01-int8-mac-unit.md) | 🟢 Beginner | Stage 0 · Track A | 1 weekend |
| 02 | [Systolic array for matrix multiply](02-systolic-array-matmul.md) | 🟡 Intermediate | Stage 2 · Track A | 2–3 weeks |
| 03 | [Quantized CNN on FPGA with hls4ml](03-quantized-cnn-hls4ml.md) | 🟡 Intermediate | Stage 2 · Track C | 2–3 weeks |
| 04 | [ML-guided coverage closure](04-ml-guided-coverage-closure.md) | 🟡 Intermediate | Stage 2 · Track B | 2–3 weeks |
| 05 | [CNN accelerator, end to end](05-cnn-accelerator-end-to-end.md) | 🔴 Advanced | Stage 3 · Tracks A + C | 1–2 months |
| 06 | [RISC-V SoC with a custom NPU](06-riscv-soc-with-npu.md) | 🔴 Advanced | Stage 3 · Tracks A + B | 1–2 months |
| 07 | [Profile and speed up LLM inference on a GPU](07-llm-inference-profiling.md) | 🔴 Advanced | Stage 4 · Tracks A + C | 3–4 weeks |

Times assume a few hours per week alongside a job and are only a rough guide.

## Suggested paths

- **Accelerator designer:** 01 → 02 → 05 → 06
- **Verification engineer:** 01 → 04 → 02 → 06
- **Hardware-aware ML:** 01 → 03 → 05 → 07
- **LLM inference hardware:** 02 → 07, then revisit 05 with a transformer layer

## How to work on a project

1. Fork this repository (or start your own) and create a folder for your project.
2. Read the brief, then write down your own plan before you write any RTL.
3. Build in small steps, with a passing test at every step.
4. Measure: area, cycles, accuracy. Numbers turn a project into evidence.
5. Write a short README with a block diagram, results and lessons learned.

## Share your work

Finished a project? Open a pull request that adds a link to your repository under the brief's **Community solutions** section. Seeing different approaches is one of the best ways to learn.

## Add a project

Have an idea for a new project? Copy [TEMPLATE.md](TEMPLATE.md), fill it in and open a pull request. See [CONTRIBUTING.md](../CONTRIBUTING.md).
