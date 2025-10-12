# Chapter 2: Tables Reference

This document contains all tables from Chapter 2 for easy reference and use.

---

## Table 1: Accessibility Metrics Dashboard

**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.

| Metric | Definition | Target | Measurement Method | Source |
|--------|------------|--------|-------------------|--------|
| **Query latency (p95)** | 95th percentile time from query to data returned | <200ms | APM tools (DataDog, New Relic), custom telemetry | Internal SRE best practices |
| **Data freshness** | Time elapsed since last update | <60s (operational), <15min (analytical) | Timestamp comparison in Layer 6 | NIST CSF |
| **API availability** | Uptime percentage for data endpoints | 99.9% (< 43min downtime/month) | Health checks, synthetic monitoring | NIST CSF |
| **Query success rate** | % of queries returning valid results | >95% | Success/failure logging in Layer 6 | Internal SRE best practices |
| **Time-to-first-byte (TTFB)** | Initial response latency | <50ms | Network monitoring tools | Internal SRE best practices |
| **Cache hit rate** | % of queries served from cache | >70% | Cache telemetry (Redis Insights) | Internal SRE best practices |
| **Parallel retrieval efficiency** | Speedup from parallel queries | >2x (for 3+ sources) | Custom instrumentation | Internal SRE best practices |

---

## Table 2: Semantic Richness Metrics Dashboard

**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.

| Metric | Definition | Target | Measurement Method | Source |
|--------|------------|--------|-------------------|--------|
| **Concept coverage** | % of domain concepts with formal definitions | >85% | Audit of business glossary vs. actual data usage | ISO/IEC 25012 |
| **Query understanding accuracy** | % of NL queries correctly mapped to data | >90% | Manual review of query translations + user feedback | Internal validation |
| **Disambiguation success rate** | % of ambiguous terms correctly resolved by context | >80% | Analysis of multi-meaning terms | ISO/IEC 25012 |
| **Cross-system entity resolution** | % of entities unified across systems | >95% (critical entities) | Entity linkage audit | ISO/IEC 25012 |
| **Metric consistency** | % of metrics with single source of truth definition | 100% (critical metrics) | Metric definition inventory and duplication check | ISO/IEC 25012 |
| **Semantic drift detection** | Time to identify new terminology not in glossary | <1 week | Automated term extraction from queries + manual review | Evidently AI |
| **Natural language coverage** | % of common user phrases mapped to queries | >75% | Analysis of query logs for unmapped phrases | Internal validation |

---

## Table 3: Quality & Trust Metrics Dashboard

**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.

| Metric | Definition | Target | Measurement Method | Source |
|--------|------------|--------|-------------------|--------|
| **Data freshness (SLA compliance)** | % of data sources meeting freshness SLAs | >99% | Timestamp monitoring (Layer 6) | NIST CSF |
| **Completeness rate** | % of required fields populated | >98% (critical fields) | Automated validation (Great Expectations) | ISO/IEC 25012, Great Expectations |
| **Accuracy score** | % of values passing validation rules | >95% | Business rule validation, statistical checks | ISO/IEC 25012, Great Expectations |
| **Schema drift incidents** | Breaking schema changes per month | <1 | Automated schema monitoring (Layer 6) | NIST CSF |
| **Data quality incidents** | Quality issues detected per week | <5 | Observability platform alerts | NIST CSF |
| **Mean time to detect (MTTD)** | Average time to discover quality issues | <15 minutes | Monitoring lag from issue to alert | NIST CSF |
| **Mean time to resolve (MTTR)** | Average time to fix quality issues | <2 hours | Incident resolution tracking | NIST CSF |
| **Audit coverage** | % of data access logged for compliance | 100% (sensitive data) | Audit log completeness checks | NIST CSF |
| **Lineage completeness** | % of data with documented origin | >90% (critical data) | Lineage graph completeness | ISO/IEC 25012 |

---

## Table 4: Governance & Security Metrics Dashboard

**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.

| Metric | Definition | Target | Measurement Method | Source |
|--------|------------|--------|-------------------|--------|
| **Policy evaluation latency** | Time to evaluate ABAC policies | <10ms (p95) | Authorization engine telemetry | Open Policy Agent |
| **Audit log completeness** | % of data access events logged | 100% (sensitive data) | Audit log validation | NIST CSF |
| **Compliance policy coverage** | % of compliance requirements automated | >95% | Policy inventory vs. requirements | NIST CSF |
| **Data masking accuracy** | % of sensitive fields correctly masked | 100% | Masking validation tests | Open Policy Agent |
| **Permission violations detected** | Unauthorized access attempts per month | 0 | Security monitoring alerts | NIST CSF |
| **Mean time to policy update** | Time from requirement to policy deployment | <24 hours | Policy change tracking | Open Policy Agent |
| **Audit query performance** | Time to retrieve audit trail for investigation | <5 seconds | Audit system performance | NIST CSF |

