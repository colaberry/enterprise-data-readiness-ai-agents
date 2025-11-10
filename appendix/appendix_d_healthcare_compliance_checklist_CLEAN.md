# Appendix D: Healthcare Compliance Checklist
## HIPAA Requirements for AI Agent Deployment

**Purpose:** Comprehensive HIPAA compliance checklist for healthcare AI agents  
**Use:** Ensure all regulatory requirements met before production deployment  
**Date:** November 8, 2025  
**Version:** 1.0

---

## Important Disclaimer

**This checklist is for informational purposes only and does not constitute legal advice.** 

Consult with your organization's legal counsel, compliance officer, and HIPAA privacy/security officers before deploying AI agents that access Protected Health Information (PHI).

HIPAA regulations are complex and subject to interpretation. This checklist covers common requirements but may not be exhaustive for your specific use case.

---

## HIPAA Overview

**HIPAA = Health Insurance Portability and Accountability Act (1996)**

**Three Key Rules:**
1. **Privacy Rule:** How PHI can be used and disclosed
2. **Security Rule:** Technical, physical, and administrative safeguards for ePHI (electronic PHI)
3. **Breach Notification Rule:** Requirements when PHI is compromised

**Covered Entities:**
- Healthcare providers
- Health plans
- Healthcare clearinghouses

**Business Associates:**
- Vendors who process PHI on behalf of covered entities (e.g., cloud providers, AI vendors)

**Key Requirement:** Business Associate Agreements (BAAs) required with ALL vendors handling PHI

---

## Pre-Deployment Checklist

### Section 1: Business Associate Agreements (BAAs)

**✅ Required BAAs Obtained:**

- [ ] Cloud provider (Azure, AWS, GCP)
- [ ] Vector database vendor (Azure AI Search, Pinecone, etc.)
- [ ] LLM provider (OpenAI, Anthropic, etc.)
- [ ] Data warehouse vendor (Snowflake, BigQuery, etc.)
- [ ] CDC/streaming vendor (Fivetran, Confluent, etc.)
- [ ] Monitoring vendor (Datadog, Splunk, etc.)
- [ ] Data catalog vendor (Atlan, Collibra, etc.)
- [ ] Any other vendor processing PHI

**BAA Must Include:**
- Permitted uses and disclosures of PHI
- Safeguards to prevent misuse
- Subcontractor agreements (if vendor uses subcontractors)
- Breach notification obligations
- Return or destruction of PHI at contract termination

**Action:** Obtain signed BAAs from ALL vendors before Week 1. Lead time: 1-4 weeks.

---

### Section 2: HIPAA Security Rule - Technical Safeguards (§164.312)

#### § 164.312(a) - Access Control

**✅ Access Control Implemented:**

- [ ] **Unique User IDs (§164.312(a)(2)(i) - Required):**
  - No shared accounts
  - Every user has unique identifier
  - User ID tied to individual (not role like "admin")

- [ ] **Emergency Access Procedure (§164.312(a)(2)(ii) - Required):**
  - Break-glass access for emergencies documented
  - Emergency access requires justification (purpose-of-use)
  - Emergency access automatically audited

- [ ] **Automatic Logoff (§164.312(a)(2)(iii) - Addressable):**
  - Sessions timeout after 15 minutes of inactivity (recommended)
  - Or implement alternative (e.g., screen lock after 5 minutes)

- [ ] **Encryption and Decryption (§164.312(a)(2)(iv) - Addressable):**
  - PHI encrypted at rest (database encryption, Azure Key Vault)
  - PHI encrypted in transit (TLS 1.2+ for all network traffic)
  - Encryption keys managed separately (not stored with data)

**Agent-Specific Requirements:**
- [ ] ABAC policies operational (context-aware authorization)
- [ ] MFA required for PHI access
- [ ] Agent service accounts have unique IDs (not shared)

---

#### § 164.312(b) - Audit Controls (Required)

**✅ Audit Logging Implemented:**

- [ ] **100% PHI access logged:**
  - User ID (who accessed)
  - Timestamp (when accessed)
  - Action (read/write/delete)
  - Resource (what PHI accessed - patient ID, record ID)
  - Purpose of use (treatment/payment/operations)
  - Result (access allowed/denied)
  - Trace ID (for correlation)

