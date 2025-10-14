# Chapter 2: Reader Exercises Using Diagrams

**Purpose:** These exercises help readers apply the Five Pillars framework to their own organizations using the diagrams as tools. Each exercise is hands-on, produces a concrete deliverable, and takes 30-90 minutes.

---

## Exercise 1: Create Your Pillar Health Dashboard
**Difficulty:** ⭐⭐ Moderate  
**Time:** 45-60 minutes  
**Uses:** Diagram 10 (Pillar Health Dashboard)  
**Deliverable:** Your organization's current-state dashboard

### Objective
Assess your organization's current pillar health and visualize it using the same format as Meridian Health's dashboard.

### Instructions

**Step 1: Complete Self-Assessments (30 minutes)**

For each of the five pillars, answer the 6 assessment questions from the chapter:

**Pillar 1: Accessibility**
1. Can agents retrieve data in <200ms? (0-10 points)
2. Is data fresh enough (<60s)? (0-10 points)
3. Do you have multi-modal storage? (0-10 points)
4. Can agents discover data self-service? (0-10 points)
5. Do you have caching & parallelization? (0-10 points)
6. Do you monitor latency real-time? (0-10 points)
**Your Accessibility Score:** ___/60

**Pillar 2: Semantic Richness**
1. Do you have a business glossary (>85% coverage)? (0-10)
2. Are entities unified across systems? (0-10)
3. Do metrics have single source of truth? (0-10)
4. Can NL phrases map to queries automatically? (0-10)
5. Do you have formal ontologies? (0-10)
6. Do you detect semantic drift? (0-10)
**Your Semantic Score:** ___/60

**Pillar 3: Quality & Trust**
1. Do you monitor data freshness with SLAs? (0-10)
2. Are required fields validated (>98%)? (0-10)
3. Do you have accuracy validation (>95%)? (0-10)
4. Is data reconciled across systems? (0-10)
5. Do you detect issues proactively? (0-10)
6. Is all sensitive data access audited? (0-10)
**Your Quality Score:** ___/60

**Pillar 4: Governance & Security**
1. Can you enforce different permissions per user dynamically? (0-10)
2. Is data classified by sensitivity? (0-10)
3. Can you trace every access to specific user? (0-10)
4. Can you mask data by user role? (0-10)
5. Are compliance requirements (HIPAA/GDPR) automated? (0-10)
6. Is policy evaluation fast (<10ms)? (0-10)
**Your Governance Score:** ___/60

**Pillar 5: Observability**
1. Do you detect issues before users complain? (0-10)
2. Do you monitor data health real-time? (0-10)
3. Do you track model quality (embeddings, LLMs)? (0-10)
4. Can you correlate issues across layers? (0-10)
5. Do you track per-query costs? (0-10)
6. Do monitoring insights drive rapid improvements? (0-10)
**Your Observability Score:** ___/60

**Step 2: Calculate Percentages (5 minutes)**

For each pillar:
- Percentage = (Score / 60) × 100%
- Status = Use Table 7 scoring rubric:
  - 0-20% = 🔴 CRITICAL
  - 21-40% = 🟠 POOR
  - 41-60% = 🟡 FAIR
  - 61-80% = 🟢 GOOD
  - 81-100% = ✅ EXCELLENT

**Step 3: Draw Your Dashboard (10 minutes)**

Using Diagram 10 as a template, create your current-state dashboard:

```
MY ORGANIZATION: CURRENT STATE

Pillar 1: Accessibility
Score: ___/60 | Percentage: ___% | Status: [COLOR EMOJI]

Pillar 2: Semantic Richness
Score: ___/60 | Percentage: ___% | Status: [COLOR EMOJI]

Pillar 3: Quality & Trust
Score: ___/60 | Percentage: ___% | Status: [COLOR EMOJI]

Pillar 4: Governance & Security
Score: ___/60 | Percentage: ___% | Status: [COLOR EMOJI]

Pillar 5: Observability
Score: ___/60 | Percentage: ___% | Status: [COLOR EMOJI]

OVERALL HEALTH
Total: ___/300 | Average: ___% | Status: [READINESS LEVEL]
```

**Readiness Levels:**
- 0-20%: Not Ready - Delay agent projects
- 21-40%: High Risk - Proceed cautiously
- 41-60%: Moderate Risk - Pilot only
- 61-80%: Agent-Ready - Production feasible
- 81-100%: Highly Optimized - Deploy confidently

**Step 4: Identify Your Weakest Pillar (5 minutes)**