---

## Table 5: Observability Metrics Dashboard

**Default SLOs.** The thresholds below are production-proven starting points. **Tune by domain and risk tolerance** and **document rationale** for any deviations. Each SLO must be **monitored and alerted**, with a quarterly review.

| Metric | Definition | Target | Measurement Method | Source |
|--------|------------|--------|-------------------|--------|
| **Monitoring coverage** | % of critical metrics being tracked | >95% | Inventory of metrics vs. monitored | NIST CSF |
| **Mean time to detect (MTTD)** | Average time from issue to detection | <15 minutes | Incident timeline analysis | NIST CSF |
| **Mean time to resolve (MTTR)** | Average time from detection to resolution | <2 hours | Incident resolution tracking | NIST CSF |
| **Alert accuracy (precision)** | % of alerts that are true positives | >85% | False positive rate analysis | NIST CSF |
| **Feedback loop speed** | Time from issue detection to improvement deployed | <1 week | Change deployment tracking | Internal practices |
| **Cost per query** | LLM + infrastructure cost per agent query | <$0.01 (target varies) | Cost telemetry aggregation | Internal practices |
| **Retrieval quality (NDCG)** | Normalized discounted cumulative gain for retrieved results | >0.85 | Offline evaluation dataset | Evidently AI |
| **Model drift detection** | Time to detect semantic/statistical drift | <1 week | Automated drift monitoring | Evidently AI |

---

## Table 6: Pillar-to-Layer Mapping Matrix

**Visual version:** See Diagram 9 (Pillar-Layer Mapping) for graphical representation of this matrix. The diagram uses thick lines for PRIMARY connections and thin dotted lines for SECONDARY connections.

**How to use this table with Diagram 9:**
1. Identify your weakest pillar (from assessment)
2. Find that pillar's row in this table OR that pillar's node in Diagram 9
3. Look for 🔴 PRIMARY markers (table) or thick lines (diagram)
4. Those layers are your implementation priorities

| Layer | Accessibility (1) | Semantic Richness (2) | Quality & Trust (3) | Governance (4) | Observability (5) |
|-------|------------------|----------------------|-------------------|----------------|-------------------|
| **Layer 1: Real-Time Fabric** | 🔴 PRIMARY<br/>Freshness <60s | ⚪ Not directly | 🟡 SECONDARY<br/>Pipeline reliability | ⚪ Not directly | 🟡 SECONDARY<br/>Monitor pipeline health |
| **Layer 2: Semantic Layer** | 🟡 SECONDARY<br/>Query understanding | 🔴 PRIMARY<br/>Definitions, ontologies | 🟡 SECONDARY<br/>Validation rules | 🟡 SECONDARY<br/>Data classification | 🟡 SECONDARY<br/>Semantic drift detection |
| **Layer 3: Multi-Modal Storage** | 🔴 PRIMARY<br/>Optimized retrieval | ⚪ Not directly | 🟡 SECONDARY<br/>Storage reliability | ⚪ Not directly | 🟡 SECONDARY<br/>Storage performance metrics |
| **Layer 4: RAG Infrastructure** | 🔴 PRIMARY<br/>Caching, parallelization | 🔴 PRIMARY<br/>NL understanding | 🟡 SECONDARY<br/>Result quality scoring | ⚪ Not directly | 🟡 SECONDARY<br/>Retrieval quality metrics |
| **Layer 5: Governance** | ⚪ Not directly | ⚪ Not directly | 🟡 SECONDARY<br/>Audit trails | 🔴 PRIMARY<br/>ABAC, masking, audit | 🟡 SECONDARY<br/>Policy evaluation metrics |
| **Layer 6: Observability** | 🟡 SECONDARY<br/>Latency monitoring | 🟡 SECONDARY<br/>Drift detection | 🔴 PRIMARY<br/>Data quality monitoring | 🟡 SECONDARY<br/>Governance auditing | 🔴 PRIMARY<br/>All monitoring & feedback |
| **Layer 7: Data Products** | 🟡 SECONDARY<br/>Self-service APIs | 🟡 SECONDARY<br/>Product documentation | 🟡 SECONDARY<br/>SLAs & quality guarantees | 🟡 SECONDARY<br/>Product-level policies | 🟡 SECONDARY<br/>Usage & cost tracking |

**Legend:**
- 🔴 PRIMARY: Layer is critical for this pillar, core implementation
- 🟡 SECONDARY: Layer supports this pillar, enhancing or monitoring
- ⚪ Not directly: Layer doesn't directly implement this pillar

---

