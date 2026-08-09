# Diamondnode Model Registry — 7-d LEO Substrate (Reframe 2026-08-09)

## Observational Planar Layer (non-IO-blocking)
**EmbeddingGemma 300M** (Matryoshka, on-device)
- Primary: `ggml-org/embeddinggemma-300M-GGUF` or `unsloth/embeddinggemma-300m-GGUF`
- Size: ~212–334 MB (Q2_K to Q8_0)
- Pull:
  ```bash
  # on diamondnode
  mkdir -p /home/diamondnode/models/embedding
  cd /home/diamondnode/models/embedding
  huggingface-cli download ggml-org/embeddinggemma-300M-GGUF --local-dir .
  # or
  ollama pull embeddinggemma
  ```
- Role: Dimension-agnostic observational plane. Emits embeddings for Hermitian audit and 7-d coordinate assignment. Never blocks forward path.

## Quantization Strategies (Inkling-derived, applied to dims 1-4)
Source: Unsloth Dynamic GGUF recipes from `unsloth/inkling-GGUF` and Unsloth Dynamic 2.0 docs.
- Selective layer-wise dynamic bit allocation (1–4 bit dominant, higher precision only where KL divergence requires).
- Shared-expert sinks, short-convolution patterns, relative positional bias where residual dense pieces remain.
- Active-parameter collapse target: ≤4–5 % for any sparse component hosted on the 1650.
- Reference recipes:
  - UD-IQ1_S / UD-IQ1_M (1-bit dynamic)
  - UD-Q2_K_XL, UD-Q3_K_XL, UD-Q4_K_XL
- Application: Extract the *strategy*, not the full 975B/41B active model. Apply to HyperNEAT-generated topologies and any residual dense kernels that still require Pascal MMQ.

## Residual Dense Path
Only the pieces that cannot yet be sparsified or embedded stay on the Pascal-MMQ recompiled llama.cpp binary (ngl limited, FORCE_MMQ=ON). All other work moves to embedding + quantized geometric substrate.

## Registry Status
- Asset ID: evt_7d_leo_model_registry_20260809
- Mapped objectives: Intrinsic Pursuit (geometric invariants), Hybridization (observational plane), Financial Infrastructure (higher useful-token density on existing 1650 hardware)
- Next: after pull, run Hermitian self-adjointness check at dim 6 via the 7d-leo-substrate skill.
