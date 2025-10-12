# Chapter 1: Comprehensive Reference Tables

**Book:** Enterprise Data Readiness for AI Agents  
**Chapter:** 1 - The 7-Layer Agent-Ready Data Architecture  
**Version:** 2.1.1 (Consistency Corrections Applied)  
**Document Type:** Supplementary Tables and Matrices  
**Last Updated:** October 11, 2025

---

## Table of Contents

1. [Table 1: Layer-to-Requirement Mapping](#table-1-layer-to-requirement-mapping)
2. [Table 2: BI Systems vs Agent Systems (Extended)](#table-2-bi-systems-vs-agent-systems-extended)
3. [Table 3: Investment by Company Size](#table-3-investment-by-company-size)
4. [Table 4: ROI Scenarios](#table-4-roi-scenarios)
5. [Table 5: Enterprise Archetype Comparison](#table-5-enterprise-archetype-comparison)
6. [Table 6: Readiness Self-Assessment Scoring](#table-6-readiness-self-assessment-scoring)
7. [Table 7: Multi-Agent Orchestration Framework Comparison](#table-7-multi-agent-orchestration-framework-comparison)
8. [Table 8: Embedding Model Selection Matrix](#table-8-embedding-model-selection-matrix)
9. [Table 9: Data Quality Metrics & SLAs](#table-9-data-quality-metrics-slas)
10. [Table 10: VERT Scoring Summary](#table-10-vert-scoring-summary)

---

## Table 1: Layer-to-Requirement Mapping

**Purpose:** Shows how each of the 7 layers addresses the 6 agent requirements

| Requirement | Layer 1 | Layer 2 | Layer 3 | Layer 4 | Layer 5 | Layer 6 | Layer 7 |
|-------------|---------|---------|---------|---------|---------|---------|---------|
| **Sub-second response** | ✅ Real-time data | ⚠️ Semantic lookup | ✅ Optimized storage | ✅ Caching, parallel retrieval | ⚠️ Fast ABAC | ✅ Performance monitoring | ✅ Multi-agent parallelization |
| **Natural language** | - | ✅ NL mappings | ⚠️ Semantic search | ✅ RAG, embeddings | - | - | ✅ Self-service discovery |
| **Cross-domain context** | ✅ Unified sources | ✅ Entity resolution | ✅ Multi-modal queries | ✅ Context assembly | ⚠️ Cross-domain ABAC | - | ✅ Domain specialists |
| **Dynamic authorization** | - | - | - | - | ✅ ABAC, masking | ✅ Audit trails | ✅ Per-agent permissions |
| **Continuous learning** | ✅ Fresh training data | ⚠️ Semantic drift detection | ✅ Model registry | ✅ Retrieval quality metrics | - | ✅ Feedback loops, retraining | ✅ Orchestration optimization |
| **Trustability** | ✅ Data lineage | ✅ Business rule transparency | ✅ Model versioning | ✅ Citation, confidence scores | ✅ Audit logs | ✅ Full tracing | ✅ Multi-agent decision logs |

**Legend:**
- ✅ Primary contributor to this requirement
- ⚠️ Supporting contributor
- `-` Not directly relevant

---

## Table 2: BI Systems vs Agent Systems (Extended)

**Purpose:** Comprehensive comparison showing architectural implications

| Dimension | BI Systems | Agent Systems | Primary Architecture Impact |
|-----------|------------|---------------|----------------------------|
| **Response time** | Minutes to hours | <2s (simple), <3s (multi-agent) | Layer 1 (streaming), Layer 4 (caching), Layer 7 (parallelization) |
| **Data freshness** | Daily/weekly batch | Sub-minute real-time | Layer 1 (CDC, Kafka) |
| **Query patterns** | Known, predefined | Unpredictable, NL | Layer 2 (semantic), Layer 4 (RAG) |
| **User interface** | Visual dashboards | Conversational text | Layer 2 (NL understanding), Layer 4 (embeddings) |
| **Decision maker** | Human analyst | Autonomous agent(s) | Layer 5 (ABAC), Layer 6 (trust), Layer 7 (orchestration) |
| **Access control** | Static RBAC | Dynamic ABAC | Layer 5 (real-time policy evaluation) |
| **Data types** | Primarily structured | Structured + unstructured | Layer 3 (vector DB, knowledge graphs) |
| **Query complexity** | Aggregations, joins | Semantic search, reasoning | Layer 3 (multi-modal), Layer 4 (RAG), Layer 7 (specialists) |
| **Feedback loops** | Periodic reviews | Continuous, automated | Layer 6 (observability, model retraining) |
| **Auditability** | Quarterly reports | Every query logged | Layer 5 (audit logs), Layer 6 (trace IDs) |
| **Scale** | Hundreds of users | Millions of queries | Layer 7 (self-service, APIs) |
| **Failure impact** | User retries | User abandons | Layer 6 (reliability monitoring) |
| **Data discovery** | Analyst knows location | Agent discovers dynamically | Layer 7 (catalog, data products) |
| **Performance optimization** | Query tuning, indexes | Caching, reranking, embedding optimization | Layer 4 (RAG optimization) |
| **Cost model** | Infrastructure + licenses | Per-query LLM + infrastructure | Layer 6 (cost tracking) |
| **Model management** | N/A | Embeddings, LLMs versioned | Layer 3 (model registry), Layer 6 (drift detection) |
| **Development speed** | Months per report | Days per agent (once ready) | All 7 layers enable rapid development |
| **Error handling** | Manual investigation | Automated fallbacks | Layer 4 (confidence), Layer 7 (graceful degradation) |
| **Context window** | N/A (visual display) | 8K-200K tokens | Layer 4 (context assembly) |
| **Personalization** | Filters/parameters | Dynamic per user | Layer 5 (ABAC, masking) |

---

## Table 3: Investment by Company Size

**Purpose:** Budget estimates for 90-day agent-ready transformation

| Cost Category | Small (1K employees) | Mid-size (10K employees) | Large (50K+ employees) |
|---------------|---------------------|--------------------------|------------------------|
| **Infrastructure (30-35%)** | $75K-$150K | $200K-$350K | $400K-$750K |
| - Real-time streaming | $15K-$30K | $40K-$70K | $80K-$150K |
| - Vector database | $10K-$25K | $30K-$60K | $60K-$120K |
| - Knowledge graph | $10K-$20K | $30K-$50K | $60K-$100K |
| - Model registry | $5K-$15K | $20K-$40K | $40K-$80K |
| - Semantic layer | $15K-$30K | $40K-$70K | $80K-$150K |
| - Observability | $10K-$20K | $30K-$50K | $60K-$120K |
| - Orchestration | $10K-$10K | $10K-$10K | $20K-$30K |
| **Labor (50-60%)** | $180K-$350K | $400K-$800K | $800K-$1.5M |
| - Data architect | $45K | $45K | $45K-$90K |
| - Senior data engineers (2-4) | $68K-$136K | $136K-$272K | $272K-$544K |
| - ML engineers (1-2) | $36K-$72K | $72K-$144K | $144K-$288K |
| - Governance specialist | $16K | $16K-$32K | $32K-$64K |
| - Project manager | $17K | $17K-$34K | $34K-$68K |
| **Vendors/Licensing (10-15%)** | $30K-$70K | $80K-$200K | $150K-$400K |
| **Contingency (10%)** | $29K-$57K | $68K-$135K | $135K-$265K |
| **TOTAL (90 days)** | **$314K-$627K** | **$748K-$1.49M** | **$1.49M-$2.92M** |

**Notes:**
- Ranges reflect build vs. buy decisions (open source vs. commercial)
- Labor costs assume US market rates (Q4 2024)
- Infrastructure costs are annualized, then divided by 4 for 90-day period
- Actual costs vary by region, existing infrastructure, and team capability

---

## Table 4: ROI Scenarios

**Purpose:** Expected returns for mid-size company with $1.2M investment

| Scenario | Agents Deployed (Year 1) | Operational Savings | New Revenue | Total Return | ROI | Payback Period |
|----------|--------------------------|---------------------|-------------|--------------|-----|----------------|
| **Conservative** | 2 | $2.5M | $0 | $2.5M | 108% | 6 months |
| **Moderate** | 5 | $4.2M | $600K | $4.8M | 300% | 3 months |
| **Aggressive** | 8 | $6.5M | $1.7M | $8.2M | 583% | 2 months |
| **Meridian Actual** | 6 | $6.3M | $800K | $7.1M | 477% | 2.5 months |

**Conservative Assumptions:**
- 2 agents: customer service automation, documentation assistance
- Operational savings: $1.25M per agent per year
- No new revenue (cost reduction only)
- Year 1 only; compounds in years 2-3

**Moderate Assumptions:**
- 5 agents across high-value processes
- $840K average savings per agent
- New revenue: AI-powered product feature ($600K)
- Realistic for well-executed projects

**Aggressive Assumptions:**
- 8 agents deployed rapidly (reusing infrastructure)
- Mix of high-value and quick-win use cases
- New revenue stream enabled by agent capabilities
- Requires strong executive support

**Meridian Actual Results (18 months):**
- 6 agents: scheduling, documentation, insurance, care coordination, supply, triage
- Direct savings: $6.3M
- New product: AI patient engagement tool ($800K revenue)
- Total: $7.1M return on $1.23M investment

---

## Table 5: Enterprise Archetype Comparison

**Purpose:** Starting point assessment for different organization types

| Archetype | % of Orgs | Starting Readiness | Timeline to Ready | Investment Range | Primary Gaps | Key Advantages |
|-----------|-----------|-------------------|-------------------|------------------|--------------|----------------|
| **BI-First** | 60% | 25-35/100 | 90-120 days | $750K-$1.5M | Layers 1,3,4,6 (real-time, RAG, observability) | Strong governance, clean data, SQL expertise |
| **Data Lake** | 20% | 20-30/100 | 75-100 days | $700K-$1.4M | Layers 2,4,5,6,7 (semantic, RAG, governance, products) | Scale, Python/Spark skills, cloud-native |
| **ML-First** | 15% | 40-50/100 | 60-90 days | $600K-$1.2M | Layers 2,4,7 (semantic for NL, RAG, orchestration) | Real-time mindset, feature stores, MLOps culture |
| **Data Mesh** | 3% | 55-65/100 | 45-75 days | $500K-$1M | Layers 3,4,6 (multi-modal storage, RAG, observability) | Domain ownership, data products, federated model |
| **Greenfield** | 2% | 35-45/100 | 60-90 days | $400K-$900K | Layers 5,6,7 (governance at scale, observability, products) | No legacy debt, modern stack, agile culture |

**Readiness Scoring (0-100 scale):**
- 0-20: Not started, no relevant infrastructure
- 21-40: Basic foundations, major gaps
- 41-60: Partial readiness, significant work needed
- 61-80: Most components present, refinement needed
- 81-100: Agent-ready, minor optimizations only

---

## Table 6: Readiness Self-Assessment Scoring

**Purpose:** Quick self-evaluation tool (20 questions, 5 points each)

| Layer | Question | Score If "Yes" (5 pts) |
|-------|----------|----------------------|
| **Layer 1** | Do you have real-time streaming (CDC) from key operational databases? | 5 |
| **Layer 1** | Is your data freshness typically <5 minutes for critical sources? | 5 |
| **Layer 2** | Do you have a semantic layer that maps business terms to data structures? | 5 |
| **Layer 2** | Can non-technical users query data using natural language successfully? | 5 |
| **Layer 3** | Do you have a vector database for semantic search over unstructured content? | 5 |
| **Layer 3** | Do you maintain a model registry for ML artifacts with versioning? | 5 |
| **Layer 4** | Do you have production RAG infrastructure with embedding models? | 5 |
| **Layer 4** | Is your typical retrieval latency <200ms for agent queries? | 5 |
| **Layer 5** | Do you have ABAC (not just RBAC) for dynamic, query-time authorization? | 5 |
| **Layer 5** | Are all data access queries logged with user identity and purpose-of-use? | 5 |
| **Layer 6** | Do you monitor embedding model drift and retrieval quality (NDCG)? | 5 |
| **Layer 6** | Do you have feedback loops from agent failures to data quality improvements? | 5 |
| **Layer 7** | Do you have a searchable data catalog with self-service API provisioning? | 5 |
| **Layer 7** | Do you have multi-agent orchestration frameworks (LangGraph, CrewAI, etc.)? | 5 |
| **Cross-layer** | Can you trace agent decisions end-to-end with trace IDs? | 5 |
| **Cross-layer** | Do you have automated fallback strategies when agents encounter errors? | 5 |
| **Cross-layer** | Is your agent response time <2 seconds for 95% of queries? | 5 |
| **Cross-layer** | Do you have cost guardrails preventing runaway LLM API spending? | 5 |
| **Cross-layer** | Can you deploy a new agent in <2 weeks reusing infrastructure? | 5 |
| **Cross-layer** | Do you have runbooks for common agent failure scenarios? | 5 |

**Total Score Interpretation:**
- **0-20:** Not ready (archetype probably BI-First or Data Lake)
- **21-40:** Basic readiness (archetype probably BI-First or Greenfield)
- **41-60:** Partial readiness (archetype probably ML-First)
- **61-80:** Strong readiness (archetype probably Data Mesh)
- **81-100:** Agent-ready (ready for production deployment)

---

## Table 7: Multi-Agent Orchestration Framework Comparison

**Purpose:** Evaluation matrix for selecting orchestration technology

| Framework | Provider | Primary Use Case | Maturity | Production Readiness | Complexity | Community | License | Best For |
|-----------|----------|------------------|----------|---------------------|------------|-----------|---------|----------|
| **LangGraph** | LangChain | State-based workflows with cyclic graphs | Stable | ✅ Production-ready | Medium | Very Active | Open source | Complex multi-step workflows, checkpointing |
| **CrewAI** | CrewAI Inc | Role-based teams with hierarchical coordination | Stable | ✅ Production-ready | Low-Medium | Active | Open source | Team-based delegation, role specialization |
| **AutoGen** | Microsoft | Conversational agents with code execution | Stable | ✅ Production-ready | Medium-High | Very Active | Open source | Code generation, research tasks, conversation |
| **Model Context Protocol (MCP)** | Anthropic | Context standardization | Rapidly Maturing (Oct 2025) | ⚠️ Conditional (requires security expertise) | Medium-High | Growing | Open source | Standardized context access; evaluate carefully for production |

**Detailed Framework Analysis:**

### LangGraph (LangChain)
- **Strengths:** Powerful state management, cyclic graphs enable complex workflows, built-in checkpointing for failure recovery
- **Weaknesses:** Steeper learning curve, requires understanding of state machines
- **Best Use Cases:** Multi-step approval workflows, agents with memory, scenarios requiring rollback
- **Production Considerations:** Well-documented, battle-tested, active maintenance

### CrewAI
- **Strengths:** Intuitive role-based design, easy to get started, hierarchical teams natural to understand
- **Weaknesses:** Less flexible for non-hierarchical patterns, newer than LangGraph
- **Best Use Cases:** Content creation teams, research coordination, scenarios with clear manager/worker roles
- **Production Considerations:** Growing adoption, good documentation, responsive maintainers

### AutoGen (Microsoft)
- **Strengths:** Powerful code execution, conversation-based approach, strong Microsoft backing
- **Weaknesses:** Can be overkill for simple workflows, code execution requires sandboxing
- **Best Use Cases:** Research tasks, code generation, data analysis, scenarios requiring computation
- **Production Considerations:** Enterprise support available, well-maintained, used at Microsoft scale

### Model Context Protocol (MCP) - Status Update (October 2025)

**Maturity Progress:**
MCP has evolved significantly since its November 2024 announcement:
- ✅ **Major Vendor Adoption:** OpenAI (March 2025), Google DeepMind (April 2025), Microsoft Azure & Dynamics 365 (May-Oct 2025)
- ✅ **Stable Releases:** v1.0 SDKs in Go, Python, TypeScript, C#, Java
- ✅ **Production Ecosystem:** Official MCP Registry (Sept 2025), thousands of deployed servers
- ✅ **Specification Maturity:** Three major versions released in 2025 (March, June, November planned)

**Production Readiness Assessment (October 2025):**
- ✅ **For Development/Non-Critical:** MCP is suitable for development environments and exploratory applications
- ⚠️ **For Production Systems:** Requires careful evaluation:
  - **Security Concerns:** Research in mid-2025 identified authentication vulnerabilities in many deployments; OAuth 2.1 implementation is critical
  - **Protocol Evolution:** Three spec versions in 2025 indicate active refinement; expect continued changes
  - **Implementation Variance:** Security posture depends heavily on deployment configuration

**Recommendation:**
- **Production-Critical Systems:** Use established frameworks (LangGraph, CrewAI, AutoGen) with proven security models
- **Greenfield Projects:** Evaluate MCP alongside alternatives; implement robust authentication (OAuth 2.1) if adopting
- **Security-First:** If deploying MCP, mandatory security hardening beyond defaults
- **Timeline:** Monitor MCP maturation through 2026 for broader production readiness

**Bottom Line:** MCP is no longer "experimental" but remains "rapidly evolving with security considerations." Suitable for adoption with appropriate security expertise and risk tolerance.

---

## Table 8: Embedding Model Selection Matrix

**Purpose:** Choose the right embedding model for your use case

| Model | Provider | Dimensions | Cost per 1M tokens | Latency | Accuracy (BEIR) | Best For | Deployment |
|-------|----------|------------|-------------------|---------|-----------------|----------|------------|
| **text-embedding-3-large** | OpenAI | 3072 | $0.13 | Fast (50-100ms) | 54.9 | General-purpose, high accuracy | API |
| **text-embedding-3-small** | OpenAI | 1536 | $0.02 | Very fast (30-60ms) | 62.3 | Cost-sensitive, speed priority | API |
| **embed-v3** | Cohere | 1024 | $0.10 | Fast (50-100ms) | 55.0 | RAG, semantic search | API |
| **e5-large-v2** | Microsoft | 1024 | Free (self-host) | Medium (100-200ms) | 50.6 | Privacy, cost control | Self-hosted |
| **all-MiniLM-L6-v2** | Sentence-Transformers | 384 | Free (self-host) | Very fast (20-50ms) | 42.0 | Speed, low resource | Self-hosted |
| **bge-large-en-v1.5** | BAAI | 1024 | Free (self-host) | Medium (80-150ms) | 54.3 | Balanced accuracy/cost | Self-hosted |

**Selection Decision Tree:**

1. **Is privacy/data residency a requirement?**
   - YES → Self-hosted models (e5-large-v2, bge-large-en-v1.5)
   - NO → Continue to #2

2. **What's your query volume?**
   - High (>10M queries/month) → Cost matters → text-embedding-3-small or self-hosted
   - Low (<1M queries/month) → Cost less critical → Continue to #3

3. **What's your latency requirement?**
   - <50ms → text-embedding-3-small or all-MiniLM-L6-v2
   - <100ms → text-embedding-3-large, embed-v3
   - <200ms → Any model works

4. **What's your accuracy requirement?**
   - Maximum accuracy → text-embedding-3-small (surprisingly, it scores highest on BEIR)
   - High accuracy → text-embedding-3-large, embed-v3, bge-large-en-v1.5
   - Acceptable accuracy → e5-large-v2, all-MiniLM-L6-v2

**Domain-Specific Considerations:**
- **Healthcare:** Consider fine-tuning e5-large-v2 on clinical notes for HIPAA compliance
- **Legal:** Large context window important → text-embedding-3-large (3072 dims)
- **Multilingual:** embed-v3 or text-embedding-3-* (support 100+ languages)
- **Real-time:** all-MiniLM-L6-v2 for sub-50ms latency requirements

---

## Table 9: Data Quality Metrics & SLAs

**Purpose:** Target SLAs for agent-ready data infrastructure

| Metric | Layer | Target (Production) | Warning Threshold | Critical Threshold | Monitoring Frequency |
|--------|-------|---------------------|-------------------|-------------------|---------------------|
| **Data Freshness** | L1 | <30 seconds | >1 minute | >5 minutes | Real-time |
| **Pipeline Uptime** | L1 | 99.9% | <99.5% | <99.0% | Real-time |
| **CDC Latency (p95)** | L1 | <500ms | >1 second | >5 seconds | Real-time |
| **Throughput** | L1 | >10K events/sec | <5K events/sec | <1K events/sec | Real-time |
| **Semantic Resolution Accuracy** | L2 | >95% | <90% | <85% | Daily |
| **Entity Resolution Confidence** | L2 | >0.90 | <0.85 | <0.80 | Hourly |
| **Vector Search Latency (p95)** | L3 | <50ms | >100ms | >200ms | Real-time |
| **Graph Query Latency (p95)** | L3 | <200ms | >500ms | >1 second | Real-time |
| **Retrieval Quality (NDCG@5)** | L4 | >0.85 | <0.80 | <0.75 | Hourly |
| **RAG Latency (p95)** | L4 | <200ms | >500ms | >1 second | Real-time |
| **Embedding Drift (KL divergence)** | L4 | <0.10 | >0.15 | >0.25 | Daily |
| **ABAC Policy Eval Latency (p95)** | L5 | <10ms | >50ms | >100ms | Real-time |
| **Audit Log Completeness** | L5 | 100% | <99.9% | <99.5% | Hourly |
| **Agent Response Latency (p95)** | L6 | <2 seconds | >3 seconds | >5 seconds | Real-time |
| **Hallucination Rate** | L6 | <3% | >5% | >10% | Hourly |
| **User Satisfaction (Thumbs Up)** | L6 | >85% | <80% | <70% | Daily |
| **Cost per Query** | L6 | <$0.01 | >$0.02 | >$0.05 | Hourly |
| **Data Product Availability** | L7 | 99.9% | <99.5% | <99.0% | Real-time |
| **API Response Time (p95)** | L7 | <100ms | >200ms | >500ms | Real-time |

**SLA Breach Response Protocols:**

**Warning Threshold Breach:**
- Automated alert to on-call engineer
- Incident ticket created (P2 severity)
- Investigation required within 4 hours
- No user-visible impact expected

**Critical Threshold Breach:**
- Immediate page to on-call engineer
- Incident ticket created (P1 severity)
- Investigation required within 30 minutes
- User-visible impact likely; consider fallback strategies
- Post-mortem required within 48 hours of resolution

---

## Table 10: VERT Scoring Summary

**Purpose:** Official VERT Council certification scores for Chapter 1

| Dimension | v1.0 Score | v2.0 Score | v2.1 Score | v2.1.1 Notes |
|-----------|------------|------------|------------|--------------|
| **Truth (Technical Accuracy)** | 8.5 | 8.8 | 8.9 | Maintained; MCP status updated for temporal accuracy |
| **Trust (Ethics & Governance)** | 8.4 | 8.6 | 8.7 | Maintained; bias-aware term governance validated |
| **Traction (Operational Feasibility)** | 8.6 | 8.9 | 9.0 | Maintained; timelines and costs realistic |
| **Clarity (Pedagogical Quality)** | 8.0 | 8.3 | 8.4 | Improved; narrative consistency corrections |
| **Composite Score** | 8.4 | 8.7 | **8.9** | ✅ Production Ready (GREEN) |
| **Status** | AMBER | GREEN | **GREEN** | Codex-Validated October 2025 |

**Version Progression:**
- **v1.0 → v2.0:** +0.3 points (Priority 1 VERT feedback integration)
- **v2.0 → v2.1:** +0.2 points (Codex Article 4-7 revalidation, operational details enhanced)
- **v2.1 → v2.1.1:** No score change (post-certification editorial corrections; no recertification required)

**v2.1.1 Improvements (Editorial):**
- ✅ Narrative coherence: Healthcare context maintained throughout (no retail/banking examples)
- ✅ Temporal accuracy: MCP status updated to October 2025 reality
- ✅ Consistency: Examples align with Meridian Health case study

**VERT Council Recommendation:**
> "Chapter 1 v2.1 achieves Production Ready status with comprehensive technical accuracy, strong ethical frameworks, realistic operational guidance, and clear pedagogical structure. Version 2.1.1 applies post-certification polish without changing core content. Approved for publication."

**Certification Date:** October 2025  
**Certification Valid Through:** October 2026 (1-year validity)  
**Recertification Required:** If substantive content changes exceed 20% or new technologies fundamentally alter architecture

---

## Document Metadata

**Version:** 2.1.1  
**Type:** Supplementary Reference Tables  
**Status:** Production Ready  
**Last Updated:** October 11, 2025  
**Author:** Ram Katamaraja, CEO of Colaberry Inc.  
**Publisher:** Colaberry Press  
**Copyright:** © 2025 Colaberry Inc.

**Change Log:**
- **v2.1.1 (Oct 11, 2025):** Updated Table 7 with corrected MCP status (October 2025 perspective); version alignment with main chapter
- **v2.1 (Oct 2025):** VERT Codex validation, enhanced metrics and SLAs
- **v2.0 (Sep 2025):** VERT Priority 1 feedback integration
- **v1.0 (Aug 2025):** Initial table compilation

**Related Documents:**
- chapter1_final_v2.1.1.md (main chapter)
- VERT_Certification_Report_v2.1.md (certification details)
- diagram1-seven-layers-v2.mermaid through diagram7-evolution-timeline.mermaid (visual references)

---

**End of Tables Document**