# 🧠 Limen Neural

> *Build a modular, hardware-agnostic toolkit for encoding, simulation, telemetry, neuromorphic algorithms, SNN–LLM quantization, and bio-inspired computation — without relying on any local environment quirks.*

Hey, I'm Raul — an out‑of‑the‑box tinkerer, builder, and relentless experimenter based in San Marcos, Texas. What hooked me was the elegance: the way spikes, timing, and sparse events can mirror real brain‑like computation. The excitement was addictive, and suddenly I was in deep hyperfocus — experimenting with temporal coding, FPGA ideas, and trying to build biologically plausible systems from the ground up on my RTX 5080 rig.

Rapid growth + hyperfocus = messy early codebase. I used GitHub like a cloud backup, not a development platform. Accidental deletions wiped chunks of work. Modules scattered. Dependencies baked into my local Fedora setup. Everything is now moving toward being **portable, reproducible, and free of local environment quirks**.

---

## 🚀 What Limen Neural Builds

Limen Neural is an open‑source neuromorphic research platform organized around a clean set of Rust and Julia crates/packages. The architecture separates concerns across five layers:

| Layer | Purpose |
|-------|---------|
| **Encoding** | Convert analog signals into spike trains |
| **Neuron Dynamics** | Biologically plausible neuron models |
| **Topology & Wiring** | Synaptic mesh, delays, sparse maps |
| **Simulation & Training** | GPU-accelerated SNN inference and learning |
| **Hardware Export** | FPGA synthesis, Q8.8 fixed-point deployment |

---

## 🗂️ Repository Map

### 🦀 Rust — Core Infrastructure

| Repo | Description |
|------|-------------|
| [`axon-encoder`](https://github.com/Limen-Neural/axon-encoder) | SNN sensory encoding pipelines: Poisson spike trains, rate/temporal/predictive coding, neuromodulator-driven encoding |
| [`neuromod`](https://github.com/Limen-Neural/neuromod) | High-performance SNN library: LIF, Izhikevich, Hebbian, Nagumo, Lapicque, and Hodgkin-Huxley neuron dynamics |
| [`synaptic-mesh`](https://github.com/Limen-Neural/synaptic-mesh) | Wiring, topology, and temporal delay infrastructure between neurons |
| [`kinetic-signals`](https://github.com/Limen-Neural/kinetic-signals) | Streaming feature extraction for high-velocity stochastic signals (Hurst, Hawkes, GBM, entropy) |
| [`corpus-ipc`](https://github.com/Limen-Neural/corpus-ipc) | ZMQ-based IPC bridge — sends float vectors in, receives spike output back |
| [`silicon-bridge`](https://github.com/Limen-Neural/silicon-bridge) | SNN-to-FPGA deployment: Q8.8 parameter export, `.mem` generation for Vivado `$readmemh`, UART readback |
| [`thalamic-relay`](https://github.com/Limen-Neural/thalamic-relay) | Live hardware supervision, orchestration, and SNN input pipeline |
| [`limbic-critic`](https://github.com/Limen-Neural/limbic-critic) | Neuromodulator mapping: Dopamine (reward), Serotonin (risk/patience), Cortisol (stress) |
| [`engram-parser`](https://github.com/Limen-Neural/engram-parser) | Extracts frozen weights from MoE models to feed into live spiking networks |
| [`cortex-tensor`](https://github.com/Limen-Neural/cortex-tensor) | Pure-Rust matrix multiplication and Transformer execution |
| [`plasticity-lab`](https://github.com/Limen-Neural/plasticity-lab) | Offline/closed-loop SNN training experiments |
| [`metabolic-ledger`](https://github.com/Limen-Neural/metabolic-ledger) | ATP energy metaphors, adaptive Kelly commitment, metabolic cost tracking for SNN portfolios |
| [`brainstem-daemon`](https://github.com/Limen-Neural/brainstem-daemon) | Soma-level daemon and system runtime |
| [`hybrid-fusion`](https://github.com/Limen-Neural/hybrid-fusion) | SNN–LLM hybrid fusion research |

### 🔵 Julia — Algorithms & Application Layer

| Repo | Description |
|------|-------------|
| [`SpikeStream.jl`](https://github.com/Limen-Neural/SpikeStream.jl) | Streaming spike feature extraction: spike count, density, ISI stats, burst detection — zero allocation |
| [`SynapticDistill.jl`](https://github.com/Limen-Neural/SynapticDistill.jl) | Monte Carlo SNN training + FPGA distillation: E-prop, ensemble weight distillation, Q8.8 `.mem` export |
| [`LiquidCortex.jl`](https://github.com/Limen-Neural/LiquidCortex.jl) | GPU-accelerated sparse Liquid State Machine — 65k-neuron CUDA LSM with OU-SDE dynamics and STDP |
| [`NeuroPulse.jl`](https://github.com/Limen-Neural/NeuroPulse.jl) | NERO: multi-lobe SNN relevance scoring with cross-lobe inhibition and softmax normalisation |
| [`TemporalFocus.jl`](https://github.com/Limen-Neural/TemporalFocus.jl) | Spike-coincidence attention kernel — attention via spike-time correlation, not softmax |
| [`DendriteTrader.jl`](https://github.com/Limen-Neural/DendriteTrader.jl) | Async SNN trade execution: ZMQ SUB → confidence gating → Kelly sizing → dYdX v4 REST |

### ⚡ Hardware

| Repo | Description |
|------|-------------|
| [`Spikenaut-Hardware`](https://github.com/Limen-Neural/Spikenaut-Hardware) | SystemVerilog HDL for FPGA neuromorphic implementations |

---

## 🔬 Current Research Focus

- **SAAQ — Spiking Adaptive Activity Quantization**: Discovering and validating mathematical formulas for spike-based quantization using symbolic regression
- **SNN ↔ LLM Fusion**: Standardized interface for converting embeddings, latents, and activations into spike-based dynamics
- **FPGA Neuromorphic Deployment**: Q8.8 fixed-point export pipeline from trained SNN weights to Vivado `.mem` files

---

## 🛠️ Architecture Philosophy

- **Rust for performance-critical infrastructure** — encoding, wiring, IPC, hardware bridge, neuron simulation
- **Julia for research algorithms** — SNN training, spike features, CUDA-accelerated inference
- **Hard repo boundaries** — each crate/package owns one layer; no cross-layer state duplication
- **Hardware-agnostic** — CUDA, FPGA (Vivado), and CPU backends all in scope

---

## 🔭 Long-Term Vision

The long-term goal is to create **usable, modularized neuromorphic libraries** — clean, portable packages that anyone can drop into their own projects without fighting local environment quirks.

Python support is on the roadmap. Whether as standalone Python packages or bindings into the existing Rust/Julia repos is still TBD — the priority is making the work accessible to the broader Python community as the platform matures.

---

## 📡 Links

- 🤗 HuggingFace: [huggingface.co/rmems](https://huggingface.co/rmems)
- 🐦 Twitter/X: [@KeepOnSpiking](https://twitter.com/KeepOnSpiking)
- 📍 San Marcos, Texas, USA

---

## 🤝 Contributing

Ideas, suggestions, and collaboration are genuinely welcome. This is as much about the journey as the destination.

> *Thanks for stopping by — let's push neuromorphic computing forward together, one spike at a time. ⚡*

---

*This README was drafted by [Viktor](https://viktor.com) (AI · Claude Sonnet 4.6).*