- [ ] **Audit logs immutable:**
  - Cannot be deleted or modified
  - Write-once, read-many storage
  - Tamper-evident (checksums, blockchain, or similar)

- [ ] **Audit logs retained 6+ years:**
  - HIPAA requires 6 years minimum
  - Some states require longer (check state laws)

- [ ] **Audit log review process:**
  - Weekly automated review (anomaly detection)
  - Monthly manual review (compliance team)
  - Escalation process for suspicious activity

**Agent-Specific Requirements:**
- [ ] All LLM calls accessing PHI logged
- [ ] All RAG retrievals accessing PHI logged
- [ ] Multi-agent orchestration logged (which agent accessed what)
- [ ] Reasoning traces logged (why agent made decision)

---

#### § 164.312(c) - Integrity (Addressable)

**✅ Data Integrity Controls:**

- [ ] **Checksums or hashes:**
  - Verify data not corrupted in transit
  - Verify data not corrupted in storage
  - Alert on integrity violations

- [ ] **Version control:**
  - Track changes to PHI
  - Audit trail of modifications
  - Ability to restore previous versions

**Agent-Specific Requirements:**
- [ ] Embedding checksums (verify vector integrity)
- [ ] Semantic layer version control (track business logic changes)
- [ ] Model version tracking (which LLM version generated response)

---

#### § 164.312(d) - Person or Entity Authentication (Required)

**✅ Authentication Implemented:**

- [ ] **Strong authentication:**
  - Password complexity requirements (12+ characters, mixed case, numbers, symbols)
  - Or certificate-based authentication
  - Or biometric authentication

- [ ] **Multi-Factor Authentication (MFA) for PHI access:**
  - SMS, authenticator app, or hardware token
  - Required for all users accessing PHI
  - Required for administrator accounts

**Agent-Specific Requirements:**
- [ ] Users authenticate before querying agents about PHI
- [ ] Agent service accounts use managed identities (Azure) or IAM roles (AWS) - no passwords
- [ ] API keys rotated every 90 days

---

#### § 164.312(e) - Transmission Security (Addressable)

**✅ Transmission Security Implemented:**

- [ ] **Encryption in transit (TLS 1.2+):**
  - All API calls encrypted
  - All database connections encrypted
  - All streaming data encrypted
  - No unencrypted PHI transmission

- [ ] **Integrity controls:**
  - Checksums verify data not modified in transit
  - Digital signatures for critical transactions

**Agent-Specific Requirements:**
- [ ] LLM API calls encrypted (OpenAI, Anthropic use HTTPS)
- [ ] Vector DB queries encrypted
- [ ] CDC/streaming encrypted (Kafka SSL, Event Hubs encryption)

---

### Section 3: HIPAA Security Rule - Physical Safeguards (§164.310)

#### § 164.310(a) - Facility Access Controls

**✅ Cloud Datacenter Security:**

- [ ] **Cloud provider is HIPAA-eligible:**
  - Azure (HIPAA regions: US Gov, US East, US West, etc.)
  - AWS (HIPAA regions: us-east-1, us-west-2, etc.)
  - GCP (HIPAA compliance available)

- [ ] **No local PHI storage:**
  - All PHI in cloud (not on laptops, workstations)
  - Developers cannot download PHI to local machines
  - Test data de-identified (no real PHI in dev/test)

**Agent-Specific Requirements:**
- [ ] No PHI in LLM prompts sent to non-BAA providers
- [ ] No PHI in logs stored locally (all logs in cloud with BAA)

---

#### § 164.310(b) - Workstation Use

**✅ Workstation Security:**

- [ ] **Screen lock after 5 minutes:**
  - Automatic timeout
  - Requires password/biometric to unlock

- [ ] **No PHI on unencrypted devices:**
  - Laptops encrypted (BitLocker, FileVault, etc.)
  - USB drives prohibited or encrypted

- [ ] **Physical security:**
  - Workstations in secure areas
  - No PHI visible to unauthorized persons

**Agent-Specific Requirements:**
- [ ] Agent UI screens lock after inactivity
- [ ] No PHI in agent response screenshots/exports without authorization

---

### Section 4: HIPAA Security Rule - Administrative Safeguards (§164.308)

#### § 164.308(a)(1) - Security Management Process (Required)

**✅ Risk Assessment:**

