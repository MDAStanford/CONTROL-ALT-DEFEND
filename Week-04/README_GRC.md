# Control + Alt + Defend — Week 4: GRC Vendor Security Assessment

**Assessment:** Third-party vendor security risk review  
**Overall decision:** **FAIL / DOES NOT MEET**  
**Approval:** Withheld pending remediation and reassessment

> Exercise assessment based on vendor questionnaire responses. A failed internal vendor assessment is not a formal SOC 2 audit opinion. Findings reflect the proposed organization's control expectations and should be validated against its contractual and regulatory obligations.

## DELIVERABLE 1 — Vendor Questionnaire Assessment

| # | Control area | Vendor response / evidence | Decision |
|---|---|---|---|
| 1 | Encryption | Technical encryption standards and implementation not adequately specified | **DOES NOT MEET** |
| 2 | Multi-factor authentication (MFA) | MFA is applied to some personnel rather than all applicable users | **DOES NOT MEET** |
| 3 | Independent assurance | SOC 2 Type I report issued 11 months ago, covering Security criteria | **DOES NOT MEET** |
| 4 | Subprocessors | “We use trusted cloud providers.” | **CONDITIONALLY ACCEPTED** — evidence required |
| 5 | Breach notification | “Within 10 business days of confirming a breach.” | **DOES NOT MEET** pending applicable notification requirements |
| 6 | Business Associate Agreement (BAA) | “We sign our standard BAA. We don't negotiate changes.” | **DOES NOT MEET** pending acceptable executed agreement |
| 7 | Data deletion | “Within 12 months” after contract termination | **DOES NOT MEET** |
| 8 | Incident history (additional review item) | “No incidents to report.” | **FURTHER VERIFICATION REQUIRED** |

### Findings and required evidence

**1. Encryption — DOES NOT MEET**
- Identify encryption methods, key management, data coverage, and relevant providers.
- Verify the controls against the organization's documented standards rather than accepting generic claims.

**2. MFA — DOES NOT MEET**
- Require MFA for applicable workforce and privileged access.
- Least privilege limits authorization; it is not a substitute for strong authentication.

**3. Independent assurance — DOES NOT MEET**
- An 11-month-old SOC 2 Type I report addresses control design at a point in time, not operating effectiveness over a period.
- Obtain SOC 2 Type II or acceptable equivalent evidence of operating effectiveness and review it annually.

**4. Subprocessors — CONDITIONALLY ACCEPTED**
- Obtain named subprocessors, services provided, data categories accessed, processing locations, and relevant safeguards.
- Reassess if the vendor cannot substantiate the response.

**5. Breach notification — DOES NOT MEET**
- Assess the proposed 10-business-day period against applicable laws, the BAA, and organizational response obligations.
- Require enforceable notification and escalation deadlines that allow the organization to meet its own obligations.

**6. BAA — DOES NOT MEET**
- Obtain legal and compliance review of the vendor's standard BAA.
- Require an acceptable, executed BAA when protected health information is involved; a refusal to negotiate is not itself proof of noncompliance, but unacceptable terms block approval.

**7. Data retention and deletion — DOES NOT MEET**
- The proposed 12-month period lacks a documented justification.
- Establish a contractual target of deletion within 30–90 days, subject to justified legal or regulatory exceptions.
- Define backup expiration and require written deletion confirmation.

**8. Incident history — FURTHER VERIFICATION REQUIRED**
- Request an appropriate summary of incidents, investigations, and remediation over the preceding 18 months, subject to confidentiality and access restrictions.
- A vendor's assertion of no incidents is not independently verified by that assertion alone.

## DELIVERABLE 2 — Risk Assessment and Decision

**Final decision: FAIL / DOES NOT MEET.**

Principal concerns:
- Inconsistent MFA coverage and unauthorized-access exposure.
- Insufficient independent evidence that controls operate effectively.
- Unidentified subprocessors and limited data-processing visibility.
- Potentially unsuitable breach-notification commitments.
- Unresolved BAA terms and unjustified post-termination data retention.

**Recommendation:** Do not approve the vendor at this stage. Document remediation owners and evidence requirements, then reassess the vendor before approval. The conditional subprocessor finding does not override the overall failed assessment.

## DELIVERABLE 3 — Three Vendor Follow-Up Questions

1. **Independent security assurance:** Can you provide a current SOC 2 Type II report or equivalent independent evidence that your security controls have operated effectively over time?
2. **Subprocessor transparency:** Can you provide a complete list of subprocessors, their responsibilities, the data they access, and the locations where that data is stored or processed?
3. **Retention and deletion:** Can you contractually commit to deleting customer data within 90 days of termination, identify justified legal and backup exceptions, and provide written confirmation of deletion?

## DELIVERABLE 4 — Contract Requirements

**Status: FINALIZED / APPROVED**

1. **Annual independent security assurance:** Require an annual SOC 2 Type II report or equivalent independent assessment, with documented remediation of significant findings.
2. **Acceptable BAA:** Require a mutually acceptable, executed Business Associate Agreement covering electronic protected health information (ePHI), breach notification, subcontractors, and data retention/deletion obligations.
3. **Security governance and audit cadence:** Require documented controls aligned with an established framework such as NIST Cybersecurity Framework (CSF) or ISO 27001, with a risk-based assessment cadence:
   - Quarterly review of high-risk controls and remediation progress.
   - Annual formal security assessment.
   - Event-driven reassessment after material changes or significant incidents.
   - Documented findings, corrective actions, and evidence of closure.

An audit schedule supports governance but does not, by itself, demonstrate framework conformity.

## FINAL DETERMINATION

**FAIL / DOES NOT MEET — VENDOR NOT APPROVED.**

Remediation and satisfactory supporting evidence are required before approval. This determination concerns the vendor's fit against the organization's security and privacy requirements; it is not an auditor's opinion on the vendor's SOC 2 examination.

## BONUS — Response to Sales (Friday Deadline)

**Two-sentence response:**

> Can you clarify what's driving the Friday deadline and whether the vendor needs immediate access to sensitive data? We can develop a phased remediation plan with owners, deadlines, and compensating controls, but vendor approval and production access must wait until critical security and contractual requirements are satisfied.

**Action plan:**
- Maintain **FAIL / DOES NOT MEET** and withhold approval.
- Identify missing evidence and contractual requirements; assign owners and target dates.
- Work with the vendor and Sales on milestones and periodic status reviews; remediation may take months.
- Consider a limited, separately authorized pilot using synthetic data only, without production access or protected health information.
- Reassess after remediation and evidence review before granting approval.
