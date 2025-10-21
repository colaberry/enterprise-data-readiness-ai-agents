<artifact identifier="colaberry-codex-lean" type="application/vnd.ant.code" language="markdown" title="The Colaberry Codex (TCC) - Lean Edition">
# The Colaberry Codex (TCC) - Lean Edition

**Writing Standards for "Enterprise Data Readiness for AI Agents"**

Version 1.1.0 | October 21, 2025 | Ram Katamaraja, CEO Colaberry Inc.

---

## Core Principles (The Non-Negotiables)

1. **Evidence-based:** Major claims need citations <18 months old
2. **URLs:** Every product gets official URL on first mention
3. **Healthcare-only:** All examples use Meridian Health Systems
4. **No internal jargon:** Never use "VERT", "TCC", "Four-T" in reader content
5. **Standard terms:** Use exact terminology from glossary
6. **Healthcare context:** Patient (not customer), encounter (not transaction)
7. **Meridian consistency:** Use exact figures from canonical reference
8. **Chapter flow:** Every chapter connects to previous and bridges to next
9. **Cite visuals:** Reference all tables/diagrams with exact titles
10. **Current tech:** Indicate maturity status (production-ready/maturing/experimental)

---

## Section 1: Evidence & Attribution

### TCC-001: Evidence Required
Every statistic, benchmark, or best practice needs a citation.

**Needs citation:**
- "95% of GenAI projects fail" → cite MIT NANDA study
- "ABAC evaluation <10ms" → cite NIST documentation
- "Semantic layer improves accuracy 60% → 85%" → cite vendor case study

**No citation needed:**
- Colaberry's own frameworks (7-layer architecture, INPACT™)
- Narrative storytelling
- Explanations of already-cited concepts

**Citation age limits:**
- Statistics/research: <18 months (prefer <12)
- Technology: <12 months
- Regulations: Current version only

### TCC-002: Attribution Format
```markdown
"[Finding from source], [context]. [#]"

Example:
"MIT NANDA examined 300+ GenAI initiatives. Finding: 95% fail to achieve ROI. [1]"

References:
[1] Challapally, A., et al. (2025, July). "The GenAI Divide." MIT NANDA. [URL]
```

### TCC-003: Colaberry IP
Attribute our frameworks clearly:
```markdown
"Colaberry's 7-layer agent-ready data architecture addresses six capabilities..."
"Ram Katamaraja synthesized these patterns from 30 years of implementations..."
```

---

## Section 2: Terminology (Use Exactly)

### TCC-010: Standard Terms

**Architecture:**
- "7-layer agent-ready data architecture" (never "7-layer framework")
- "INPACT™" OR "Six Agent Capabilities" (never "six requirements")
- "Multi-agent orchestration" (never "agent coordination")

**Layers (use exact names):**
- L1: Real-Time Data Fabric
- L2: Unified Semantic Layer
- L3: Multi-Modal Storage
- L4: Intelligent Retrieval (RAG)
- L5: Agent-Aware Governance
- L6: Observability & Feedback
- L7: Self-Service Data Products & Multi-Agent Orchestration

### TCC-011: Forbidden Terms (Reader-Facing Content)
Never use in published chapters:
- ❌ "VERT Council" / "VERT Ethics Audit" / "VERT score"
- ❌ "Four-T framework" (Truth, Trust, Traction, Thread)
- ❌ "TCC-compliant" / "The Colaberry Codex"
- ❌ Any reviewer persona names

Use instead: "independent ethics review" or omit entirely

### TCC-012: Healthcare Terminology

| Use This | Never This |
|----------|------------|
| Patient | Customer, client |
| Encounter, visit, appointment | Transaction, order |
| Service, procedure | Product |
| Admissions, encounters | Revenue, sales |
| Provider, physician, clinician | Employee, staff |
| EHR (Electronic Health Record) | Patient database |
| PHI (Protected Health Information) | Sensitive data |

---

## Section 3: Examples & Case Studies

### TCC-020: Healthcare Context Only
ALL examples must use Meridian Health Systems. No retail, banking, or mixed industry examples.

❌ **WRONG:**
```
"When a customer adds items to cart (like a patient booking appointment)..."
```

✅ **CORRECT:**
```
"When a care coordinator asks 'Show me patients needing diabetes follow-up', 
the semantic layer translates to diagnosis codes E11.*, HbA1c > 7.0..."
```

### TCC-021: Meridian Canonical Reference
Use EXACT figures. Never round or approximate.

