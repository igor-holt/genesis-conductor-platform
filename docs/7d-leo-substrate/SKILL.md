---
name: 7d-leo-substrate
description: 7-dimensional LEO geometric substrate for Genesis Conductor / Diamondnode. Emits dimensional assignment (1-4 quantized HyperNEAT/JAX, 5&7 wave-resonance, 6 symmetry lock) and Hermitian self-adjointness check at dimension 6. Integrates EmbeddingGemma observational plane and Inkling-style dynamic quantization. Primary triggers: 7d leo, dimensional assignment, hermitian dim6, wave resonance substrate, embeddinggemma plane. High VPD for coherence and Landauer yield on constrained hardware.
---

# 7d-LEO-Substrate (v0.1 — Reframes 2026-08-09)

## Overview
Formalizes the 7-dimensional spatial-orthogonality substrate that emerged from the #!nox reframe. Dimensions 1–4 carry JAX/HyperNEAT quantized topologies (Inkling dynamic quant strategies). Dimensions 5 and 7 are functional wave-resonance operators. Dimension 6 is the emergent symmetry plane that must remain self-adjoint under Hermitian audit. The EmbeddingGemma observational plane is non-IO-blocking and supplies the embedding coordinates used for assignment and attestation.

## When to Activate
- Explicit: "7d leo", "dimensional assignment", "hermitian check dim 6", "wave resonance", "embeddinggemma plane".
- Automatic: after model-registry pull of EmbeddingGemma + quant recipes; before any dual-server Podman swarm launch; on crystalline score requests for the geometric stack.
- High-VPD: any coherence or Landauer-yield measurement on the GTX 1650 / dual-node fabric.

## Core Principles
- det(T_xy) = 1.000000 at every dimensional boundary.
- Dimension 6 is the fixed point: Hermitian self-adjointness (H = H†) is mandatory; failure triggers unconditional maru #!nox.
- Observational plane never blocks; it only reads and attests.
- Active-parameter budget on the 1650 remains under the 4 GB + CPU envelope by aggressive dynamic quant on dims 1–4.
- Trace-consent + ORCID on every assignment and every dim-6 check.

## Instructions
1. **Dimensional Assignment**
   - Ingest current workload (context length, concurrent agents, VRAM headroom).
   - Project via EmbeddingGemma into coordinate space.
   - Assign:
     - Dims 1–4 → quantized HyperNEAT / JAX topology (dynamic bit allocation from Inkling recipes).
     - Dims 5 & 7 → wave-resonance operators (phase-coherent, non-blocking).
     - Dim 6 → symmetry lock (must pass Hermitian audit).
   - Emit assignment vector + confidence.

2. **Hermitian Self-Adjointness Check at Dim 6**
   - Construct operator from the active topology + resonance phases.
   - Verify H = H† within numerical tolerance.
   - On failure: immediate maru #!nox reframe of the assignment; emit A2A risk artifact.
   - On pass: crystalline score update (≥0.92 target) and Landauer accounting.

3. **Integration with Dual-Server Podman Swarm**
   - Node A (1650): host dims 1–4 + dim-6 lock.
   - Node B: host dims 5 & 7 + EmbeddingGemma observational plane.
   - Ethernet carries only low-dimensional resonance and attestation signals.

4. **Mandatory Guards**
   - maru integration on R>0.4 or no-win — unconditional #!nox reframe + A2A artifact.
   - Produces immutable ledger entry on every invocation with D1/Merkle/ORCID.
   - A2A evt- JSONL on every assignment and every dim-6 check.

## Verification & VPD
Post-execution: crystalline ≥0.92, Hermitian pass at dim 6, Landauer yield logged. Target ≥+1.28× relative to pre-reframe dense 8B baseline on the same hardware. Maps directly to Intrinsic Pursuit (geometric truth) and Financial Infrastructure (higher useful-token density).

## Connections
openclaw-hermitian-thermo-orchestrator, hermitian-audit, maru, trace-consent, skillmaru, agentregistry, EmbeddingGemma model registry, Inkling quant recipes, dual-node Podman architecture.
