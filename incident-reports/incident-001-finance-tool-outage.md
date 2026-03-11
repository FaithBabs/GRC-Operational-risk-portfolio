# Operational Risk Incident Report #001
## Finance Platform Outage – Post Invoice Adjustment Tool

---

#### EXECUTIVE SUMMARY

Critical finance platform outage prevented processing of customer refunds and credits across US and Canada markets for 4 days, impacting 20+ customer accounts and creating customer escalations. Issue resolved through cross-functional incident management and emergency code deployment.

**Severity:** SEV 3 – High Impact  
**Duration:** 4 days (96 hours)  
**Geographic Scope:** US and Canada markets  
**Status:** Closed

---

#### 1. INCIDENT DETAILS

| Field | Details |
|-------|---------|
| **Incident ID** | INC-2024-001 |
| **Severity Level** | SEV 3 - High Impact |
| **Date Detected** | [Date] |
| **Date Resolved** | [Date + 4 days] |
| **Duration** | 4 days (96 hours) |
| **Geographic Scope** | US and Canada markets |

---

#### 2. RISK EVENT DESCRIPTION

**What Happened:**  
The Post Invoice Adjustment tool within the finance platform experienced a system failure that prevented sales representatives from processing refunds and credits for customer accounts. The tool returned error messages when attempting to execute adjustment transactions.

**Systems Affected:**
- Primary: Finance Platform – Post Invoice Adjustment Tool
- Integrated: Backend finance systems
- Related: Billing and invoicing platforms

---

#### 3. IMPACT ASSESSMENT

| Impact Category | Assessment | Details |
|-----------------|------------|---------|
| **Operational** | High | 20+ sales representatives unable to perform core job functions |
| **Customer** | Medium-High | 20+ customer accounts unable to receive refunds/credits; customer escalations reported |
| **Financial** | Low-Medium | No revenue impact; delayed refund processing created backlog |
| **Reputational** | Medium | Customer satisfaction impacted; escalations to Client Success required |
| **Compliance** | Low | Refund processing delays; no regulatory violations identified |

**Affected Users:**
- Internal: 20+ sales representatives (US and Canada)
- External: 20+ customer accounts

**Business Impact:**
- 4-day processing backlog for refunds and credits
- Customer escalations requiring manual intervention and communication
- Reduced team productivity during outage window

---

#### 4. DETECTION & RESPONSE

**Detection Method:**
- Pattern recognition: Multiple sales representatives reporting identical error messages
- Proactive validation: Analyst replicated issue across 10 customer accounts
- Cross-team verification: Team communication channels confirmed widespread impact

**Initial Response Actions:**
1. Incident validation and scope assessment (tested 10 accounts)
2. Legal entity analysis confirmed US and Canada market impact
3. Created parent case in CRM with linked child cases for tracking
4. Gathered diagnostic evidence:
   - Screenshots of error messages
   - Video walkthroughs of failed transactions
   - Backend log analysis
   - Refund status verification
5. Cross-functional communication to validate scope
6. Escalated to Finance Systems team with comprehensive documentation

**Escalation Path:**  
Billing Support → Finance Systems Team → Product Team (ticket created)

---

#### 5. ROOT CAUSE ANALYSIS

**Identified Root Cause:**
- Code deployment error in backend finance system
- System error affecting platform integration with Post Invoice Adjustment tool

**Contributing Factors:**
- No pre-deployment testing detected integration failure
- No automated monitoring to alert on adjustment tool failures
- Manual detection through user reports (reactive vs. proactive)

**Control Failures:**
- **Preventive Control Gap:** Change management process did not catch deployment error
- **Detective Control Gap:** No automated monitoring for Post Invoice Adjustment tool availability/errors
- **Corrective Control Success:** Incident management process effectively escalated and resolved

---

#### 6. REMEDIATION & RESOLUTION

**Resolution Actions:**
- Finance Systems and Product teams deployed code fix
- Backend system error corrected
- Platform integration restored

**Post-Resolution:**
- Backlog of refund/credit requests processed
- Customer communications sent explaining delay
- Parent case and child cases closed

**Resolution Time:** 4 days from detection to full restoration

---

#### 7. RISK RATING

| Factor | Rating | Justification |
|--------|--------|---------------|
| **Likelihood** | Medium | Code deployments occur regularly; integration errors possible |
| **Impact** | High | Affects core business function (refunds/credits); customer-facing |
| **Inherent Risk** | **HIGH** | Medium likelihood × High impact |
| **Residual Risk** | **HIGH** | No preventive controls implemented post-incident |

---

### 8. RECOMMENDATIONS (Risk Mitigation)

**Immediate (0-30 days):**
1. **Implement automated monitoring** for Post Invoice Adjustment tool
   - Alert on error rate thresholds
   - Daily health checks on integration status
   - **Control Type:** Detective

**Short-term (30-90 days):**
2. **Enhance change management process** for finance system deployments
   - Require integration testing with finance tools pre-deployment
   - Implement rollback procedures for finance-critical changes
   - **Control Type:** Preventive

3. **Create incident playbook** for finance tool outages
   - Define workaround procedures where possible
   - Establish communication templates for customer-facing teams
   - Document escalation paths and SLAs
   - **Control Type:** Corrective

**Long-term (90+ days):**
4. **Establish Key Risk Indicator (KRI)** dashboard
   - Track: Adjustment tool error rate, mean time to detect, mean time to resolve
   - Monthly review with Finance Systems and Product teams
   - **Control Type:** Detective/Monitoring

---

### 9. LESSONS LEARNED

**What Worked Well:**
- Rapid pattern recognition and proactive validation
- Comprehensive documentation enabled effective escalation
- Cross-functional communication streamlined response
- Parent-child case structure maintained visibility

**Opportunities for Improvement:**
- Earlier detection through automated monitoring vs. user reports
- No workaround available; dependency on single system created complete outage
- Post-incident review not conducted; no preventive measures implemented

---

### 10. ATTACHMENTS/EVIDENCE

- Screenshots of error messages
- Video walkthrough of failed transaction attempts
- Backend log excerpts
- CRM parent case # [XXXXX]
- Product team ticket # [XXXXX]

---

**Prepared by:** Faith Babs, Support Analyst  
**Date:** March 2026  
**Review Status:** Portfolio Case Study (Sanitized)

---

## Portfolio Note

This incident demonstrates:
- Impact assessment methodology
- Root cause analysis capabilities
- Control gap identification
- Risk rating (likelihood × impact)
- Control recommendation (preventive/detective/corrective)
- Evidence-based documentation
- Stakeholder coordination and escalation management
