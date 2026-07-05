# 🧠 Limen Neural

> *Build a modular, hardware-agnostic toolkit for encoding, simulation, telemetry, neuromorphic algorithms, SNN–LLM quantization, and bio-inspired computation — without relying on any local environment quirks.*

Limen Neural is a solo research effort to build reusable, modular libraries for spiking neural networks and hybrid SNN–LLM systems. The work is primarily independent experimentation (including with AI coding agents) whose outputs are intended for personal use and for anyone else who wants to experiment with them.

The platform is organized as a collection of focused crates and packages with clear architectural layers and strict repository boundaries. Everything is designed to be portable, reproducible, and hardware-agnostic (CPU, CUDA, FPGA) so the pieces can be picked up and used independently.

All code is released under permissive licenses. People are free to use the libraries however they like.

## Architecture

Limen Neural separates concerns across five layers:

| Layer                  | Purpose                                      |
|------------------------|----------------------------------------------|
| **Encoding**           | Convert analog signals into spike trains     |
| **Neuron Dynamics**    | Biologically plausible neuron models         |
| **Topology & Wiring**  | Synaptic mesh, delays, sparse maps           |
| **Simulation & Training** | GPU-accelerated SNN inference and learning |
| **Hardware Export**    | FPGA synthesis, Q8.8 fixed-point deployment  |

## Technology & Philosophy

- **Rust** for performance-critical infrastructure: encoding, neuron models, wiring, IPC, runtimes, and hardware bridges.
- **Julia** for research algorithms and applications: training, spike feature extraction, large-scale simulations, and control-plane tooling.
- **Hard repo boundaries**: each repository owns a single layer or concern. No cross-layer state duplication.
- Emphasis on reproducibility, comprehensive CI, clear ownership documentation, and modular reuse.

## Current Research Focus

- **SAAQ — Spiking Adaptive Activity Quantization**: discovering and validating mathematical formulas for spike-based quantization using symbolic regression and routing techniques.
- **SNN ↔ LLM Fusion**: standardized interfaces and orchestrators for converting embeddings, latents, and activations into spike-based dynamics (see hybrid-fusion, cortex-tensor, engram-parser).
- **FPGA Neuromorphic Deployment**: Q8.8 fixed-point export pipelines and SystemVerilog primitives for real hardware.

Python support is on the roadmap to increase accessibility as the core platform matures.

## Repository Ecosystem

Limen Neural currently comprises 22 focused repositories.

For the complete, up-to-date repository map with descriptions of every crate and package, see [`profile/README.md`](profile/README.md).

**Selected highlights** (see profile for the full list):
- **Rust core**: `neuromod` (SNN dynamics), `axon-encoder` (sensory encoding), `synaptic-mesh` (topology & delays), `hybrid-fusion` (transformer-to-SNN orchestration), `cortex-tensor` (pure-Rust tensors + MoE), `engram-parser` (GGUF/MoE extraction), `limbic-critic` (neuromodulator mapping), `kinetic-signals` (streaming features), `metabolic-ledger` (bio-inspired accounting), `brainstem-daemon` & `thalamic-relay` (runtimes), `plasticity-lab`, `corpus-ipc`, `silicon-bridge`.
- **Julia research/apps**: `LiquidCortex.jl` (GPU sparse LSM), `NeuroPulse.jl` (spike-driven relevance routing), `SpikeStream.jl` (spike feature extraction), `SynapticDistill.jl`, `TemporalFocus.jl`, `DendriteTrader.jl`.
- **Hardware**: `silicon-hdl` (Vivado-ready SNN FPGA primitives).

## This Repository

`Limen-Neural/.github` provides the organization profile (displayed on https://github.com/Limen-Neural) and shared GitHub configuration for the Limen Neural ecosystem.

## Links

- Organization: https://github.com/Limen-Neural
- Hugging Face: https://huggingface.co/rmems
- X / Twitter: [@KeepOnSpiking](https://twitter.com/KeepOnSpiking)

## Usage & Contributing

All libraries are permissively licensed (MIT/Apache-2.0 unless noted). You are free to use, modify, and experiment with the code as you please.

Each repository maintains its own README with scope, development commands, testing requirements, and boundary documentation. Please respect the explicit ownership boundaries when proposing changes or building on the work.

---

*Solo experimental neuromorphic libraries — Limen Neural (2026).*

*Updated by Grok Build Agent (xAI).*