**Investment:** $1.23M (not ~$1.2M, not "about $1.2M")
**Duration:** 90 days (not "3 months", not "~90 days")
**Agents deployed:** 6 (not "several", not "multiple")
**ROI:** 477% (not "over 400%", not "~480%")
**Payback:** 10 weeks (not "about 3 months")
**Return:** $7.1M ($6.3M savings + $800K revenue)
**Start readiness:** 28/100 (BI-First archetype)
**End readiness:** 85/100
**SLOs:** Data freshness 25 seconds, NDCG 0.94, API availability 99.92%

Before writing Meridian example: Check these figures. Copy exactly. Never vary.

---

## Section 4: URLs & Citations

### TCC-030: URLs Required
Every product/technology needs official URL on first mention per chapter.

```markdown
✅ CORRECT:
[Pinecone](https://www.pinecone.io) is a managed vector database optimized 
for semantic search.

[Apache Kafka](https://kafka.apache.org) is an open-source distributed 
event streaming platform.
```

Even if URL in Chapter 1, provide again in Chapter 5 (readers may skip chapters).

### TCC-031: Multiple Options
Provide 2-3 examples per category, not just one vendor.

```markdown
✅ CORRECT:
"Vector databases include [Pinecone](url) (managed), [Weaviate](url) 
(open-source), and [Qdrant](url) (high-performance)."

❌ WRONG:
"Use Pinecone for vector database."
```

### TCC-032: URL Testing
Before publication:
- Click every URL (100%)
- No 404s allowed
- Mark paywalls: "(requires subscription)"
- Fix broken: Use web.archive.org or find replacement

---

## Section 5: Technology Guidance

### TCC-040: Selection Criteria
Never just recommend one tool. Show options, criteria, trade-offs.

**Pattern:**
```markdown
Vector Database Selection:

Options:
- [Pinecone](url): Managed, auto-scaling, higher cost
- [Weaviate](url): Self-hosted, flexible, ops overhead
- [Qdrant](url): High-performance, Rust-based, newer

Choose based on:
- Prioritize hands-off → Pinecone
- Prioritize flexibility → Weaviate
- Prioritize performance → Qdrant

Trade-offs:
- Managed: Easy but less control, higher cost
- Self-hosted: Control but ops complexity
- Performance: Fast but less mature ecosystem
```

### TCC-041: Version Neutrality
Avoid specific version numbers unless critical.

✅ "Use current stable release of Apache Kafka"
✅ "As of October 2025, Pinecone offers managed services..."
❌ "Install Apache Kafka v3.4.2"

### TCC-042: Technology Maturity Status
Indicate status clearly:

- **Production-ready:** LangGraph, CrewAI, AutoGen
- **Rapidly maturing:** MCP (mainstream adoption but requires security expertise)
- **Experimental:** Alpha releases, limited production use
- **Deprecated:** Avoid for new projects

For MCP (Oct 2025): Note mainstream adoption + security considerations required.

---

## Section 6: Visual Elements

### TCC-050: Diagrams Required
Complex concepts need diagrams:
- Multi-component architectures
- Process flows
- Comparisons (BI vs Agent)
- Relationships (entity resolution)

### TCC-051: Generic vs Specific
Use generic terms in diagrams UNLESS comparing specific vendors.

Generic: "Vector Database" → "Query Results" → "LLM"
Specific: Only when showing "Pinecone vs Weaviate vs Qdrant"

### TCC-052: Reference All Visuals
All diagrams and tables must be:
1. Numbered and titled
2. Referenced in text with exact title

```markdown
**Diagram 1: Seven-Layer Architecture**

[diagram content]

In text: "The seven-layer stack (Diagram 1: Seven-Layer Architecture) shows..."
```

---

## Section 7: Chapter Integration

### TCC-060: Opening Connection
Every chapter connects to previous:

```markdown
✅ CORRECT:
"Chapter 0 established that agents require six capabilities: sub-second response, 
natural language understanding, cross-domain context, dynamic authorization, 
continuous learning, trustability.

The question becomes: What architecture delivers all six?

This chapter presents the answer..."
```

### TCC-061: Bridge to Next
Every chapter ends with explicit bridge:

```markdown
Template:
In [current chapter], we [established] [key points].

[Next chapter] builds on this by [what's next].

[Transition question creating momentum]

Let's [action verb] [topic]...
```

### TCC-062: No Contradictions
- Same terminology across all chapters
- Same Meridian figures across all chapters
- Same framework names (established in Ch 0/1)
- No conflicting statistics

---

## Section 8: Voice & Audience

### TCC-070: Professional but Accessible
Target: CDOs, CTOs, VPs Data, Data Architects

✅ **Good:**
```
"Your data systems were built for patience. Overnight batch jobs. Queries 
taking 9-13 seconds. That worked when humans analyzed reports over coffee. 
It fails when agents must respond at conversation speed."
```