- Which pillar has the lowest score? ____________
- What specific gaps cause this low score? (List 2-3)
  1. ___________________________________
  2. ___________________________________
  3. ___________________________________

### Reflection Questions

1. **Surprise:** Which pillar score surprised you most (higher or lower than expected)? Why?

2. **Balance:** What's the gap between your highest and lowest pillar? 
   - Gap = ___% (difference between max and min)
   - Is your pentagon balanced (<20% gap) or lopsided (>40% gap)?

3. **Priority:** Based on your scores, which pillar needs immediate attention?

4. **Archetype:** Which archetype (Chapter 1, Table 5) best matches your organization?
   - BI-First (60%)
   - Data Lake (20%)
   - ML-First (15%)
   - Data Mesh (3%)
   - Greenfield (2%)

### Deliverable

**Save your completed dashboard as:** `[YourCompany]_Pillar_Dashboard_[Date].pdf`

**Share with:**
- Your data leadership team
- Executives (use this in next strategy review)
- Peer organizations (benchmark with others)

**Update frequency:** Monthly during transformation, quarterly after reaching >60%

---

## Exercise 2: Navigate Your Priority with the Decision Tree
**Difficulty:** ⭐ Easy  
**Time:** 30 minutes  
**Uses:** Diagram 15 (Decision Tree)  
**Deliverable:** Your personalized 90-day action plan

### Objective
Use the decision tree to determine YOUR organization's specific priority order and create a customized action plan.

### Instructions

**Step 1: Prepare Your Scores (5 minutes)**

From Exercise 1, write your five pillar scores here:

| Pillar | Score (0-60) | Percentage | Status |
|--------|--------------|------------|--------|
| Accessibility | ___ | ___% | ___ |
| Semantic | ___ | ___% | ___ |
| Quality | ___ | ___% | ___ |
| Governance | ___ | ___% | ___ |
| Observability | ___ | ___% | ___ |

**Step 2: Walk the Decision Tree (10 minutes)**

Open Diagram 15 (Decision Tree). Start at the top "START" node and answer each question:

**Question 1: Critical Check**
"Any pillar score <20% (CRITICAL)?"

Your answer: [ ] YES [ ] NO

- If YES: Which pillar(s)? ____________
- Action: 🔴 IMMEDIATE - Fix critical pillar first (1-2 weeks)

**Question 2: Foundation Check** (if Q1 = NO)
"Is Observability <60% (FAIR)?"

Your answer: [ ] YES [ ] NO
Your Observability: ___% 

- If YES: Action: 🔵 HIGH PRIORITY - Start with Observability (3-4 weeks)

**Question 3: Compliance Check** (if Q2 = NO)
"Is Governance <60% (FAIR)?"

Your answer: [ ] YES [ ] NO
Your Governance: ___%

- If YES: Action: 🟣 HIGH PRIORITY - Fix Governance next (4-6 weeks)

**Question 4: Reliability Check** (if Q3 = NO)
"Is Quality & Trust <60% (FAIR)?"

Your answer: [ ] YES [ ] NO
Your Quality: ___%

- If YES: Action: 🟢 MEDIUM PRIORITY - Improve Quality (3-4 weeks)

**Question 5: Performance Check** (if Q4 = NO)
"Is Accessibility OR Semantic Richness <60% (FAIR)?"

Your answer: [ ] YES [ ] NO
Your Accessibility: ___% | Your Semantic: ___%

- If YES: Action: 🟡 MEDIUM PRIORITY - Optimize Performance (4-6 weeks)

**If ALL questions = NO:**
✅ EXCELLENT! All pillars >60%. Action: Maintain & optimize.

**Step 3: Create Your Action Plan (15 minutes)**

Based on where you landed in the decision tree, fill out this action plan:

```
MY 90-DAY ACTION PLAN

PRIORITY 1: [Pillar Name]
- Current Score: ___/60 (___%)
- Target Score: ___/60 (___%)
- Timeline: ___ weeks
- Owner: [Name/Role]

Top 3 Actions to Improve This Pillar:
1. ___________________________________
   Estimated effort: ___ days
   Assigned to: ___________
   
2. ___________________________________
   Estimated effort: ___ days
   Assigned to: ___________
   
3. ___________________________________
   Estimated effort: ___ days
   Assigned to: ___________

PRIORITY 2: [Pillar Name]
- Current Score: ___/60 (___%)
- Target Score: ___/60 (___%)
- Timeline: ___ weeks
- Owner: [Name/Role]

Top 3 Actions:
1. ___________________________________
2. ___________________________________
3. ___________________________________

PRIORITY 3: [Pillar Name]
- Current Score: ___/60 (___%)
- Target Score: ___/60 (___%)
- Timeline: ___ weeks
- Owner: [Name/Role]

Top 3 Actions:
1. ___________________________________
2. ___________________________________
3. ___________________________________

RE-ASSESSMENT SCHEDULE:
- Week 4: Re-assess Priority 1 pillar
- Week 8: Re-assess Priority 2 pillar
- Week 12: Re-assess all pillars
- Monthly: Dashboard review (Exercise 1)
```