## Table 7: Pillar Assessment Scoring Rubric

| Score Range | Percentage | Status | Visual | Action Required |
|-------------|-----------|--------|--------|-----------------|
| 0-12 | 0-20% | CRITICAL | 🔴 | Immediate attention, agent will fail. Highest priority. |
| 13-24 | 21-40% | POOR | 🟠 | Significant work needed, agents at risk of failure. |
| 25-36 | 41-60% | FAIR | 🟡 | Foundation exists, needs strengthening before production. |
| 37-48 | 61-80% | GOOD | 🟢 | Minor improvements needed, production-ready with monitoring. |
| 49-60 | 81-100% | EXCELLENT | ✅ | Maintain and optimize continuously. |

**Overall Assessment (Average of 5 pillars):**

| Overall % | Agent Readiness Status | Recommendation |
|-----------|----------------------|----------------|
| 0-20% | Not ready | Delay agent projects, build foundations first |
| 21-40% | High risk | Proceed cautiously with pilots, expect failures |
| 41-60% | Moderate risk | Pilot projects only, improve pillars in parallel |
| 61-80% | Agent-ready | Production agents feasible with active monitoring |
| 81-100% | Highly optimized | Deploy confidently, industry-leading capability |

---

## Table 8: Common Pillar Violations & Fixes

| Pillar | Violation | Symptom | Root Cause | Fix | Timeline |
|--------|----------|---------|-----------|-----|----------|
| **Accessibility** | Batch ETL bottleneck | Agent can't answer "current" questions accurately | Overnight ETL creates 8-24 hour data lag | Implement CDC and streaming (Layer 1) | 2-4 weeks |
| **Accessibility** | No caching strategy | Query latency 5-8 seconds under load | Every query hits database | Implement semantic caching (Layer 4) | 1-2 weeks |
| **Accessibility** | Sequential processing | Agent takes 3+ seconds for multi-source queries | Agent waits for each source sequentially | Parallel retrieval (Layer 4) | 1 week |
| **Semantic Richness** | Cryptic table names | Agent can't understand "patient" stored as FCT_PTNT_ENCT | Technical names not mapped to business concepts | Build business glossary (Layer 2) | 2-4 weeks |
| **Semantic Richness** | Inconsistent terminology | "Customer" means different things in different systems | No unified entity resolution | Create MDM or identity graph (Layer 2 + 1) | 8-12 weeks |
| **Semantic Richness** | No metric definitions | "Revenue" calculated differently everywhere | No single source of truth for metrics | Define metrics in semantic layer (Layer 2) | 2-3 weeks |
| **Quality & Trust** | Stale data undetected | Agent gives confident answers on outdated info | No freshness monitoring | Add freshness monitoring with SLA alerts (Layer 6) | 1-2 weeks |
| **Quality & Trust** | Missing required fields | Agent responds "I don't have that information" frequently | No data completeness validation | Add validation at ingestion (Great Expectations) | 2-3 weeks |
| **Quality & Trust** | Inconsistent data | Agent gives contradictory answers from different systems | Same entity, different values, no reconciliation | Implement data reconciliation rules (Layer 1 + 2) | 4-6 weeks |
| **Governance** | Static RBAC | Agent has overly broad permissions, users see wrong data | Single service account with static permissions | Replace with ABAC (Layer 5) | 4-6 weeks |
| **Governance** | Incomplete audit trails | Can't answer "Who accessed this data?" during audit | Audit logs don't capture user attribution | Enhance audit logging with user context (Layer 5) | 2-3 weeks |
| **Governance** | No data classification | Sensitive data treated same as public data | No systematic classification by sensitivity | Classify data, tag tables/columns (Layer 5 + 2) | 3-4 weeks |
| **Observability** | No proactive monitoring | Issues discovered only when users complain | No automated monitoring or alerting | Implement monitoring dashboard with alerts (Layer 6) | 3-4 weeks |
| **Observability** | Siloed metrics | Teams can't correlate issues across layers | Metrics in separate systems, no unified view | Deploy unified observability platform | 2-3 weeks |
| **Observability** | No model monitoring | Agent performance degrades without obvious cause | No monitoring of embedding drift, LLM quality | Add ML observability (Arize, Evidently) | 3-4 weeks |

---

## Table 9: Pillar Prioritization Guide

### Recommended Priority Order for Most Organizations