- [ ] **Formal risk assessment conducted:**
  - Identify threats to PHI (unauthorized access, breach, loss)
  - Assess likelihood and impact
  - Document risks and mitigations
  - Updated annually

- [ ] **Risk management plan:**
  - How to reduce risks to reasonable and appropriate level
  - Prioritize risks (high/medium/low)
  - Assign owners (who fixes what)
  - Timeline for remediation

- [ ] **Sanction policy:**
  - Consequences for HIPAA violations
  - Documented and communicated to workforce
  - Applied consistently

- [ ] **Information system activity review:**
  - Weekly automated audit log review
  - Monthly manual compliance review
  - Quarterly management review

**Agent-Specific Requirements:**
- [ ] AI-specific risks assessed (hallucinations, bias, wrong data access)
- [ ] HITL escalation for high-risk agent decisions
- [ ] Bias testing completed (no disparate impact >10% across demographics)

---

#### § 164.308(a)(3) - Workforce Security (Required)

**✅ Workforce Training:**

- [ ] **HIPAA training for all workforce:**
  - Annual training required
  - Covers Privacy Rule, Security Rule, Breach Notification
  - Documents training completion

- [ ] **Agent-specific training:**
  - How agents work (architecture, capabilities)
  - How to escalate when agent makes mistakes
  - How to interpret agent reasoning/citations
  - HITL workflows and approval processes

- [ ] **Termination procedures:**
  - Revoke access within 24 hours of termination
  - Audit terminated users' final access
  - Document access revocation

**Action:** Train ALL users (clinicians, administrators, IT staff) before Week 12 launch

---

#### § 164.308(a)(4) - Information Access Management (Required)

**✅ Access Authorization:**

- [ ] **Role-based access (RBAC) + Attribute-based access (ABAC):**
  - Principle of least privilege (users only access PHI they need)
  - ABAC policies enforce context (user.role + patient.department match)
  - Purpose-of-use required (treatment, payment, operations)

- [ ] **Access request/approval process:**
  - New users request access
  - Manager approves
  - IT provisions
  - Access logged and audited

- [ ] **Access review:**
  - Quarterly review of who has access
  - Remove access no longer needed
  - Document reviews

**Agent-Specific Requirements:**
- [ ] ABAC policies prevent agents from cross-department access (patient.department == user.department)
- [ ] HITL approval required for clinical recommendations

---

### Section 5: HIPAA Privacy Rule (§164.502-§164.528)

#### Minimum Necessary Standard (§164.502(b))

**✅ Minimum Necessary Implemented:**

- [ ] **Agents only retrieve PHI needed:**
  - RAG retrieval limited to relevant chunks (not entire patient record)
  - Vector DB filters by department/authorization (user can only search their patients)
  - No unnecessary data access (agent doesn't pull diagnosis when only name needed)

- [ ] **Role-based minimum necessary:**
  - Clinicians: Full access to their patients
  - Billing: Only billing data, not clinical notes
  - Administrators: Aggregate/de-identified data only

**Agent-Specific Requirements:**
- [ ] RAG context assembly limited to top-5 relevant chunks (not top-100)
- [ ] Agent responses don't include unnecessary PHI (e.g., don't cite SSN when only name needed)

---

#### Notice of Privacy Practices (§164.520)

**✅ Patient Notice:**

- [ ] **Notice includes AI agent use:**
  - "We use AI agents to [purpose: scheduling, care coordination, etc.]"
  - "AI agent decisions reviewed by healthcare professionals"
  - "You can request human review of AI recommendations"
  - "Your data used to improve AI (opt-out available)"

- [ ] **Notice provided to all patients:**
  - At first encounter
  - Updated when AI use changes
  - Acknowledgment of receipt documented

**Action:** Update Notice of Privacy Practices before Week 12 launch, obtain patient acknowledgments

---

#### Patient Rights (§164.524-§164.528)

**✅ Patient Rights Supported:**

- [ ] **Right of Access (§164.524):**
  - Patients can request copy of their data
  - Includes AI agent interactions about them
  - Provided within 30 days

- [ ] **Right to Accounting of Disclosures (§164.528):**
  - Patients can request list of PHI disclosures (last 6 years)
  - Includes disclosures to AI agents (if agent shared data externally)
  - Does NOT include disclosures for treatment/payment/operations