### Reflection Questions

1. **Alignment:** Does the decision tree's recommendation match your intuition? If not, why might they differ?

2. **Deviation:** Are there any reasons you might deviate from the tree's recommendation? (e.g., imminent compliance audit, active production failures)

3. **Resources:** Do you have the team/budget to execute this plan in the recommended timeline?

4. **Risks:** What happens if you DON'T address your Priority 1 pillar in the next 30 days?

### Deliverable

**Save your action plan as:** `[YourCompany]_90Day_Action_Plan_[Date].pdf`

**Review with:**
- Data architecture team (Week 1)
- Executive sponsors (Week 2)
- Finance/HR (for budget/hiring approval)

**Track progress:** Weekly standup against this plan

---

## Exercise 3: Map Your Failure Cascade Risks
**Difficulty:** ⭐⭐⭐ Challenging  
**Time:** 60-90 minutes  
**Uses:** Diagram 11 (Failure Cascade)  
**Deliverable:** Your organization's specific failure cascade scenarios

### Objective
Identify how YOUR organization's weak pillars could compound into catastrophic failures—and create mitigation plans.

### Instructions

**Step 1: Identify Your Weakest Pillars (10 minutes)**

From Exercise 1, list pillars scoring <60%:

1. Pillar: ____________ | Score: ___% | Status: ___
2. Pillar: ____________ | Score: ___% | Status: ___
3. Pillar: ____________ | Score: ___% | Status: ___

**Step 2: Map Cascade Scenario 1 (25 minutes)**

Using Diagram 11 as a template, map a specific failure cascade for YOUR organization:

**Starting Condition:**
- Weak Pillar(s): [List 2-3 weak pillars]
- Planned Agent Use Case: [Describe your first planned agent]
  - Example: "Customer service agent to answer product questions"

**Cascade Step 1:**
- **Trigger:** [What initial failure could occur?]
  - Example: "No observability monitoring"
- **Impact:** [What goes undetected?]
  - Example: "Data from product catalog becomes stale (updated in vendor system but not in our warehouse)"

**Cascade Step 2:**
- **Compounding Failure:** [How does Step 1 enable Step 2?]
  - Example: "Stale product data (prices, availability) goes undetected for 8 hours"
- **Impact:** [What breaks next?]
  - Example: "Agent gives customers wrong prices and says products are in stock when they're not"

**Cascade Step 3:**
- **Compounding Failure:** [How do Steps 1-2 enable Step 3?]
  - Example: "No semantic validation (Pillar 2 weak) means agent doesn't catch nonsensical inventory levels"
- **Impact:** [What fails next?]
  - Example: "Agent tells customer 'Yes, we have 10,000 units' when product is discontinued"

**Cascade Step 4:**
- **Compounding Failure:** [How do Steps 1-3 enable Step 4?]
  - Example: "No governance controls (Pillar 4 weak) means agent accesses pricing data it shouldn't"
- **Impact:** [What privacy/security breach occurs?]
  - Example: "Agent shows wholesale pricing to retail customers, violating vendor agreements"

**Final Outcome:**
- **User Impact:** [What do customers/users experience?]
  - Example: "Customers place orders for wrong prices, orders fail, trust lost"
