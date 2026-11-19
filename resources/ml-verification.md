# Track B: ML-driven verification

Resources for [Track B](../README.md#track-b-ml-driven-verification).

This is the youngest of the three tracks, so expect this list to grow quickly. Contributions are especially welcome here.

## Verification foundations

- 🎓 [Verification Academy](https://verificationacademy.com/) - Siemens EDA's free courses on UVM, coverage and formal (free account required).
- 🎓 [ChipVerify](https://www.chipverify.com/) - Practical SystemVerilog and UVM tutorials with examples.
- 🧩 [SystemVerilogReference](https://github.com/VerificationExcellence/SystemVerilogReference) - Training labs and examples for SystemVerilog verification.

## Python-based verification

- 🛠️ [cocotb](https://github.com/cocotb/cocotb) - Python coroutine testbenches for any simulator. The base for this track's milestones.
- 🛠️ [pyuvm](https://github.com/pyuvm/pyuvm) - UVM implemented in Python on top of cocotb.
- 🛠️ [cocotb-coverage](https://github.com/mciepluc/cocotb-coverage) - Functional coverage and constrained-random stimulus for cocotb.
- 🛠️ [SymbiYosys](https://github.com/YosysHQ/sby) - Open-source formal verification front end; pair it with simulation.

## Stimulus generators and test suites

- 🧩 [riscv-dv](https://github.com/chipsalliance/riscv-dv) - Random instruction generator for RISC-V verification; a realistic target for ML-guided stimulus.
- 🧩 [sv-tests](https://github.com/chipsalliance/sv-tests) - SystemVerilog standard compliance tests across open-source tools.

## ML toolkits useful for verification

- 🛠️ [scikit-learn](https://scikit-learn.org/stable/) - Clustering and classification for failure triage and log analysis.
- 🛠️ [Optuna](https://optuna.org/) - Bayesian optimisation for tuning stimulus knobs towards coverage holes.
- 🛠️ [Gymnasium](https://gymnasium.farama.org/) - Standard API for reinforcement learning environments; wrap your testbench as an environment.

## Papers and benchmarks

- 📄 *Coverage Directed Test Generation for Functional Verification using Bayesian Networks* (Fine & Ziv, DAC 2003) - The classic paper on closing coverage with machine learning.
- 📄 [VerilogEval: Evaluating Large Language Models for Verilog Code Generation](https://arxiv.org/abs/2309.07544) (Liu et al.) - Benchmark for LLM-generated RTL; useful to understand where LLMs help and fail.
- 🧩 [RTLLM](https://github.com/hkust-zhiyao/RTLLM) - Open benchmark of design tasks for LLM-based RTL generation.
