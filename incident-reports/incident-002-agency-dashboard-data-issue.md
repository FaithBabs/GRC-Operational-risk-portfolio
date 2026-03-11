# Operational Risk Incident Report #002
## Agency Dashboard Data Integrity Issue – Incorrect IO Display

---

#### EXECUTIVE SUMMARY

Multi-week platform incident where agency admin users experienced incorrect insertion order (IO) data display on master account dashboards. Issue affected global agency clients, resulting in IOs uploading to incorrect advertiser accounts with potential financial impact. Root cause identified as authentication session management bug introduced January 16, 2026. Resolution deployed after 7 days of investigation and testing.

**Severity:** SEV 2 – Major  
**Duration:** 7 days (initial detection to fix deployment)  
**Geographic Scope:** Global  
**Status:** Resolved

---

#### 1. INCIDENT DETAILS

| Field | Details |
|-------|---------|
| **Incident ID** | INC-2026-002 |
| **Severity Level** | SEV 2 - Major |
| **Date Detected** | February 6, 2026 |
| **Date Resolved** | February 19, 2026 |
| **Duration** | 7 days (active investigation) + 6 days (monitoring) |
| **Geographic Scope** | Global – All agency accounts |

---

#### 2. RISK EVENT DESCRIPTION

**What Happened:**  
Agency master account admin users reported seeing incorrect insertion orders (IOs) displayed on their dashboards that did not match expected account data. Further investigation revealed IOs were uploading to incorrect advertiser accounts when users were authenticated to multiple accounts/tabs simultaneously.

**Systems Affected:**
- Primary: Agency Master Dashboard
- Secondary: IO upload functionality
- Related: User authentication and session management systems

**Timeline:**
- **Jan 16, 2026:** Issue originated (linked to platform change)
- **Feb 6, 2026:** Issue formally reported and escalated
- **Feb 10, 2026:** Initial fix deployed (issue persisted)
- **Feb 13, 2026:** Parent case created (widespread impact confirmed)
- **Feb 19, 2026:** Final fix deployed and validated

---

#### 3. IMPACT ASSESSMENT

| Impact Category | Assessment | Details |
|-----------------|------------|---------|
| **Operational** | High | Agency admins unable to trust dashboard data; manual verification required for all IO uploads |
| **Customer** | High | Multiple agency clients affected; IOs uploading to incorrect advertiser accounts |
| **Financial** | Medium-High | Potential financial repercussions from misallocated advertising spend |
| **Data Integrity** | High | Core platform data accuracy compromised; trust in system reliability impacted |
| **Reputational** | Medium | Enterprise agency clients experiencing critical workflow disruption |

**Affected Users:**
- Internal: Support teams handling escalations
- External: Global agency clients (Fortune 500 enterprise accounts)

**Business Impact:**
- Incorrect IO-to-advertiser account mappings
- Manual correction required for misallocated IOs
- Client workflow disruption and trust erosion
- Increased support case volume

---

#### 4. DETECTION & RESPONSE

**Detection Method:**
- User reports: Agency admin users flagged dashboard discrepancies
- Pattern analysis: Multiple similar reports identified systemic issue
- Validation: Support analysts replicated issue and confirmed data mismatch

**Initial Response Actions:**
1. **Feb 6:** Collected diagnostic information from affected clients:
   - IO numbers and upload dates
   - Expected vs. actual advertiser ID mappings
   - Environment details (browser, OS, network, extensions)
   - Screen recordings demonstrating issue
