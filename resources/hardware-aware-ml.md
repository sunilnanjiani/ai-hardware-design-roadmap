# Track C: Hardware-aware ML

Resources for [Track C](../README.md#track-c-hardware-aware-ml).

## Courses and books

- 🎓 [MIT 6.5940: TinyML and Efficient AI Computing](https://efficientml.ai/) - Song Han's course on pruning, quantization, NAS and efficient LLMs, with labs.
- 📘 [Machine Learning Systems](https://mlsysbook.ai/) - Free open textbook from Harvard on building and deploying efficient ML systems.
- 🎓 [Machine Learning Compilation](https://mlc.ai/courses.html) - Tianqi Chen's course on how models get compiled down to hardware.
- 🎓 [AI on Arm](https://github.com/arm-education/AI-on-Arm) - Arm education course on deploying and optimising models on Arm CPUs.

## Key papers

- 📄 [A White Paper on Neural Network Quantization](https://arxiv.org/abs/2106.08295) (Nagel et al.) - Practical guide to PTQ and QAT. Read this first.
- 📄 [Quantization and Training of Neural Networks for Efficient Integer-Arithmetic-Only Inference](https://arxiv.org/abs/1712.05877) (Jacob et al.) - The integer quantization scheme most hardware uses.
- 📄 [Deep Compression](https://arxiv.org/abs/1510.00149) (Han et al.) - Pruning, quantization and Huffman coding combined.
- 📄 [Once-for-All: Train One Network and Specialize it for Efficient Deployment](https://arxiv.org/abs/1908.09791) (Cai et al.) - Hardware-aware neural architecture search.
- 📄 [MCUNet: Tiny Deep Learning on IoT Devices](https://arxiv.org/abs/2007.10319) (Lin et al.) - Co-designing the model and the inference engine for microcontrollers.

## Quantization and compression tools

- 🛠️ [torchao](https://github.com/pytorch/ao) - PyTorch-native quantization and sparsity.
- 🛠️ [Brevitas](https://github.com/Xilinx/brevitas) - Quantization-aware training in PyTorch, built for FPGA flows.
- 🛠️ [QKeras](https://github.com/google/qkeras) - Quantization-aware training for Keras; pairs with hls4ml.

## FPGA ML flows

- 🛠️ [hls4ml](https://github.com/fastmachinelearning/hls4ml) - Turns trained models into HLS code for FPGAs, with very low latency.
- 🧩 [hls4ml tutorial](https://github.com/fastmachinelearning/hls4ml-tutorial) - Notebooks that take you from model to FPGA resources.
- 🛠️ [FINN](https://github.com/Xilinx/finn) - Builds dataflow FPGA accelerators for quantized networks.

## Compilers and runtimes

- 🛠️ [Apache TVM](https://tvm.apache.org/) - Open deep learning compiler for CPUs, GPUs and accelerators.
- 🛠️ [MLIR](https://mlir.llvm.org/) - Compiler infrastructure behind many modern ML compilers.
- 🛠️ [IREE](https://iree.dev/) - MLIR-based compiler and runtime for edge and datacenter.
- 🛠️ [ExecuTorch](https://github.com/pytorch/executorch) - PyTorch's on-device inference runtime.
- 🛠️ [TensorFlow Lite Micro](https://github.com/tensorflow/tflite-micro) - Inference on microcontrollers.
- 🛠️ [CMSIS-NN](https://github.com/ARM-software/CMSIS-NN) - Optimised neural network kernels for Arm Cortex-M.

## Benchmarks

- 🧩 [MLPerf Tiny](https://github.com/mlcommons/tiny) - Standard benchmarks for tiny ML systems; compare your results with published ones.