| Phase | Priority | Pillar | Rationale | Typical Duration |
|-------|----------|--------|-----------|------------------|
| **Phase 1** | 1 | Observability (Pillar 5) | Can't improve what you can't see. Foundation for all improvements. | Weeks 1-4 |
| **Phase 1** | 2 | Governance (Pillar 4) | Compliance is non-negotiable. Legal/regulatory risk must be addressed early. | Weeks 1-4 |
| **Phase 1** | 3 | Quality & Trust (Pillar 3) | Bad data = bad agents. Must fix data quality before agents can be accurate. | Weeks 1-4 |
| **Phase 2** | 4 | Accessibility (Pillar 1) | Users need fast responses. Performance directly impacts adoption. | Weeks 5-8 |
| **Phase 2** | 5 | Semantic Richness (Pillar 2) | Agents need to understand queries. Improves accuracy and user experience. | Weeks 5-8 |

### Alternative Priority (If Governance Already Strong)

| Phase | Priority | Pillar | Use When |
|-------|----------|--------|----------|
| 1 | Observability | Existing compliance programs, strong governance foundation |
| 2 | Quality & Trust | Already have RBAC, audit trails, just need ABAC refinement |
| 3 | Accessibility | Governance can be enhanced later (weeks 7-8) |
| 4 | Semantic Richness | Focus on performance and understanding first |
| 5 | Governance (refinement) | Upgrade RBAC to ABAC after core agent capabilities proven |

---

## Table 10: Meridian's Pillar Assessment Journey

### Initial Assessment (Before 90-Day Acceleration)

| Pillar | Score | Percentage | Status | Key Weaknesses |
|--------|-------|-----------|---------|----------------|
| Accessibility | 18/60 | 30% | 🟠 POOR | Batch ETL (24hr lag), slow queries (6s), no caching |
| Semantic Richness | 14/60 | 23% | 🟠 POOR | Cryptic names (FCT_PTNT_ENCT), no glossary, 18-month-old docs |
| Quality & Trust | 28/60 | 47% | 🟡 FAIR | Good governance but no real-time monitoring, reactive only |
| Governance | 16/60 | 27% | 🟠 POOR | Static RBAC, broad service account, incomplete audit logs |
| Observability | 8/60 | 13% | 🔴 CRITICAL | No monitoring, no alerts, blind to issues |
| **OVERALL** | **84/300** | **28%** | **HIGH RISK** | **Not ready for production agents** |

### After 90-Day Acceleration

| Pillar | Score | Percentage | Status | Key Improvements | Improvement |
|--------|-------|-----------|---------|------------------|-------------|
| Accessibility | 52/60 | 87% | ✅ EXCELLENT | CDC (<30s freshness), vector DB (180ms), caching (82% hit rate) | +57% |
| Semantic Richness | 48/60 | 80% | ✅ EXCELLENT | Business glossary (85% coverage), NL mappings, drift detection | +57% |
| Quality & Trust | 54/60 | 90% | ✅ EXCELLENT | Real-time monitoring, MTTD <12min, proactive validation | +43% |
| Governance | 50/60 | 83% | ✅ EXCELLENT | ABAC implemented (<6ms latency), complete audit trails, HIPAA compliant | +56% |
| Observability | 54/60 | 90% | ✅ EXCELLENT | Comprehensive monitoring (96% coverage), feedback loops (4-day avg) | +77% |
| **OVERALL** | **258/300** | **86%** | **HIGHLY OPTIMIZED** | **Production-ready, 6 agents deployed successfully** | **+58%** |

### 6-Month Maintenance (Continuous Monitoring)

| Pillar | Score | Percentage | Status | Notes |
|--------|-------|-----------|---------|-------|
| Accessibility | 52/60 | 87% | ✅ EXCELLENT | Maintained, latency 1.8s stable |
| Semantic Richness | 50/60 | 83% | ✅ EXCELLENT | +2 points from ongoing glossary updates |
| Quality & Trust | 56/60 | 93% | ✅ EXCELLENT | +2 points from improved validation |
| Governance | 52/60 | 87% | ✅ EXCELLENT | +2 points from policy refinements |
| Observability | 56/60 | 93% | ✅ EXCELLENT | +2 points from expanded coverage |
| **OVERALL** | **266/300** | **89%** | **HIGHLY OPTIMIZED** | **Continuous improvement culture** |

---

## Usage Guide for These Tables

**For assessment:**
1. Use Tables 1-5 to understand what metrics to track for each pillar
2. Use the self-assessment questions in Chapter 2 to calculate your scores
3. Use Table 7 to interpret your scores and determine readiness

**For planning:**
4. Use Table 6 to understand which layers to prioritize for each pillar
5. Use Table 8 to identify which common violations apply to your situation
6. Use Table 9 to determine priority order for your pillar improvements

**For benchmarking:**
7. Use Table 10 to compare your organization to Meridian's journey
8. Track your progression monthly using the same scoring methodology

**For communication:**
9. Use these tables in executive presentations to show objective readiness
10. Include pillar scores in monthly/quarterly data strategy reviews

---

**End of Tables Reference Document**