# VERT Implementation Guide — Chapter 2 (Round 2)
_Audience: Claude + Authoring Team_  
_Date: October 9, 2025_

> **Use these snippets verbatim.** Each item includes the **insertion point** so you can patch quickly in `chapter_2_complete.txt` and `chapter_2_tables.txt`. Diagrams 8 & 9 already exist—just confirm captions.

---

## A) Metrics tables — add “Default SLOs” preface + Source column
**Files:** `chapter_2_tables.txt` (Tables 1–5), and mirror the same preface where the tables also appear in `chapter_2_complete.txt`.

**Insertion point (repeat above Tables 1–5):** Immediately **above** each “Metrics Dashboard” table heading.

**Paste this one-liner (identical for all five tables):**
```
**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.
```

**Add a final column to each table: `Source`**  
Use this mapping to fill the column:

- **Table 1 – Accessibility:** NIST CSF (uptime/monitoring). For latency/TTFB/cache where no formal standard exists, cite “Internal SRE best practices”.
- **Table 2 – Semantic Richness:** ISO/IEC 25012 (consistency/completeness concepts); Evidently AI (drift); Great Expectations (validation coverage).
- **Table 3 – Quality & Trust:** ISO/IEC 25012; NIST CSF (incident/SLAs); Great Expectations (rules/tests).
- **Table 4 – Governance & Security:** Open Policy Agent docs (ABAC evaluation, policy decisions, masking patterns); NIST CSF (audit/controls).
- **Table 5 – Observability:** NIST CSF (monitor/alert/MTTD/MTTR); Evidently AI (model/embedding drift, NDCG).

---

## B) Governance — “Policy-aware caching” note
**File:** `chapter_2_complete.txt`  
**Insertion point:** Pillar 4 → *Governance & Security* → under **Common failures & fixes** (after the latency/masking items).

**Paste this callout (verbatim):**
```
> **Policy-aware caching.** To maintain security without harming UX latency, include **user attributes** and the active **policy version** in cache keys, and **invalidate caches on policy change** events. This prevents replaying content outside the user’s current authorization scope.
```

---

## C) Observability — “Production Acceptance” (Definition of Done)
**File:** `chapter_2_complete.txt`  
**Insertion point:** Pillar 5 → *Observability – Seeing What Agents See* → **after** the “How to measure” metrics list.

**Paste this boxed checklist:**
```
> **Production-ready when (for 30 consecutive days):**
> • Monitoring **coverage ≥95%** across data (freshness/completeness/accuracy), agent (latency p95, timeout), model (**NDCG ≥0.85**, drift), and **cost/query**.
> • **MTTD <15 min** and **MTTR <2 hr** for P1 incidents; **alert precision >85%**.
> • Nightly retrieval regression holds **NDCG ≥0.85**.
```

---

## D) Semantic Richness — 4-step Semantic-Drift SOP
**File:** `chapter_2_complete.txt`  
**Insertion point:** Pillar 2 → *Semantic Richness* → **under** “How to measure” (or at the end of “Common failures”).

**Paste this box:**
```
> **Semantic Drift SOP (≤7 days end-to-end):**
> **Detect** (weekly NLQ term mining + anomaly alerts) → **Review** (steward triage ≤48h)
> → **Update** (glossary/ontology/metrics + re-embed) → **Validate** (offline eval **NDCG ≥0.85**
> + short shadow run).
```

---

## E) Accessibility — format the 2-second budget as a table
**File:** `chapter_2_complete.txt`  
**Insertion point:** Pillar 1 → *Accessibility – Why it matters* → where the 2-second flow is described.

**Paste this table:**
```
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

Follow with two bullets:
- **Parallelize retrieval** across sources (avoid sequential waterfalls).  
- Use **GPU/managed embeddings** to keep semantic lookups inside budget.

---

## F) Quality & Trust — two defaults (guardrails)
**File:** `chapter_2_complete.txt`  
**Insertion point:** Pillar 3 → *Quality & Trust* → within “How to measure” or “Common failures & fixes”.

**Paste these notes:**
```
- **Fail-closed on critical fields:** quarantine or reject on validation failure; surface **data-health status** to the agent so it can defer or caveat answers.
- **Golden-record rule:** document reconciliation precedence (source of truth + freshness) and expose **“last updated by [system], [timestamp]”** where user-relevant.
```

---

## G) Diagrams 8 & 9 — captions (no diagram changes)
**Files:** `diagram_8_mermaid_file.txt`, `diagram_9_mermaid_file.txt`

- **Diagram 8 (Pillar Interdependencies) – Caption to add/confirm:**  
  “Observability monitors and improves all pillars; Governance↔Accessibility must balance sub-10 ms policy checks with 2 s UX; Semantic enables Governance and Quality.”

- **Diagram 9 (Pillars→Layers) – Caption to add/confirm:**  
  “PRIMARY links implement the pillar; SECONDARY links enforce, validate, or monitor.”

- **Cross-refs:** Ensure the chapter text references “Diagram 8” and “Diagram 9” with these updated captions.

---

## H) Final sanity checklist
- [ ] Preface line appears **above** each of Tables 1–5.  
- [ ] `Source` column filled per table as mapped.  
- [ ] Governance callout added under **Common failures**.  
- [ ] Observability DoD box inserted under Pillar 5 metrics.  
- [ ] Semantic Drift SOP box inserted under Pillar 2.  
- [ ] Accessibility 2-second **table** replaces bullets.  
- [ ] Diagram captions confirmed and cross-refs updated.