- **Business Impact:** [What's the cost?]
  - Example: "$200K in pricing errors, vendor contract breach ($50K penalty), 1,000 customer complaints, agent taken offline"
- **Total Estimated Impact:** $______

**Step 3: Map Prevention Strategy (15 minutes)**

For the same scenario, identify which strong pillars would prevent the cascade:

**Prevention Point 1:**
- **Strong Pillar:** [Which pillar, if strong, would catch this?]
  - Example: "Observability (Pillar 5) at >80%"
- **How it prevents:** [Specific mechanism]
  - Example: "Real-time data freshness monitoring detects stale catalog in 10 minutes, alerts team before agent uses bad data"

**Prevention Point 2:**
- **Strong Pillar:** [Which pillar provides safety net?]
  - Example: "Quality & Trust (Pillar 3) at >80%"
- **How it prevents:** [Specific mechanism]
  - Example: "Automated validation rules reject inventory values >1000 units without manual approval"

**Prevention Point 3:**
- **Strong Pillar:** [Which pillar provides final backstop?]
  - Example: "Governance (Pillar 4) at >80%"
- **How it prevents:** [Specific mechanism]
  - Example: "ABAC policies prevent agent from accessing wholesale pricing table, only allows retail pricing"

**Step 4: Map Cascade Scenario 2 (Optional, 25 minutes)**

If you have multiple weak pillars, repeat Steps 2-3 for a different agent use case.

**Step 5: Create Risk Mitigation Plan (15 minutes)**

Based on your cascade scenarios, create a risk mitigation plan:

```
RISK MITIGATION PLAN

HIGHEST RISK SCENARIO: [Brief description]
Estimated Impact: $______
Probability: [ ] High [ ] Medium [ ] Low

MITIGATION ACTIONS (In Priority Order):

1. Strengthen [Pillar Name] to >60%
   - Key action: ___________________________________
   - Timeline: ___ weeks
   - Cost: $______
   - Risk reduction: [High/Medium/Low]

2. Strengthen [Pillar Name] to >60%
   - Key action: ___________________________________
   - Timeline: ___ weeks
   - Cost: $______
   - Risk reduction: [High/Medium/Low]

3. Add Safety Net: [Specific control]
   - Description: ___________________________________
   - Timeline: ___ weeks
   - Cost: $______
   - Risk reduction: [High/Medium/Low]

TOTAL MITIGATION COST: $______
TOTAL RISK AVOIDED: $______
ROI: ___% (Risk Avoided / Mitigation Cost)

DEPLOYMENT DECISION:
[ ] Proceed with agent deployment now (risk acceptable)
[ ] Delay deployment until Priority 1-2 mitigations complete
[ ] Delay deployment until all mitigations complete
```

### Reflection Questions

1. **Surprise:** Were you surprised by how quickly weak pillars could cascade into major failures?

2. **Hidden Costs:** What's the ratio of "prevention cost" to "failure cost"?
   - Prevention: $______ (mitigation actions)
   - Failure: $______ (total cascade impact)
   - Ratio: ____:1 (e.g., "1:10 = $1 prevention saves $10 in failures")

3. **Executive Communication:** If you had to explain ONE cascade scenario to your CEO in 60 seconds, which would you choose and why?

4. **Quick Wins:** Are there any "low-cost, high-impact" mitigations that could break multiple cascades?

### Deliverable

**Save your cascade maps as:** `[YourCompany]_Risk_Cascade_Analysis_[Date].pdf`

**Use for:**
- Budget justification (show ROI of prevention)
- Executive risk communication
- Team alignment (make risks concrete)
- Agent deployment go/no-go decisions

---

## Exercise 4: Plot Your Radar Chart for Balance
**Difficulty:** ⭐ Easy  
**Time:** 30 minutes  
**Uses:** Diagram 13 (Radar Chart)  
**Deliverable:** Your pillar balance visualization

### Objective
Visualize whether your pillar health is balanced (circular) or lopsided (spiky)—and identify which gaps to close for stability.

### Instructions

**Step 1: Prepare Data (5 minutes)**

From Exercise 1, write your five pillar percentages:

| Pillar | Percentage |
|--------|------------|
| Accessibility | ___% |
| Semantic Richness | ___% |
| Quality & Trust | ___% |
| Governance | ___% |
| Observability | ___% |

**Step 2: Draw Your Radar Chart (15 minutes)**

**Option A: By Hand**
1. Draw a pentagon with five axes (one per pillar)
2. Mark each axis from 0% (center) to 100% (outer edge)
3. Plot each pillar's percentage as a point on its axis
4. Connect the five points with lines to form a shape

**Option B: Using Tools**
1. Use a spreadsheet (Excel, Google Sheets) with radar chart template
2. Or use online tools: ChartGo.com, Visme.co (free radar chart makers)

**Step 3: Analyze Your Shape (10 minutes)**

**Shape Assessment:**

My radar chart shape is:
[ ] Circular/Near-circular (balanced)
[ ] Moderately irregular (some gaps)
[ ] Highly irregular/spiky (large gaps)

**Gap Analysis:**

- Highest pillar: ____________ at ___%
- Lowest pillar: ____________ at ___%
- Gap: ___% (difference between highest and lowest)

**Balance Status:**
- Gap <20%: 🟢 Balanced - sustainable, production-ready
- Gap 20-40%: 🟡 Moderate - uneven foundation, strengthen weak pillars
- Gap >40%: 🔴 Unbalanced - unstable, weak pillars will cause failures

**My Status:** [ ] Balanced [ ] Moderate [ ] Unbalanced

**Step 4: Create Balance Improvement Plan (10 minutes)**

**If your gap is >20%, answer these:**

**Which pillars are dragging down balance?**
1. [Pillar Name] at ___% (vs. highest at ___%)
2. [Pillar Name] at ___% (vs. highest at ___%)

**What's the minimum score needed to balance?**
- Target: Bring all pillars within 20% of each other
- Lowest pillar must reach: ___% (highest - 20%)
- Example: If highest = 80%, lowest must reach 60%

**Balance Improvement Actions:**

For each low pillar, pick ONE quick win action:

**Pillar 1: [Name]**
- Current: ___%
- Target: ___%
- Quick win action: ___________________________________
- Timeline: ___ weeks

**Pillar 2: [Name]**
- Current: ___%
- Target: ___%
- Quick win action: ___________________________________
- Timeline: ___ weeks

### Reflection Questions

1. **Visual Impact:** Does the radar chart shape (visual) make the imbalance more obvious than just numbers?

2. **Strategic Choice:** If you could only fix ONE pillar to improve balance, which would it be and why?

3. **Balance vs. Average:** Compare two scenarios:
   - Scenario A: Pillars at 90%, 85%, 80%, 75%, 20% (Avg: 70%)
   - Scenario B: Pillars at 65%, 65%, 65%, 65%, 65% (Avg: 65%)
   - Which is MORE production-ready? Why?

4. **Monthly Tracking:** How will you track balance over time? (Hint: Monthly radar chart snapshots)

### Deliverable

**Save your radar chart as:** `[YourCompany]_Pillar_Balance_Radar_[Date].png`

**Update monthly and compare:**
- Month 0 (baseline): ___% gap
- Month 1: ___% gap (trend: improving/stable/degrading)
- Month 2: ___% gap (trend: improving/stable/degrading)
- Month 3: ___% gap (target: <20%)

---

## Exercise 5: Design Your Observability Architecture
**Difficulty:** ⭐⭐⭐ Challenging  
**Time:** 90 minutes  
**Uses:** Diagram 14 (Metric Collection Architecture)  
**Deliverable:** Your observability implementation plan

### Objective
Map your current telemetry gaps and design a complete observability architecture to calculate pillar health scores.

### Instructions

**Step 1: Audit Current Telemetry (30 minutes)**

For each layer, list what metrics you currently collect:

**Layer 1: Real-Time Data Fabric**
Current metrics:
- [ ] Data freshness timestamps
- [ ] Pipeline latency (p50, p95, p99)
- [ ] CDC lag time
- [ ] Throughput (events/sec)
- [ ] Other: ___________________

**Layer 2: Semantic Layer**
Current metrics:
- [ ] Concept coverage %
- [ ] Query understanding accuracy
- [ ] Entity resolution success rate
- [ ] Semantic drift alerts
- [ ] Other: ___________________

**Layer 3: Multi-Modal Storage**
Current metrics:
- [ ] Query latency per store type
- [ ] Storage uptime %
- [ ] Index performance
- [ ] Disk I/O metrics
- [ ] Other: ___________________

**Layer 4: RAG Infrastructure**
Current metrics:
- [ ] Retrieval quality (NDCG)
- [ ] Cache hit rate %
- [ ] Embedding generation time
- [ ] Context assembly latency
- [ ] Other: ___________________

**Layer 5: Governance**
Current metrics:
- [ ] Policy evaluation latency
- [ ] ABAC permit/deny decisions
- [ ] Audit log completeness
- [ ] Permission violation attempts
- [ ] Other: ___________________

**Layer 7: Data Products**
Current metrics:
- [ ] API usage counts
- [ ] Cost per query
- [ ] Product-level SLA compliance
- [ ] Self-service success rate
- [ ] Other: ___________________

**Gap Summary:**
- Total possible metrics: 24 (4 per layer × 6 layers)
- Current metrics collected: ___
- Coverage: ___% 
- Gap: ___ metrics missing

**Step 2: Choose Observability Platform (15 minutes)**

Based on your organization size (from Chapter 1), choose a platform:

| Size | Employees | Recommended Platform | Cost/Month | Setup Effort |
|------|-----------|---------------------|------------|--------------|
| Small | 1,000 | Cloud-native (AWS CloudWatch, Azure Monitor) | $500-$2K | 1 eng, 2-3 weeks |
| Mid | 10,000 | Unified (Datadog, New Relic, Grafana) | $3K-$10K | 2 eng, 3-4 weeks |
| Large | 50,000+ | Enterprise (Splunk, Datadog Enterprise) | $15K-$50K | 3-4 eng, 4-6 weeks |

**My Choice:**
- Platform: ___________________
- Rationale: ___________________
- Estimated Cost: $______/month
- Setup Timeline: ___ weeks

**Step 3: Design Metric Flow (20 minutes)**

Using Diagram 14 as a template, map your metric flow:

**Emission → Collection → Processing → Outputs**

```
TELEMETRY EMISSION (Layers 1-5, 7)

Layer 1: Emit to → [Tool Name] → Send to Layer 6
Layer 2: Emit to → [Tool Name] → Send to Layer 6
Layer 3: Emit to → [Tool Name] → Send to Layer 6
Layer 4: Emit to → [Tool Name] → Send to Layer 6
Layer 5: Emit to → [Tool Name] → Send to Layer 6
Layer 7: Emit to → [Tool Name] → Send to Layer 6

LAYER 6: COLLECTION HUB

Telemetry Collector: [Platform Name]
- Time-series database: [Tool]
- Retention: 7 days (high-res), 90 days (aggregated)

Metric Processing:
- Statistical analysis: [Tool]
- Anomaly detection: [Tool/Method]
- Threshold evaluation: [Tool]

OUTPUTS

Dashboard: [Tool Name]
- Pillar health scores (real-time)
- Layer performance metrics
- Trend analysis

Alerts: [Tool Names]
- Slack for P2-P3
- PagerDuty for P0-P1
- Email for daily digests

Feedback Loops: [Process]
- Automated: [Which metrics trigger what actions?]
- Manual: [Who reviews weekly?]
```

**Step 4: Map Metrics to Pillars (15 minutes)**

For each pillar, list which layer metrics contribute to its score:

**Pillar 1: Accessibility**
Contributing metrics:
- L1: Data freshness → Weight: ___% of pillar score
- L3: Query latency → Weight: ___%
- L4: Cache hit rate → Weight: ___%
- L7: API availability → Weight: ___%
- Other: _________________ → Weight: ___%

**Pillar 2: Semantic Richness**
Contributing metrics:
- L2: Concept coverage → Weight: ___%
- L4: Query understanding → Weight: ___%
- L2: Entity resolution → Weight: ___%
- Other: _________________ → Weight: ___%

**Pillar 3: Quality & Trust**
Contributing metrics:
- L1: Pipeline uptime → Weight: ___%
- L6: MTTD → Weight: ___%
- L6: MTTR → Weight: ___%
- Other: _________________ → Weight: ___%

**Pillar 4: Governance**
Contributing metrics:
- L5: Policy latency → Weight: ___%
- L5: Audit completeness → Weight: ___%
- L5: Violations → Weight: ___%
- Other: _________________ → Weight: ___%

**Pillar 5: Observability**
Contributing metrics:
- L6: Monitoring coverage → Weight: ___%
- L6: Alert accuracy → Weight: ___%
- L6: Feedback loop speed → Weight: ___%
- Other: _________________ → Weight: ___%

**Step 5: Create Implementation Roadmap (10 minutes)**

```
OBSERVABILITY IMPLEMENTATION PLAN

Phase 1: Foundation (Weeks 1-2)
- Set up observability platform: [Platform]
- Configure Layer 1 telemetry: [Metrics]
- Build basic dashboard: [Tool]
- Cost: $______

Phase 2: Instrumentation (Weeks 3-4)
- Instrument Layers 2-5, 7: [Metrics per layer]
- Configure alerts: [Threshold + channels]
- Test end-to-end metric flow
- Cost: $______

Phase 3: Pillar Scoring (Weeks 5-6)
- Build pillar calculation logic: [Formula]
- Create pillar health dashboard
- Configure automated re-assessment
- Cost: $______

Phase 4: Feedback Loops (Weeks 7-8)
- Define automated actions per metric
- Create runbooks for manual actions
- Train team on using observability
- Cost: $______

TOTAL COST: $______
TOTAL TIMELINE: 8 weeks
TEAM: ___ engineers

MONTHLY OPERATING COST: $______
```

### Reflection Questions

1. **Coverage Gap:** What % of critical metrics are you currently NOT collecting? What's the risk?

2. **Quick Wins:** Which 3 metrics could you start collecting THIS WEEK with minimal effort?

3. **ROI:** If observability prevents just ONE major incident ($100K+), what's the ROI vs. setup cost?

4. **Ownership:** Who will own observability maintenance after setup? (It's not one-time—it's continuous)

### Deliverable

**Save your plan as:** `[YourCompany]_Observability_Architecture_[Date].pdf`

**Include:**
- Current state audit (Step 1)
- Platform selection rationale (Step 2)
- Metric flow diagram (Step 3)
- Pillar scoring logic (Step 4)
- Implementation roadmap with budget (Step 5)

**Review with:** Engineering leads (Week 1), Finance (Week 2), Execute (Week 3+)

---

## Exercise 6: Build Your 90-Day Transformation Timeline
**Difficulty:** ⭐⭐ Moderate  
**Time:** 60 minutes  
**Uses:** Diagram 12 (90-Day Roadmap)  
**Deliverable:** Your customized Gantt chart

### Objective
Create a realistic 90-day roadmap customized for YOUR archetype and pillar priorities.

### Instructions

**Step 1: Determine Your Archetype (5 minutes)**

From Chapter 1 (Table 5), identify your starting archetype:

My archetype: [ ] BI-First [ ] Data Lake [ ] ML-First [ ] Data Mesh [ ] Greenfield

**Baseline timeline:**
- BI-First: 90-120 days
- Data Lake: 75-100 days
- ML-First: 60-90 days
- Data Mesh: 45-75 days
- Greenfield: 60-90 days

**My estimated timeline:** ___ days

**Step 2: Map Your Priority Order (10 minutes)**

From Exercise 2 (Decision Tree), list your pillar priorities:

1. Priority 1: ____________ (Timeline: ___ weeks)
2. Priority 2: ____________ (Timeline: ___ weeks)
3. Priority 3: ____________ (Timeline: ___ weeks)

**Step 3: Customize the Roadmap (30 minutes)**

Using Diagram 12 as a template, create your customized timeline:

```
MY 90-DAY TRANSFORMATION ROADMAP

PHASE 1: FOUNDATION (Days 1-30)
Week 1-2:
- [ ] [Priority 1 Pillar]: [Specific action]
      Owner: _______ | Budget: $_____ | Completion: __/%
- [ ] Quick wins: Caching & indexes
      Owner: _______ | Budget: $_____ | Completion: __/%

Week 3-4:
- [ ] [Priority 1 Pillar]: [Specific action]
      Owner: _______ | Budget: $_____ | Completion: __/%
- [ ] [Priority 2 Pillar]: [Foundation work]
      Owner: _______ | Budget: $_____ | Completion: __/%

Phase 1 Milestone (Day 30):
- [ ] [Priority 1 Pillar] at >40% (current: __%)
- [ ] Observability live (monitoring active)
- [ ] Quick wins deployed (visible user value)

PHASE 2: CORE INFRASTRUCTURE (Days 31-60)
Week 5-6:
- [ ] [Layer-specific work for Priority 1]
      Example: If Accessibility → CDC implementation
      Owner: _______ | Budget: $_____ | Completion: __/%
      
Week 7-8:
- [ ] [Priority 2 Pillar]: [Core buildout]
      Owner: _______ | Budget: $_____ | Completion: ___%
- [ ] [Priority 3 Pillar]: [Initial work]
      Owner: _______ | Budget: $_____ | Completion: __/%

Phase 2 Milestone (Day 60):
- [ ] [Priority 1 Pillar] at >60% (production-ready threshold)
- [ ] [Priority 2 Pillar] at >40% (foundation complete)
- [ ] Core layers operational (L1-L4)

PHASE 3: PRODUCTION READY (Days 61-90)
Week 9-10:
- [ ] [Priority 2 Pillar]: [Complete to >60%]
      Owner: _______ | Budget: $_____ | Completion: __/%
- [ ] [Priority 3 Pillar]: [Build to >60%]
      Owner: _______ | Budget: $_____ | Completion: __/%

Week 11-12:
- [ ] All pillars: Final tuning
- [ ] Agent pilot deployment
- [ ] Production readiness gate: All pillars >60%?

Phase 3 Milestone (Day 90):
- [ ] ALL pillars >60% ✅
- [ ] First agent deployed to pilot
- [ ] Observability & governance validated
- [ ] Team trained, runbooks ready

TOTAL BUDGET: $_______ (breakdown by phase in Step 4)
TOTAL FTEs: ___ engineers
```

**Step 4: Estimate Resources (15 minutes)**

**Budget by Phase:**

| Phase | Infrastructure | Labor | Vendors | Total |
|-------|----------------|-------|---------|-------|
| Phase 1 (Days 1-30) | $_____ | $_____ | $_____ | $_____ |
| Phase 2 (Days 31-60) | $_____ | $_____ | $_____ | $_____ |
| Phase 3 (Days 61-90) | $_____ | $_____ | $_____ | $_____ |
| **TOTAL** | **$_____** | **$_____** | **$_____** | **$_____** |

**Team Requirements:**

| Role | FTE | Weeks | Loaded Cost |
|------|-----|-------|-------------|
| Data Architect (Lead) | 1.0 | 12 | $_____ |
| Senior Data Engineers | ___ | 12 | $_____ |
| ML Engineers | ___ | 12 | $_____ |
| Data Governance Specialist | 0.5 | 12 | $_____ |
| Project Manager | 0.5 | 12 | $_____ |
| **TOTAL** | **___** |  | **$_____** |

**Step 5: Identify Risks & Mitigations (10 minutes)**

**Top 3 Risks:**

**Risk 1:** _______________________________________
- Probability: [ ] High [ ] Medium [ ] Low
- Impact: [ ] High [ ] Medium [ ] Low
- Mitigation: _______________________________________

**Risk 2:** _______________________________________
- Probability: [ ] High [ ] Medium [ ] Low
- Impact: [ ] High [ ] Medium [ ] Low
- Mitigation: _______________________________________

**Risk 3:** _______________________________________
- Probability: [ ] High [ ] Medium [ ] Low
- Impact: [ ] High [ ] Medium [ ] Low
- Mitigation: _______________________________________

### Reflection Questions

1. **Feasibility:** Is your timeline realistic given current team capacity and budget?

2. **Dependencies:** What external dependencies could delay your timeline? (vendor selection, budget approval, hiring)

3. **Flexibility:** If a phase takes 2 weeks longer than planned, how does that cascade through the remaining phases?

4. **Success Criteria:** How will you know if Phase 1 was successful? (Be specific with metrics)

### Deliverable

**Save your roadmap as:** `[YourCompany]_90Day_Transformation_Roadmap_[Date].pdf`

**Include:**
- Gantt chart (visual timeline)
- Budget breakdown by phase
- Team resource allocation
- Risk mitigation plan

**Review with:**
- Executive sponsors (for budget approval)
- Engineering managers (for resource commitment)
- HR (for any new hires needed)

**Track progress:** Weekly standup, update completion % for each task

---

## Bonus Exercise: Executive Presentation (30 minutes)
**Uses:** All 6 diagrams  
**Deliverable:** 10-slide presentation

Create a concise executive presentation using the diagrams:

**Slide 1:** Title + Your Overall Pillar Health (Diagram 10)
**Slide 2:** The Risk - Failure Cascade Example (Diagram 11)
**Slide 3:** Our Priority - Decision Tree Result (Diagram 15)
**Slide 4:** Balance Assessment - Radar Chart (Diagram 13)
**Slide 5:** The Plan - 90-Day Roadmap (Diagram 12)
**Slide 6:** Observability Architecture - How We'll Track Progress (Diagram 14)
**Slide 7:** Budget Request - By Phase
**Slide 8:** ROI - Risk Avoided vs. Investment
**Slide 9:** Success Metrics - Target Pillar Scores at Day 90
**Slide 10:** Decision Required - Approval to Proceed

**Time to present:** 15 minutes + 10 min Q&A

---

## Exercise Completion Checklist

Track your progress through all exercises:

- [ ] Exercise 1: Created my pillar health dashboard
- [ ] Exercise 2: Determined my priority with decision tree
- [ ] Exercise 3: Mapped my organization's failure cascade risks
- [ ] Exercise 4: Plotted my radar chart for balance assessment
- [ ] Exercise 5: Designed my observability architecture
- [ ] Exercise 6: Built my 90-day transformation timeline
- [ ] Bonus: Created executive presentation

**Estimated total time:** 6-8 hours (can be split across multiple sessions)

**Deliverables:** 6-7 documents you can use immediately for planning, communication, and execution

---

**End of Reader Exercises**

These exercises transform Chapter 2 from passive reading to active application—readers now have concrete tools to assess their organization and build their transformation plan.