**Agent-Specific Requirements:**
- [ ] Audit logs enable accounting of disclosures (can generate report)
- [ ] Patients can request "what did AI agents say about me?"

---

### Section 6: HIPAA Breach Notification Rule (§164.400-§164.414)

#### Breach Definition

**Breach = Unauthorized acquisition, access, use, or disclosure of PHI that compromises privacy/security**

**Exceptions (not considered breaches):**
- Unintentional access by workforce within scope of authority
- Inadvertent disclosure to another person with authorization
- Disclosure where recipient couldn't reasonably retain information

**Agent-Specific Breach Scenarios:**
- ❌ Agent shows Patient A's data to Patient B → BREACH
- ❌ Agent accesses patient record without authorization → BREACH
- ❌ Agent discloses PHI to unauthorized third party → BREACH
- ❌ Data breach exposes patient embeddings with identifiable info → BREACH
- ✅ Agent error caught by HITL before disclosure → NOT a breach (if caught before patient sees it)

---

#### Breach Notification Requirements

**✅ Breach Response Plan:**

- [ ] **Immediate assessment:**
  - Detect breach within 24 hours (monitoring/alerts)
  - Assess scope (how many patients? what data?)
  - Contain breach (isolate affected systems)

- [ ] **Notification to individuals (<500 affected):**
  - Within 60 days of discovery
  - By mail or email (if authorized)
  - Includes: what happened, what data involved, what organization is doing, patient steps

- [ ] **Notification to HHS (≥500 affected):**
  - Within 60 days of discovery
  - Submit to HHS Breach Portal (public "wall of shame")

- [ ] **Notification to media (≥500 affected in same state/jurisdiction):**
  - Within 60 days
  - Prominent media outlets

- [ ] **Documentation:**
  - All breaches documented (including <500)
  - Breach log maintained for 6 years
  - Includes actions taken to mitigate

**Agent-Specific Requirements:**
- [ ] Automated breach detection (agent accessed wrong patient → alert immediately)
- [ ] Runbook for agent-caused breaches (what to do when agent shows wrong data)
- [ ] Breach notification templates ready (can notify within 60 days)

---

## Agent-Specific HIPAA Requirements

### 1. Human-in-the-Loop (HITL) for Clinical Decisions

**✅ HITL Required:**

- [ ] **All clinical recommendations reviewed by licensed clinician:**
  - Diagnoses
  - Treatment plans
  - Medication prescriptions
  - Patient discharge decisions

- [ ] **HITL workflow operational:**
  - Agent generates recommendation
  - Routes to clinician for approval
  - Clinician can approve, reject, or modify
  - Final decision documented (who approved, when, why if modified)

- [ ] **Agent CANNOT auto-approve clinical decisions**

**Rationale:** Avoids practicing medicine without a license, maintains professional liability

---

### 2. De-Identification for Non-Clinical Uses

**✅ De-Identification Used:**

- [ ] **Agent training/fine-tuning uses de-identified data:**
  - Remove 18 HIPAA identifiers (names, dates, ZIP codes, etc.)
  - Or use Expert Determination method (statistician certifies low re-identification risk)

- [ ] **Agent evaluation/testing uses de-identified data:**
  - Test datasets don't contain real PHI
  - Or use synthetic data (generated, not real patients)

**18 HIPAA Identifiers to Remove:**
1. Names
2. Geographic subdivisions smaller than state
3. Dates (except year) - birth date, admission date, discharge date, death date
4. Telephone numbers
5. Fax numbers
6. Email addresses
7. Social Security Numbers
8. Medical Record Numbers
9. Health Plan Beneficiary Numbers
10. Account numbers
11. Certificate/license numbers
12. Vehicle identifiers
13. Device identifiers/serial numbers
14. URLs
15. IP addresses
16. Biometric identifiers (fingerprints, voiceprints)
17. Full-face photos
18. Any other unique identifying number/characteristic

**Agent-Specific:**
- [ ] Embeddings de-identified (no names/dates in vector metadata)
- [ ] LLM prompts de-identified for non-clinical testing

---

### 3. Third-Party AI Model Vendors

**✅ AI Vendor Compliance:**

