# 🧠 Limen Neural — Generalized Neuromorphic Library

Hey, I'm Raul. I'm an out‑of‑the‑box tinkerer, builder, and relentless experimenter based in San Marcos, Texas.

What hooked me was the elegance — the way spikes, timing, and sparse events could mirror real brain‑like computation. The excitement was addictive, and suddenly I was in deep hyperfocus: experimenting with temporal coding, data extraction, playing with FPGA ideas, and trying to build biologically plausible systems from the ground up, right on my new build rig.

But here's the honest part: rapid growth + hyperfocus = messy codebase. I treated GitHub more like a personal cloud backup than a proper development platform. Accidental terminal deletions wiped out chunks of work. Modules were scattered. Dependencies were tied to my local Fedora setup. Even an AI coding agent I tried made things worse at times. A lot of early "real" code got lost in the chaos.

Because of that rapid growth, a lot of the early code became chaotic: accidental terminal deletions, disorganized modules, local Fedora‑specific dependencies, and an AI agent that made things worse instead of better. A lot of my real code began washing away. I used GitHub mostly as a cloud backup, not as a real development platform.

Everything is moving toward being **portable, reproducible, and free of local environment quirks**.

### Current State & Roadmap

- Removing Fedora‑specific and other local dependencies  
- Eventually bringing back HDL libraries for FPGA neuromorphic enthusiasts  
- Spikenaut will return in a cleaner, stronger form as I rebuild the algorithms, data engineering, and architecture behind it.

This won't happen overnight — it's a deliberate, careful rebuild. But I'm committed to doing it right.

I want Limen Neural to become a clean, open, community‑friendly project — not something trapped on my local machine. I want to rebuild the parts that were lost, refine the parts that survived, and finally share the work I’ve been doing on Spikenaut, neuromorphic data and algorithms, now SAAQ (Spiking Activity Adaptive Quantization) and Metis (MoE‑SNN), in a way that others can actually use.

Even as an opportunity to learn from y'all.

If you have ideas, suggestions, or want to collaborate, I’d genuinely love to hear them.

The long‑term goal is simple:

## 🚀 Purpose

Limen Neural provides a clean, reusable foundation for:

- **Spiking Neural Network (SNN) encoding**  
  Rate, temporal, population, and neuromodulated encoders.

- **GPU‑accelerated SNN simulation**  
  Designed to integrate with CUDA, maybe even ROCm, or CPU backends.

- **Telemetry extraction & quantization**  
  Including SAAQ (Spiking Activity & Adaptive Quantization) and data extraction for hardware‑driven learning.

- **LLM ↔ SNN fusion research**  
  A standardized interface for converting embeddings, latents, or activations into spike‑based dynamics.

This future library is going to be the “generalized chassis” extracted from the original workstation‑bound architecture — now being rebuilt to be portable, reproducible, and open.

This project is as much about the journey as the destination. Thanks for stopping by — let's push neuromorphic computing forward together, one spike at a time. ⚡

---

*“The long‑term goal is simple: Build a modular, hardware‑agnostic toolkit for encoding, simulation, telemetry, neuromorphic algorithms, SNN‑LLM quantization, and bio‑inspired computation — without relying on any local environment quirks.”*
