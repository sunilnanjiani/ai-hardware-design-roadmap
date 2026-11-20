# 07: Profile and speed up LLM inference on a GPU

| Level | Stage / track | Time | Tools |
|---|---|---|---|
| 🔴 Advanced | Stage 4 · Tracks A + C | 3–4 weeks | PyTorch, vLLM, Triton, Nsight Systems / Nsight Compute (any NVIDIA GPU, a cloud instance is fine) |

## Goal

Take a small open-weight large language model (LLM), measure where its inference time goes on a real GPU, then make it faster with quantization and one hand-written kernel. You will see in practice why LLM serving is a memory-bandwidth problem, which is the problem every new AI chip is trying to solve.

## What you'll learn

- The two phases of LLM inference: **prefill** (process the prompt, compute-bound) and **decode** (one token at a time, memory-bound)
- How the key-value (KV) cache grows with batch size and context length, and why it limits throughput
- Placing real workloads on a roofline using measured FLOPs and bytes moved
- What a serving engine (vLLM) does: continuous batching and paged KV cache
- How weight quantization (e.g. AWQ or FP8) trades accuracy for speed
- Writing and profiling a GPU kernel in Triton

## Prerequisites

- Roadmap [Stage 1](../README.md#stage-1-ml-foundations-for-hardware-engineers) milestones, especially the roofline milestone
- Basic Python and PyTorch; no CUDA experience needed

## Specification

- Model: an open-weight LLM of 0.5B to 3B parameters (e.g. a small Llama, Qwen or Phi model).
- Hardware: one NVIDIA GPU. Write down its peak FLOP/s and memory bandwidth from the datasheet.
- Metrics to report for every experiment:
  - Time to first token (TTFT) and inter-token latency (ITL)
  - Throughput in tokens per second at batch sizes 1, 8 and 32
  - GPU memory used by weights vs. KV cache
  - Accuracy or perplexity on a small evaluation set (for quantized variants)

## Suggested steps

1. Compute by hand the weight size, the KV cache size per token, and the FLOPs per token for your model. Predict whether decode at batch 1 is compute-bound or memory-bound.
2. Run the model in plain PyTorch (Hugging Face `transformers`) and measure TTFT, ITL and throughput.
3. Run the same model in vLLM and repeat the measurements. Explain the difference.
4. Profile one decode step with Nsight Systems and find the top kernels by time.
5. Place prefill and decode on your GPU's roofline using measured (not just predicted) numbers.
6. Quantize the weights (AWQ, GPTQ or FP8, whichever your GPU supports) and measure speed and accuracy again.
7. Write one Triton kernel (e.g. a fused RMSNorm, or a fused dequantize-and-matmul) and compare it with the PyTorch version in Nsight Compute.

## Done when

- [ ] Your hand calculations of weight size, KV cache size and FLOPs per token are within 20% of what you measure.
- [ ] You report TTFT, ITL and throughput for PyTorch vs. vLLM at three batch sizes.
- [ ] A roofline plot shows where prefill and decode sit, and you explain why decode is memory-bound.
- [ ] You report the speed and accuracy change from quantization.
- [ ] Your Triton kernel matches PyTorch's output and you report its achieved memory bandwidth as a percentage of peak.
- [ ] Your README ends with a section: "If I were designing an inference chip, this experiment tells me to..."

## Stretch goals

- Turn on speculative decoding in vLLM and measure when it helps and when it does not.
- Compare against SGLang or TensorRT-LLM on the same model.
- Run the same model on a non-NVIDIA target (a Google TPU through Colab or Kaggle, Apple silicon with MLX, or a CPU with llama.cpp) and compare tokens per second per watt.
- Re-read the TPU or Groq design choices and explain which of your bottlenecks they address.

## Resources

- [Efficient Memory Management for Large Language Model Serving with PagedAttention](https://arxiv.org/abs/2309.06180)
- [LLM Inference Unveiled: Survey and Roofline Model Insights](https://arxiv.org/abs/2402.16363)
- [How to Scale Your Model](https://jax-ml.github.io/scaling-book/) for roofline and memory calculations on accelerators
- [Triton](https://github.com/triton-lang/triton) tutorials
- More in [resources/advanced.md](../resources/advanced.md#llm-inference-hardware)

## Community solutions

_Finished this project? Add a link to your repository here with a pull request._