2. **Feb 6:** Identified workaround: Close browser tabs, re-login, retry (without account switching via global nav)
3. **Feb 10:** Product deployed initial fix (issue persisted)
4. **Feb 11:** Collected additional examples; re-escalated to Product
5. **Feb 13:** Created parent case (case #20140278) to track widespread impact
6. **Feb 17-19:** Product identified root cause and deployed comprehensive fix

**Escalation Path:**  
Support → Business Operations → Product Engineering

**Workarounds Provided:**
- Close all browser tabs and re-login before IO upload
- Avoid switching advertiser accounts using global navigation bar
- Manual verification and correction of misallocated IOs
- **Authentication error workaround:** Close browser entirely (not just tabs) and open new session

---

#### 5. ROOT CAUSE ANALYSIS

**Identified Root Cause:**
- **Authentication session management bug** introduced in platform change around January 16, 2026
- Users logged into multiple tabs/accounts simultaneously caused session state conflicts
- System failed to properly isolate account context when switching between advertiser accounts

**Contributing Factors:**
- Recent platform change (EVNT-8246) not adequately tested for multi-tab/multi-account scenarios
- No automated monitoring for IO upload accuracy or account mapping validation
- Session management logic did not handle concurrent authentication states

**Control Failures:**
- **Preventive Control Gap:** Change management testing did not include multi-session scenarios
- **Detective Control Gap:** No automated validation of IO-to-account mappings post-upload
- **Corrective Control Success:** Incident response provided workarounds and coordinated fix deployment

---

#### 6. REMEDIATION & RESOLUTION

**Resolution Actions:**
- **Feb 19:** Product deployed comprehensive fix
- **New functionality:** Pop-up notification when user logged into multiple tabs/accounts alerts them of logout due to different account authentication
- **Validation:** Fix tested and confirmed across multiple agency accounts
- **Monitoring:** Continued observation for additional edge cases post-deployment

**Post-Resolution:**
- Parent case remained open for monitoring (closed after validation period)
- Support teams updated to close workaround communications
- Product team implementing preventive measures to avoid recurrence

**Resolution Time:** 13 days from initial detection to validated fix

---

#### 7. RISK RATING

| Factor | Rating | Justification |
|--------|--------|---------------|
| **Likelihood** | Medium | Platform changes occur regularly; multi-session scenarios common |
| **Impact** | High | Direct financial impact potential; data integrity compromise; enterprise client trust |
| **Inherent Risk** | **HIGH** | Medium likelihood × High impact |
| **Residual Risk** | **MEDIUM** | Fix deployed; preventive measures in progress |

---

#### 8. RECOMMENDATIONS (Risk Mitigation)

**Immediate (0-30 days):**
1. **Implement automated IO upload validation**
   - Post-upload verification: IO mapped to intended advertiser account
   - Alert on account mapping discrepancies
   - **Control Type:** Detective

2. **Enhance session management monitoring**
   - Track multi-tab/multi-account authentication patterns
   - Alert on session state conflicts
   - **Control Type:** Detective

**Short-term (30-90 days):**
3. **Expand change management testing scope**
   - Mandatory multi-session/multi-account testing for authentication changes
   - User acceptance testing (UAT) with agency clients for critical workflows
   - **Control Type:** Preventive

4. **Develop IO upload audit trail**
   - Log all IO uploads with account context and user session details
   - Enable retroactive analysis of misallocations
   - **Control Type:** Detective/Forensic

**Long-term (90+ days):**
5. **Establish data integrity KRIs**
   - Track: IO upload accuracy rate, account mapping errors, session conflict incidents
   - Monthly review with Product and Engineering teams
   - **Control Type:** Monitoring

---

#### 9. LESSONS LEARNED

**What Worked Well:**
- Rapid escalation from support to Product engineering
- Effective workaround communication reduced impact
- Parent case structure enabled tracking of widespread issue
- Continuous updates to stakeholders maintained transparency
- Cross-functional coordination (Support, BusOps, Product) streamlined resolution

**Opportunities for Improvement:**
- Initial fix (Feb 10) did not resolve issue; additional validation needed pre-deployment
- Multi-session scenarios should be standard in platform testing
- Automated detection would have identified issue faster than user reports
- Financial impact assessment not formally conducted

---

#### 10. COMMUNICATION & STAKEHOLDER MANAGEMENT

**Internal Communications:**
- Daily BusOps updates broadcast to support teams (Feb 6 - Feb 19)
- Incident broadcast sent via Slack and email
- Parent case chatter updates for cross-team visibility

**External Communications:**
- Client-facing reps provided workaround guidance
- Transparency on investigation status and expected resolution timeline

**Stakeholder Coordination:**
- Support teams: Case triage and workaround implementation
- BusOps: Status updates and cross-team coordination
- Product Engineering: Root cause investigation and fix deployment
- Agency clients: Workflow guidance and impact mitigation

---

#### 11. ATTACHMENTS/EVIDENCE

- Parent case # 20140278
- Product work item notes and timeline
- BusOps update history (Feb 6 - Feb 19)
- Client-reported examples (IO numbers, advertiser ID mappings)
- Incident broadcast communications

---

**Prepared by:** Faith Babs, Support Analyst  
**Date:** March 2026  
**Review Status:** Portfolio Case Study (Sanitized)

---

#### Portfolio Note

This incident demonstrates:
- ✅ Complex multi-stakeholder incident coordination
- ✅ Workaround development and communication
- ✅ Data integrity risk assessment
- ✅ Financial impact consideration
- ✅ Long-duration incident management (13 days)
- ✅ Post-incident monitoring and validation
- ✅ Preventive control recommendations
