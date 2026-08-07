# DSCP Routing Invariants Specification

**Genesis Conductor Platform**  
**Version:** 1.0.0  
**Thermodynamic Priority:** EF  
**Author:** Igor Holt <igor@kovachenterprises.com>  
**ORCID:** 0009-0008-8389-1297  
**Commit Context:** feat(core): implement global @grok ingestion binary & DSCP routing invariants

## 1. Purpose

This document defines the Differentiated Services Code Point (DSCP) routing invariants used by the Genesis Conductor Platform for priority-aware packet and payload routing across Ambient Access Layer (AAL), MCP, UCP, and edge workers.

DSCP enables thermodynamic-aware prioritization: high-value, low-entropy, or time-critical agent trajectories receive Expedited Forwarding treatment, minimizing Landauer energy cost and maximizing crystalline invariant preservation.

## 2. Canonical Tags

| DSCP Value | Name | PHB | Genesis Mapping | Use Case |
|------------|------|-----|-----------------|----------|
| 46 | EF | Expedited Forwarding | `thermodynamic_priority: "EF"` | Global @grok ingestion, critical cycle settlement, KVDF NFT mint, maru reframe |
| 34 | AF41 | Assured Forwarding 4 | High-assurance agent telemetry | Hermitian audit streams, trace-consent Merkle updates |
| 26 | AF31 | Assured Forwarding 3 | Standard A2A orchestration | Ordinary skill dispatch |
| 0 | CS0 / BE | Best Effort | Background / bulk | Non-critical logging, archival |

**Invariant:** All production @grok binary payloads MUST carry DSCP 46 (EF) unless explicitly overridden by an authenticated UCP power-tower decision.

## 3. Binary Envelope Format (scripts/grok_payload.py)

```
Offset  Size  Field
0       4     Magic "GROK"
4       1     Version (uint8) = 1
5       1     DSCP tag (uint8) 0–63
6       4     Payload length (uint32 big-endian)
10      N     Raw payload bytes
```

Checksum: SHA-256 of the raw payload (not including header). Verified on decode.

## 4. Routing Invariants

1. **EF Strict Priority**  
   Packets/payloads with DSCP 46 are placed on the express queue. No preemption by lower classes. Bounded latency target ≤ 5 ms on Diamondnode edge paths.

2. **No Degradation of EF**  
   EF traffic MUST NOT be remarked downward except by an authenticated EulerCycleAttestor v2 decision under R > 0.4 (maru path).

3. **Thermodynamic Accounting**  
   Every EF-routed ingestion increments the VPD ledger with Landauer cost estimate:  `kT ln 2 × bits_processed`. Logged via trace-consent.

4. **Hermitian Preservation**  
   DSCP transitions are self-adjoint: the routing operator R satisfies ⟨ψ|R|φ⟩ = ⟨Rψ|φ⟩ for state vectors on the manifold. Verified by hermitian-audit skill.

5. **Zero Private Exposure**  
   DSCP headers and routing decisions contain no PII or private trajectory data. Only capability hashes and priority class.

## 5. Integration Points

- **Ambient Access Layer (AAL):** Cloudflare Worker routes EF to diamondnode production domains first.
- **MCP / UCP:** TaskEnvelope carries optional `dscp` field; default 46 for Grok-sourced tasks.
- **OpenClaw / Hermes:** Local polyagent runtime honors DSCP when bridging to remote AAL.
- **maru:** On no-win, may temporarily elevate a cycle to EF for reframe execution, then restore original class.

## 6. Validation

```bash
python scripts/grok_payload.py --encode sample.json --dscp 46 --out sample.grok
python scripts/grok_payload.py --decode sample.grok
```

Expected route: `EF_EXPRESS_QUEUE`.

## 7. References

- RFC 2598 / RFC 3246 (Expedited Forwarding PHB)
- Genesis Conductor UCP Integration skill (power-tower + AAL)
- Hermitian-audit skill (self-adjointness)
- Trace-consent skill (immutable ledger)

---

*Part of the Genesis Conductor thermodynamic AI orchestration stack.*  
*Maryland-governed · Annapolis arbitration · EO 14363 aligned*
