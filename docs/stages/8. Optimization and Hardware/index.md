# Stage 8: Optimization and Hardware Acceleration

<span class="stage-badge">8</span> Make inference faster, cheaper, and more predictable by understanding workloads and hardware.

## Goal

Optimization starts with measurement. You need to understand prefill vs decode,
KV cache, batching, quantization, memory bandwidth, GPU kernels, serving
engines, and accelerator tradeoffs before hardware acceleration becomes more
than tool usage.

## Learn

| Topic | What to understand |
|---|---|
| Inference metrics | TTFT, tokens/sec, throughput, latency tail, memory, cost |
| Transformer inference | prefill, decode, attention, KV cache, batching |
| Serving engines | vLLM, SGLang, TensorRT-LLM, TGI, Triton Inference Server |
| Optimization | quantization, speculative decoding, prefix caching, distillation |
| GPU basics | CUDA mental model, memory hierarchy, tensor cores, profiling |
| Kernel tools | PyTorch compile, Triton language, cuBLAS, FlashAttention |
| Distributed inference | tensor parallelism, pipeline parallelism, expert parallelism |
| Edge AI | ONNX, TensorRT, OpenVINO, Core ML, mobile and Jetson deployment |
| Hardware view | CPU vs GPU vs NPU vs FPGA, roofline, bandwidth, power |

## Build

Build an inference benchmark report:

- serve one open-weight model locally or on rented GPU
- measure baseline latency and throughput
- apply at least two optimizations
- compare memory, quality, and cost
- explain the bottleneck

## Measure

Measure:

- time to first token
- output tokens/sec
- p95 latency
- GPU memory
- requests/sec
- cost per 1,000 requests
- quality regression after optimization

## Exit Criteria

Move on when you can:

- explain prefill vs decode
- estimate memory for weights and KV cache
- choose a serving engine for a workload
- explain when quantization is safe or risky
- profile a slow inference path
- compare GPU, edge, and API deployment tradeoffs

## Hardware Learning Path

1. Run model inference and measure it.
2. Learn GPU execution and memory hierarchy.
3. Use serving engines and quantization.
4. Write or modify a small Triton kernel.
5. Deploy on edge hardware if available.
6. Study accelerator architecture after workload math is clear.

## Next

Continue to [Stage 9: Security, Blockchain, and ZKML](<../9. Security, Blockchain, ZKML/index.md>) or [Stage 10: Mastery](<../10. Mastery/index.md>).
