# VERT Drop‑ins — Chapter 2 (Round 2)
_Paste these verbatim in the specified sections._

---

## 1) Metrics tables preface (all five tables)
```md
**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.
```

---

## 2) Governance — Policy-aware caching (Pillar 4 → Common failures)
```md
> **Policy-aware caching.** To maintain security without harming UX latency, include **user attributes** and the active **policy version** in cache keys, and **invalidate caches on policy change** events. This prevents replaying content outside the user’s current authorization scope.
```

---

## 3) Observability — Production Acceptance (Pillar 5)
```md
> **Production-ready when (for 30 consecutive days):**
> • Monitoring **coverage ≥95%** across data (freshness/completeness/accuracy), agent (latency p95, timeout), model (**NDCG ≥0.85**, drift), and **cost/query**.
> • **MTTD <15 min** and **MTTR <2 hr** for P1 incidents; **alert precision >85%**.
> • Nightly retrieval regression holds **NDCG ≥0.85**.
```

---

## 4) Semantic Richness — Drift SOP (Pillar 2)
```md
> **Semantic Drift SOP (≤7 days end-to-end):**
> **Detect** (weekly NLQ term mining + anomaly alerts) → **Review** (steward triage ≤48h)
> → **Update** (glossary/ontology/metrics + re-embed) → **Validate** (offline eval **NDCG ≥0.85**
> + short shadow run).
```

---

## 5) Accessibility — 2-second budget table (Pillar 1)
```md
| Stage                          | Budget (p95) |
|--------------------------------|--------------|
| Intent / NLU                   | 100 ms       |
| **Retrieval (multi-source)**   | **≤200 ms**  |
| Context assembly               | 100 ms       |
| LLM generation                 | ~500 ms      |
| Response formatting            | 100 ms       |
| Network / overhead             | ~100 ms      |
| **Total**                      | **≈2.0 s**   |
```
**Follow with:**  
- **Parallelize retrieval** across sources (avoid sequential waterfalls).  
- Use **GPU/managed embeddings** to keep semantic lookups inside budget.
```

---

## 6) Quality & Trust — guardrails (Pillar 3)
```md
- **Fail-closed on critical fields:** quarantine or reject on validation failure; surface **data-health status** to the agent so it can defer or caveat answers.
- **Golden-record rule:** document reconciliation precedence (source of truth + freshness) and expose **“last updated by [system], [timestamp]”** where user-relevant.
```

---

## 7) Diagram captions (Diagrams 8 & 9)
- **Diagram 8 (Pillar Interdependencies):** “Observability monitors and improves all pillars; Governance↔Accessibility must balance sub-10 ms policy checks with 2 s UX; Semantic enables Governance and Quality.”
- **Diagram 9 (Pillars→Layers):** “PRIMARY links implement the pillar; SECONDARY links enforce, validate, or monitor.”
