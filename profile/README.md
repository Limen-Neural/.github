# Limen Neural

[![CI](https://github.com/Limen-Neural/neuromod/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/Limen-Neural/neuromod/actions/workflows/ci.yml)
[![codecov](https://codecov.io/gh/Limen-Neural/neuromod/branch/main/graph/badge.svg)](https://codecov.io/gh/Limen-Neural/neuromod)

> Encode. Spike. Wire. Stimulate. Deploy.  
> Modular, hardware-agnostic libraries for spiking neural networks and bio-inspired computation.

**Limen Neural** is a solo research org building small, reusable building blocks for SNNs — encoding, dynamics, topology, training loops, GPU kernels, interchange (NIR), and runtimes. Work is experimental, agent-assisted, and released under permissive licenses for anyone who wants to try it.

This org is intentionally **small**. Broader experiments, tooling, quantization labs, viz, cloud notes, and one-off research live under my personal account [@rmems](https://github.com/rmems) so Limen-Neural stays a clean core surface for a solo maintainer.

---

## Maintainer note (pace)

I am a solo maintainer.

I am currently enrolled at **Western Governors University (WGU)** in **AI Engineering**, and I am investing more time learning and manually reviewing code in:

- **Rust**
- **Python**
- **Julia**
- **C# / .NET**

Issues and PRs of any size are welcome.

---

## Architecture

Limen Neural keeps **hard repo boundaries**. Each repository owns one concern.

| Layer | Purpose | Core repos |
|-------|---------|------------|
| **Encoding** | Analog / feature streams → spike trains | [`axon-encoder`](https://github.com/Limen-Neural/axon-encoder) |
| **Neuron dynamics** | Biologically grounded models + neuromodulation | [`neuromod`](https://github.com/Limen-Neural/neuromod) |
| **Topology & wiring** | Graphs, delays, sparse synaptic maps | [`synaptic-wiring`](https://github.com/Limen-Neural/synaptic-wiring) |
| **Interchange** | Framework-agnostic SNN IR (NIR) | [`nir-rs`](https://github.com/Limen-Neural/nir-rs) |
| **Training loops** | Offline / closed-loop plasticity | [`plasticity-lab`](https://github.com/Limen-Neural/plasticity-lab) |
| **GPU kernels** | Blackwell-oriented CUDA / Rust compute | [`myelin-accelerator`](https://github.com/Limen-Neural/myelin-accelerator) |
| **Runtime** | Headless SNN inference daemon | [`brainstem-daemon`](https://github.com/Limen-Neural/brainstem-daemon) |
| **Transport** | Spike wire protocol, ZMQ transport, and REST contract between components | [`corpus-ipc`](https://github.com/Limen-Neural/corpus-ipc) |
| **Reward shaping** | Neuromodulatory critic for plasticity | [`limbic-critic`](https://github.com/Limen-Neural/limbic-critic) |

Shared org CI and the profile README live in [`.github`](https://github.com/Limen-Neural/.github).

---

## Repositories in this org

### Rust core

| Repository | Role |
|------------|------|
| [**neuromod**](https://github.com/Limen-Neural/neuromod) | Core SNN library: LIF, GIF, Izhikevich, FitzHugh–Nagumo, Hodgkin–Huxley, neuromodulators, plasticity hooks |
| [**axon-encoder**](https://github.com/Limen-Neural/axon-encoder) | Sensory / feature → spike encoding (rate, delta, latency, population, …) |
| [**synaptic-wiring**](https://github.com/Limen-Neural/synaptic-wiring) | Topology generators, axonal delays, sparse wiring |
| [**nir-rs**](https://github.com/Limen-Neural/nir-rs) | Pure-Rust [NIR](https://neuroir.org/) graph model + optional HDF5 `.nir` I/O |
| [**plasticity-lab**](https://github.com/Limen-Neural/plasticity-lab) | Domain-agnostic reward-modulated training loops around `neuromod` |
| [**myelin-accelerator**](https://github.com/Limen-Neural/myelin-accelerator) | Low-level CUDA/Rust kernels (Blackwell / `sm_120`, ternary paths, routing/SAT experiments) |
| [**brainstem-daemon**](https://github.com/Limen-Neural/brainstem-daemon) | Headless SNN inference runtime (`soma-daemon`) |
| [**corpus-ipc**](https://github.com/Limen-Neural/corpus-ipc) | Spike and neuromodulator wire protocol and IPC transports (ZMQ, REST contract) for SNN runtimes |
| [**limbic-critic**](https://github.com/Limen-Neural/limbic-critic) | Neuromodulatory reward-shaping primitive (Environment → Critic → ModulatorVector) for plasticity |

### Published crates

| Crate | crates.io | docs.rs |
|-------|-----------|---------|
| [`neuromod`](https://crates.io/crates/neuromod) | [![crates.io](https://img.shields.io/crates/v/neuromod.svg)](https://crates.io/crates/neuromod) | [![docs.rs](https://docs.rs/neuromod/badge.svg)](https://docs.rs/neuromod) |
| [`axon-encoder`](https://crates.io/crates/axon-encoder) | [![crates.io](https://img.shields.io/crates/v/axon-encoder.svg)](https://crates.io/crates/axon-encoder) | [![docs.rs](https://docs.rs/axon-encoder/badge.svg)](https://docs.rs/axon-encoder) |
| [`nir-rs`](https://crates.io/crates/nir-rs) | [![crates.io](https://img.shields.io/crates/v/nir-rs.svg)](https://crates.io/crates/nir-rs) | [![docs.rs](https://docs.rs/nir-rs/badge.svg)](https://docs.rs/nir-rs) |
| [`synaptic-wiring`](https://crates.io/crates/synaptic-wiring) | [![crates.io](https://img.shields.io/crates/v/synaptic-wiring.svg)](https://crates.io/crates/synaptic-wiring) | [![docs.rs](https://docs.rs/synaptic-wiring/badge.svg)](https://docs.rs/synaptic-wiring) |
| [`limbic-critic`](https://crates.io/crates/limbic-critic) | [![crates.io](https://img.shields.io/crates/v/limbic-critic.svg)](https://crates.io/crates/limbic-critic) | [![docs.rs](https://docs.rs/limbic-critic/badge.svg)](https://docs.rs/limbic-critic) |
| [`plasticity-lab`](https://crates.io/crates/plasticity-lab) | [![crates.io](https://img.shields.io/crates/v/plasticity-lab.svg)](https://crates.io/crates/plasticity-lab) | [![docs.rs](https://docs.rs/plasticity-lab/badge.svg)](https://docs.rs/plasticity-lab) |
| [`myelin-accelerator`](https://crates.io/crates/myelin-accelerator) | [![crates.io](https://img.shields.io/crates/v/myelin-accelerator.svg)](https://crates.io/crates/myelin-accelerator) | [![docs.rs](https://docs.rs/myelin-accelerator/badge.svg)](https://docs.rs/myelin-accelerator) |
| [`corpus-ipc`](https://crates.io/crates/corpus-ipc) | [![crates.io](https://img.shields.io/crates/v/corpus-ipc.svg)](https://crates.io/crates/corpus-ipc) | [![docs.rs](https://docs.rs/corpus-ipc/badge.svg)](https://docs.rs/corpus-ipc) |
| `brainstem-daemon` | Not published yet | — |

### Org meta

| Repository | Role |
|------------|------|
| [**.github**](https://github.com/Limen-Neural/.github) | Org profile + shared GitHub Actions workflows |

---

## Related work under @rmems

Personal and broader experimental repos (quantization bridges, MoE→SNN labs, telemetry, viz, HDL, trading research, agent tooling, cloud portfolio notes, Julia research apps, etc.) are **not** listed as Limen-Neural surface area. Browse [@rmems](https://github.com/rmems) if you are looking for those.

Examples of that wider sandbox include SAAQ / symbolic-regression work, hybrid MoE–SNN labs, gaming and mining telemetry collectors, spike visualization, SystemVerilog FPGA sketches, and multi-language playgrounds. They move faster, break more often, and are kept out of this org on purpose.

---

## Technology & philosophy

- **Rust** — performance-critical infrastructure: dynamics, encoding, wiring, IR, kernels, runtimes  
- **Julia** — research-scale simulation and personal language practice (packages live under [@rmems](https://github.com/rmems) unless promoted here)  
- **Python / C# .NET** — growing personal fluency for review, tooling, and broader ecosystem access (not a promise of first-class org packages yet)  
- **Hard boundaries** — one repo, one concern; no cross-layer state duplication  
- **Portable & reproducible** — CPU-first where possible; CUDA/FPGA paths explicit and optional  
- **Permissive licenses** — MIT / Apache-2.0 unless a repo says otherwise  

Python accessibility across [open neuromorphic frameworks](https://open-neuromorphic.org/neuromorphic-computing/software/snn-frameworks/) remains a longer-term interest as the core matures.

---

## Current research threads

- **Core SNN stack quality** — stable APIs in `neuromod`, encoders, mesh, and training loops  
- **NIR in Rust** — interchange without forcing a Python runtime  
- **GPU neuromorphic kernels** — Blackwell-oriented paths in `myelin-accelerator`  
- **Hybrid SNN–LLM / quantization** — mostly explored in personal `@rmems` labs, then folded back only when a piece is modular enough for this org  

---

## CI / quality

Shared workflows live in [Limen-Neural/.github/workflows](https://github.com/Limen-Neural/.github/tree/main/workflows).

Typical gates (per language / repo):

- **Rust** — fmt, Clippy, build/test, docs, feature matrix, MSRV where configured  
- **Julia** — package build, tests, formatting, coverage (shared templates; Julia packages are primarily under `@rmems`)  
- **Containers** — optional reproducible images (GHCR / Docker Hub) where a repo opts in  

Each library README shows its own badges. Agents and humans both benefit from failing early.

---

## This repository

`Limen-Neural/.github` is the organization profile (what you are reading on https://github.com/Limen-Neural) and the home for shared GitHub configuration.

---

## Usage & contributing

Libraries are permissively licensed. Use them, fork them, break them, rebuild them.

Issues and PRs are welcome — small fixes, docs tweaks, big features, all of it. I am a solo maintainer, so replies can take a bit.

---

*Solo experimental neuromorphic libraries — Limen Neural · maintained by [@rmems](https://github.com/rmems) · 2026*
