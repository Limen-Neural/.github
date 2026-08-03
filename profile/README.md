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

Starting **September 2026**, GitHub velocity here will slow down while I attend **Western Governors University (WGU)** for **AI Engineering**, and while I invest more time learning and manually reviewing code in:

- **Rust**
- **Python**
- **Julia**
- **C# / .NET**

Issues and PRs may sit longer. Review will be slower and more deliberate — that is intentional. The goal is deeper language fluency and better manual PR review, not maximum merge rate.

Thanks for patience if you are forking or building on these crates.

---

## Architecture

Limen Neural keeps **hard repo boundaries**. Each repository owns one concern.

| Layer | Purpose | Core repos |
|-------|---------|------------|
| **Encoding** | Analog / feature streams → spike trains | [`axon-encoder`](https://github.com/Limen-Neural/axon-encoder) |
| **Neuron dynamics** | Biologically grounded models + neuromodulation | [`neuromod`](https://github.com/Limen-Neural/neuromod) |
| **Topology & wiring** | Graphs, delays, sparse synaptic maps | [`synaptic-mesh`](https://github.com/Limen-Neural/synaptic-mesh) |
| **Interchange** | Framework-agnostic SNN IR (NIR) | [`nir-rs`](https://github.com/Limen-Neural/nir-rs) |
| **Training loops** | Offline / closed-loop plasticity | [`plasticity-lab`](https://github.com/Limen-Neural/plasticity-lab) |
| **GPU kernels** | Blackwell-oriented CUDA / Rust compute | [`myelin-accelerator`](https://github.com/Limen-Neural/myelin-accelerator) |
| **Runtime** | Headless SNN inference daemon | [`brainstem-daemon`](https://github.com/Limen-Neural/brainstem-daemon) |

Shared org CI and the profile README live in [`.github`](https://github.com/Limen-Neural/.github).

---

## Repositories in this org

### Rust core

| Repository | Role |
|------------|------|
| [**neuromod**](https://github.com/Limen-Neural/neuromod) | Core SNN library: LIF, GIF, Izhikevich, FitzHugh–Nagumo, Hodgkin–Huxley, neuromodulators, plasticity hooks |
| [**axon-encoder**](https://github.com/Limen-Neural/axon-encoder) | Sensory / feature → spike encoding (rate, delta, latency, population, …) |
| [**synaptic-mesh**](https://github.com/Limen-Neural/synaptic-mesh) | Topology generators, axonal delays, sparse wiring |
| [**nir-rs**](https://github.com/Limen-Neural/nir-rs) | Pure-Rust [NIR](https://neuroir.org/) graph model + optional HDF5 `.nir` I/O |
| [**plasticity-lab**](https://github.com/Limen-Neural/plasticity-lab) | Domain-agnostic reward-modulated training loops around `neuromod` |
| [**myelin-accelerator**](https://github.com/Limen-Neural/myelin-accelerator) | Low-level CUDA/Rust kernels (Blackwell / `sm_120`, ternary paths, routing/SAT experiments) |
| [**brainstem-daemon**](https://github.com/Limen-Neural/brainstem-daemon) | Headless SNN inference runtime (`soma-daemon`) |

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

If you open issues or PRs:

1. Prefer **small, single-concern** changes that respect repo boundaries  
2. Expect **slow review** from September 2026 onward (WGU + deliberate language practice)  
3. Read the target repo’s README for scope, commands, and ownership notes before proposing cross-crate redesigns  

I am not running a large community project — just publishing modular experiments that I want to keep honest and reviewable by hand.

---

*Solo experimental neuromorphic libraries — Limen Neural · maintained by [@rmems](https://github.com/rmems) · 2026*
