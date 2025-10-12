# VERT Transparency Ledger Template (v3.1)

This ledger records all external and internal feedback events, verification actions, and Council dispositions, as required by **Article 10 — External Intelligence Feedback Protocol** and **Article 1.3 — Timeliness & Temporal Validity**.

## How to Use
1. **Create one entry per event** (feedback, correction, verification, audit).
2. **Always include verification date** and cite the **authoritative sources** checked.
3. **Map the event to the 4T dimensions**: Truth, Trust, Traction, Thread.
4. **Disposition** must include whether adopted/rejected/partial, with rationale.
5. **Link artifacts** (PRs, docs, appendix pages) that changed as a result.

---

## Ledger Fields (schema)
- **ID**: Unique identifier (e.g., VERT-2025-001)
- **Date Reported**: YYYY-MM-DD
- **Source**: Person/Org/AI (e.g., Claude, Council Member, Reader)
- **Contact/Link**: URL or reference
- **Dimension(s)**: Truth / Trust / Traction / Thread
- **Category**: Narrative | Temporal | Technical | Compliance | ROI | Other
- **Summary**: 1–3 sentences
- **Evidence / Citations**: URLs, titles, or document references
- **Verification Date**: YYYY-MM-DD
- **Verification Actions**: What was checked (search queries, docs reviewed)
- **Custodian(s)**: Assigned VERT roles
- **Disposition**: Adopted | Partial | Rejected
- **Rationale**: Why this disposition
- **Changes Made**: File names, versions, PR links
- **Next Review**: Date or “N/A”

---

## Markdown Table (copy rows as needed)

| ID | Date Reported | Source | Dimension(s) | Category | Summary | Evidence / Citations | Verification Date | Verification Actions | Custodian(s) | Disposition | Rationale | Changes Made | Next Review |
|----|----------------|--------|--------------|----------|---------|----------------------|-------------------|----------------------|--------------|-------------|-----------|--------------|-------------|
| VERT-2025-001 | 2025-10-07 | Claude (AI Reviewer) | Truth, Thread | Narrative, Temporal | Noted context switches (healthcare→retail/banking) and outdated MCP status in Ch.1 v2.1 | Links to memo + vendor docs | 2025-10-11 | Searched latest MCP adoption & security reports; reviewed Ch.1 examples | Architect, Cartographer | Adopted | Added Art. 1.3 (Timeliness) & Art. 10 (Feedback); planned v3.1 | Updated Ch.1 v2.1.1; Issued VERT v3.1 | 2026-01-15 |

---

## Log Notes
- Use ISO dates.  
- Keep summaries concise; attach evidence where possible.  
- Prefer **public, authoritative** sources for verification.  
- Cross-link to the **Trust-Audit Reports** when relevant.
