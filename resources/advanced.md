# Building end to end and advanced topics

Resources for [Stage 3](../README.md#stage-3-build-end-to-end) and [Stage 4](../README.md#stage-4-advanced-and-research-topics).

## Stage 3: Build end to end

### SoC and FPGA frameworks

- 🛠️ [Chipyard](https://github.com/ucb-bar/chipyard) - Berkeley's SoC framework combining RISC-V cores, Gemmini and simulation.
- 🛠️ [LiteX](https://github.com/enjoy-digital/litex) - Build FPGA SoCs quickly in Python; easy to add your own accelerator.
- 🛠️ [F4PGA](https://github.com/chipsalliance/f4pga) - Fully open-source FPGA toolchain.
- 🛠️ [Edalize](https://github.com/olofk/edalize) - One Python interface to many EDA tools; handy for scripting flows.
- 🛠️ [PYNQ](https://www.pynq.io/) - Python control of FPGA accelerators on Zynq boards for quick demos and measurements.

### Taking a design to silicon

- 🛠️ [Tiny Tapeout](https://tinytapeout.com/) - Get a small design manufactured on a real chip at low cost.
- 🛠️ [OpenROAD](https://openroad.org/) - Open-source RTL-to-GDSII flow.
- 🛠️ [OpenLane](https://github.com/The-OpenROAD-Project/OpenLane) - Automated ASIC flow built on OpenROAD.

## Stage 4: Advanced and research topics

### LLM inference hardware

- 📄 [FlashAttention](https://arxiv.org/abs/2205.14135) (Dao et al.) - IO-aware attention; a lesson in designing for the memory hierarchy.
- 📄 [Efficient Memory Management for Large Language Model Serving with PagedAttention](https://arxiv.org/abs/2309.06180) (Kwon et al.) - How the KV cache dominates LLM serving.
- 📄 [LLM Inference Unveiled: Survey and Roofline Model Insights](https://arxiv.org/abs/2402.16363) (Yuan et al.) - Uses the roofline model to explain where LLM inference time goes; a natural next step after Stage 1.
- 📄 [FlashAttention-3](https://arxiv.org/abs/2407.08608) (Shah et al.) - How attention is tuned to a specific GPU generation (Hopper); shows hardware features driving kernel design.
- 📄 [Fast Inference from Transformers via Speculative Decoding](https://arxiv.org/abs/2211.17192) (Leviathan et al.) - Trading extra compute for fewer memory-bound decode steps.
- 📄 [DistServe](https://arxiv.org/abs/2401.09670) (Zhong et al.) and [Splitwise](https://arxiv.org/abs/2311.18677) (Patel et al.) - Running prefill and decode on separate hardware because they stress it so differently.
- 📄 [AWQ](https://arxiv.org/abs/2306.00978) (Lin et al.) and [GPTQ](https://arxiv.org/abs/2210.17323) (Frantar et al.) - The two most used weight-only quantization methods for LLMs.
- 📄 [TPU v4: An Optically Reconfigurable Supercomputer for Machine Learning](https://arxiv.org/abs/2304.01433) (Jouppi et al., ISCA 2023) - A modern non-GPU accelerator at scale, to compare with TPU v1.
- 🎓 [How to Scale Your Model](https://jax-ml.github.io/scaling-book/) (Google DeepMind) - Free book on rooflines, memory and parallelism for LLMs on TPUs and GPUs.
- 🛠️ [vLLM](https://github.com/vllm-project/vllm) - The most widely used open-source LLM serving engine; read it to learn continuous batching and paged KV cache.
- 🛠️ [SGLang](https://github.com/sgl-project/sglang) - Another fast serving engine, with prefix caching (RadixAttention).
- 🛠️ [Triton](https://github.com/triton-lang/triton) - Write GPU kernels in Python; the easiest way to feel memory bandwidth limits first hand.
- 📄 [Inference infra learning roadmap](https://x.com/suraj_sharma14/status/2123748198225449037) (Suraj Sharma, X post, 2026) - A 12-stage checklist of the software side of LLM inference, from serving engines to kernels and distributed serving. Useful to see what the systems people around your chip will be working on.

### Low-precision formats

- 📄 [FP8 Formats for Deep Learning](https://arxiv.org/abs/2209.05433) (Micikevicius et al.) - The E4M3 and E5M2 formats now common in accelerators.
- 📄 [Microscaling Data Formats for Deep Learning](https://arxiv.org/abs/2310.10537) (Rouhani et al.) - Shared-scale MX formats for very low precision.

### ML for EDA

- 📄 [Chip Placement with Deep Reinforcement Learning](https://arxiv.org/abs/2004.10746) (Mirhoseini et al.) - Reinforcement learning for macro placement, and the start of a lively debate.

### Where to follow research

- **Architecture:** ISCA, MICRO, HPCA, ASPLOS
- **Design automation:** DAC, ICCAD, DATE
- **FPGA:** FPGA (ACM/SIGDA International Symposium), FCCM, FPL
- **ML systems:** MLSys
- 🛠️ [arXiv cs.AR](https://arxiv.org/list/cs.AR/recent) - New hardware architecture preprints every day.

## Related lists

Other curated lists worth starring:

- [FPGA-ASIC-Roadmap](https://github.com/m3y54m/FPGA-ASIC-Roadmap) - Beginner path into FPGA and ASIC engineering.
- [awesome-electronics](https://github.com/kitspace/awesome-electronics) - Resources for electronic engineers and hobbyists.
- [awesome-open-hardware](https://github.com/delftopenhardware/awesome-open-hardware) - Tools and guides for open-source hardware projects.
- [Neural-Networks-on-Silicon](https://github.com/fengbintu/Neural-Networks-on-Silicon) - Accelerator papers by conference.
- [AI-Chip](https://github.com/basicmi/AI-Chip) - AI chip landscape.
