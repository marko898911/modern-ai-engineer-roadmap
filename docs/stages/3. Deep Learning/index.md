# Stage 3: Deep Learning

<span class="stage-badge">3</span> Understand neural networks deeply enough to train, debug, and read modern model code.

## Goal

LLMs are deep learning systems. Before transformers, learn the training loop:
forward pass, loss, backward pass, optimizer, batching, regularization, and
hardware-aware training.

## Learn

| Topic | What to understand |
|---|---|
| Neural network basics | layers, activations, loss, gradients, backpropagation |
| PyTorch | tensors, autograd, modules, dataloaders, optimizers |
| Training loop | batching, validation, checkpoints, learning rate schedules |
| Architectures | MLPs, CNNs, RNN intuition, attention preview |
| Numerical behavior | precision, initialization, exploding/vanishing gradients |
| Experiment discipline | seeds, configs, logging, ablations |

## Build

Build and train a neural model in PyTorch:

- one image classifier, text classifier, or small sequence model
- clean training loop
- validation metrics
- checkpointing
- error analysis

## Measure

Measure:

- training and validation curves
- final metric
- training time
- GPU or CPU memory use if possible
- one ablation such as learning rate, model size, or augmentation

## Exit Criteria

Move on when you can:

- write a PyTorch training loop without copying a full template
- explain what `loss.backward()` computes
- debug a model that does not learn
- explain why batch size, learning rate, and precision affect training
- read simple model architecture code

## Good Deepening Path

1. Implement a tiny autograd engine or read micrograd.
2. Train a PyTorch model.
3. Profile data loading and GPU utilization.
4. Write a short note connecting math to code.

## Next

Continue to [Stage 4: LLMs](<../4. LLMs/index.md>).