❌ **Too academic:**
```
"Contemporary enterprise data architectures exhibit temporal latency 
characteristics incompatible with real-time agentic requirements..."
```

❌ **Too casual:**
```
"So your data warehouse is like, totally not ready for AI, right? LOL 🚀"
```

### TCC-071: Acronyms
Define on first use per chapter. Add acronym list at chapter end.

```markdown
First use: "Attribute-Based Access Control (ABAC) evaluates..."
Later: "The ABAC policy engine..."

Chapter end:
## Acronyms
- ABAC: Attribute-Based Access Control
- CDC: Change Data Capture
- RAG: Retrieval-Augmented Generation
```

---

## Pre-Publication Checklist

Run this before EVERY chapter submission:

**Critical (Must Pass):**
- [ ] All major claims have citations <18 months old
- [ ] Every product has URL on first mention
- [ ] All examples use healthcare (Meridian)
- [ ] No VERT/TCC/internal jargon in reader content
- [ ] Terminology matches TCC glossary exactly
- [ ] Meridian figures match canonical reference (see TCC-021)
- [ ] Chapter connects to previous and bridges to next
- [ ] All tables/diagrams numbered, titled, referenced in text

**High Priority:**
- [ ] URLs tested (no 404s)
- [ ] Product categories have 2-3 examples
- [ ] Technology includes selection criteria + trade-offs
- [ ] Acronyms defined first use
- [ ] No retail/banking/mixed examples

**Medium Priority:**
- [ ] Complex concepts have diagrams
- [ ] Diagrams use generic terms (unless comparing vendors)
- [ ] Spell check + grammar check complete

**Status:** [ ] PASS / [ ] FAIL

---

## Quick Reference: Common Patterns

**Product with URL:**
```markdown
[Product Name](https://official-url.com) - Brief description
```

**Citation:**
```markdown
"[Finding]. [Context]. [#]"
```

**Technology selection:**
```markdown
Options: [A](url) (use case), [B](url) (use case), [C](url) (use case)
Choose based on: Priority X → A, Priority Y → B
Trade-offs: A pros/cons, B pros/cons
```

**Chapter bridge:**
```markdown
In [current], we [accomplished]. [Next] builds on this by [what's next]. 
[Question]. Let's [action]...
```

---

## LLM Self-QA Protocol

**Before delivering content, verify:**

1. Claims have citations? (TCC-001)
2. Products have URLs? (TCC-030)
3. Examples healthcare only? (TCC-020)
4. No VERT/TCC terms? (TCC-011)
5. Terminology matches glossary? (TCC-010)
6. Meridian figures exact? (TCC-021)
7. Chapter connects to previous? (TCC-060)
8. Bridges to next? (TCC-061)

If ANY fail: Fix before delivery. Note corrections made.

**Compliance Score:** [X]/8

- 8/8: ✅ Excellent, proceed
- 6-7/8: ⚠️ Acceptable, note gaps
- <6/8: ❌ Revise before delivery

---

## Priority Hierarchy (When Rules Conflict)

**Critical (Never Violate):**
- Evidence-based (TCC-001)
- URLs for products (TCC-030)
- Citation currency (TCC-001)
- Healthcare-only examples (TCC-020)
- Meridian canonical consistency (TCC-021)
- No internal jargon (TCC-011)
- Standard terminology (TCC-010)
- Chapter integration (TCC-060, TCC-061)

**High (Strongly Follow):**
- Multiple product examples (TCC-031)
- Selection criteria (TCC-040)
- Visual references (TCC-052)
- Audience voice (TCC-070)

**Medium (Important):**
- Diagram completeness (TCC-050)
- Acronym management (TCC-071)
- Version neutrality (TCC-041)

---

## Rule Index (Alphabetical)

- TCC-001: Evidence Required
- TCC-002: Attribution Format
- TCC-003: Colaberry IP
- TCC-010: Standard Terms
- TCC-011: Forbidden Terms
- TCC-012: Healthcare Terminology
- TCC-020: Healthcare Context Only
- TCC-021: Meridian Canonical Reference
- TCC-030: URLs Required
- TCC-031: Multiple Options
- TCC-032: URL Testing
- TCC-040: Selection Criteria
- TCC-041: Version Neutrality
- TCC-042: Technology Maturity
- TCC-050: Diagrams Required
- TCC-051: Generic vs Specific
- TCC-052: Reference All Visuals
- TCC-060: Opening Connection
- TCC-061: Bridge to Next
- TCC-062: No Contradictions
- TCC-070: Professional Voice
- TCC-071: Acronyms

---

**END OF TCC LEAN EDITION**

Total: 22 rules (vs 35 in bloated version)
Length: ~2,500 words (vs 15,000)
Usability: 10x better

---

© 2025 Colaberry Inc.