- [ ] **OpenAI/Anthropic/etc. BAA signed:**
  - Zero data retention (OpenAI's zero retention policy for BAA patients)
  - No training on patient data
  - Encryption at rest and in transit
  - SOC2 Type II certified

- [ ] **Data residency understood:**
  - Where is data processed? (US, EU, other?)
  - Complies with state laws? (e.g., California CMIA)

- [ ] **Model versioning:**
  - Which model version used? (GPT-4o, Claude 3.5 Sonnet, etc.)
  - Model updates controlled (not auto-upgraded without testing)

---

### 4. Bias and Fairness (Civil Rights Act, ADA)

**✅ Non-Discrimination:**

- [ ] **Bias testing completed:**
  - Across age, gender, race, ethnicity, income
  - Disparate impact <10% (no group accuracy <80% if overall 85%)

- [ ] **Mitigation strategies:**
  - Diverse training data
  - Fairness constraints in model
  - Human review of edge cases

- [ ] **Documentation:**
  - Bias testing results documented
  - Mitigation strategies documented
  - Ongoing monitoring (quarterly bias re-assessment)

**Rationale:** Avoid discrimination claims under Title VI (Civil Rights Act) and ADA

---

## Pre-Launch Final Checklist

**Before Week 12 production launch, verify ALL items:**

### Technical Safeguards
- [ ] Access control (unique IDs, emergency access, MFA)
- [ ] Audit logging (100% PHI access, immutable, 6+ year retention)
- [ ] Encryption (at rest and in transit, TLS 1.2+)
- [ ] Authentication (strong passwords, MFA for PHI)

### Physical Safeguards
- [ ] Cloud datacenters HIPAA-eligible
- [ ] No local PHI storage
- [ ] Workstations secured (screen lock, encryption)

### Administrative Safeguards
- [ ] Risk assessment completed
- [ ] Workforce trained (HIPAA + agent-specific)
- [ ] ABAC policies operational
- [ ] HITL workflows tested

### Privacy Rule
- [ ] Minimum necessary enforced
- [ ] Notice of Privacy Practices updated
- [ ] Patient rights supported (access, accounting)

### Breach Notification
- [ ] Breach response plan documented
- [ ] Breach detection automated
- [ ] Notification templates ready

### Agent-Specific
- [ ] BAAs signed with ALL vendors
- [ ] HITL operational for clinical decisions
- [ ] Bias testing passed (<10% disparate impact)
- [ ] De-identification for non-clinical uses

---

## HIPAA Penalties

**Why compliance matters: Penalties are severe**

### Civil Penalties (HHS OCR)
- **Tier 1:** $100-50,000 per violation (unknowing)
- **Tier 2:** $1,000-50,000 per violation (reasonable cause)
- **Tier 3:** $10,000-50,000 per violation (willful neglect, corrected)
- **Tier 4:** $50,000 per violation (willful neglect, not corrected)
- **Annual Maximum:** $1.5 million per violation type

### Criminal Penalties (DOJ)
- **Tier 1:** Up to $50,000 and 1 year (unknowing)
- **Tier 2:** Up to $100,000 and 5 years (false pretenses)
- **Tier 3:** Up to $250,000 and 10 years (intent to sell/transfer/misuse)

### Additional Consequences
- Loss of patient trust
- Reputation damage
- State attorney general lawsuits
- Class action lawsuits
- Exclusion from federal health programs

---

## Resources

**HIPAA Regulations:**
- HHS OCR: https://www.hhs.gov/hipaa/index.html
- HIPAA Privacy Rule: https://www.hhs.gov/hipaa/for-professionals/privacy/index.html
- HIPAA Security Rule: https://www.hhs.gov/hipaa/for-professionals/security/index.html

**Cloud Provider HIPAA Resources:**
- Azure HIPAA: https://learn.microsoft.com/en-us/azure/compliance/offerings/offering-hipaa-us
- AWS HIPAA: https://aws.amazon.com/compliance/hipaa-compliance/
- GCP HIPAA: https://cloud.google.com/security/compliance/hipaa

**AI Vendor HIPAA Resources:**
- OpenAI BAA: https://openai.com/enterprise-privacy
- Anthropic BAA: https://www.anthropic.com/legal/privacy

---

**© 2025 Colaberry Inc. All rights reserved.**

**DISCLAIMER:** This checklist is for informational purposes only and does not constitute legal advice. Consult with qualified legal counsel and HIPAA compliance experts before deploying healthcare AI agents.

---

**END OF APPENDIX D**
