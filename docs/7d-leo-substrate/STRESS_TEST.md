# 7-d Orthogonality Stress Test Protocol

## Goal
Measure Landauer yield and crystalline score of the new substrate vs the pre-reframe dense 8B baseline (May 2026 ngl=20 numbers).

## Procedure (run on diamondnode after model pull + residual Pascal MMQ recompile)
1. Load EmbeddingGemma observational plane.
2. Instantiate a minimal 7-d assignment (synthetic HyperNEAT topology on dims 1–4, simple phase oscillators on 5 & 7).
3. Execute 50 short forward passes under the geometric constraints.
4. Record:
   - tokens processed
   - wall time
   - estimated energy (or proxy via power draw if available)
   - Hermitian residual at dim 6
   - pairwise orthogonality (cosine / Grassmann) among active dims
5. Compute:
   - Landauer yield = (useful tokens / energy) relative to baseline
   - Crystalline score from Hermitian residual + orthogonality + stability
6. Pass criteria: yield ≥ +1.28× **and** crystalline ≥ 0.92 → annealing→quant skill is born inside the geometry.

## Baseline reference
- Prompt 512: 73.39 t/s
- Gen ~9.35 t/s
- ngl=20, Hermes-3-8B Q4_K_M, pre-MMQ

## Output
evt- JSONL with yield, crystalline, Hermitian residual, and decision (skill birth or further reframe).
