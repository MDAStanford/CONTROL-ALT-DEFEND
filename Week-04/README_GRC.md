# Control + Alt + Defend — Week 4: GRC Vendor Assessment

**Decision: FAIL / DOES NOT MEET**  
**Vendor status: NOT APPROVED — remediation required**

## DELIVERABLE 1 — Questionnaire Review

| Control | Decision | Reason |
|---|---|---|
| Encryption | **Does Not Meet** | Encryption methods and evidence not provided |
| Multi-factor authentication (MFA) | **Does Not Meet** | MFA not enforced for all applicable staff; least privilege is not a substitute |
| SOC 2 | **Does Not Meet** | Type I report (11 months old) shows point-in-time design, not operating effectiveness |
| Subprocessors | **Conditional** | “Trusted cloud providers” is not an adequate inventory |
| Breach notification | **Does Not Meet** | 10 business days after confirmation needs a faster, enforceable timeline aligned to obligations |
| Business Associate Agreement (BAA) | **Does Not Meet** | Standard, nonnegotiable BAA still requires legal review and acceptable terms |
| Data deletion | **Does Not Meet** | Up to 12 months after termination; no adequate justification |
| Incident history (additional review) | **Verify** | “No incidents to report” needs supporting evidence |

## DELIVERABLE 2 — Risk Decision

**FAIL / DOES NOT MEET. No approval yet.**

- Incomplete MFA coverage.
- Insufficient independent control assurance.
- Unknown subprocessors and data-handling practices.
- Breach-notification and BAA concerns.
- Unacceptable data-retention terms.

**Next step:** Assign remediation owners, collect evidence, and reassess before approval.

## DELIVERABLE 3 — Vendor Follow-Up Questions

1. Can you provide a **SOC 2 Type II** report or equivalent evidence of operating effectiveness?
2. Can you list **all subprocessors**, their data access, responsibilities, and processing locations?
3. Will you contractually commit to **deleting customer data within 90 days**, disclose justified exceptions, and confirm deletion in writing?

## DELIVERABLE 4 — Contract Requirements

**FINALIZED**

1. **Annual assurance:** SOC 2 Type II or equivalent independent assessment; remediate significant findings.
2. **Acceptable BAA:** Executed agreement covering electronic protected health information (ePHI), breach notification, subcontractors, and deletion.
3. **Governance and audit cadence:** Controls aligned with **NIST Cybersecurity Framework (CSF)** or **ISO 27001**:
   - **Quarterly:** High-risk controls and remediation.
   - **Annually:** Formal security assessment.
   - **As needed:** Reassess after significant incidents or changes.
   - Document findings and verify closure.

## BONUS — Sales Wants Friday

**Two-sentence reply:**

> What is driving Friday's deadline, and does the vendor need access to sensitive data immediately? We can agree on a phased remediation plan, but approval and production access must wait until critical requirements are met.

**Action plan:**
- **No approval** while critical gaps remain.
- Assign owners, deadlines, and evidence requirements.
- Consider a separately approved pilot using **synthetic data only**.
- Reassess before granting production access.

---

**Final determination: FAIL / DOES NOT MEET — NOT APPROVED.**

*This is an internal vendor risk decision, not a formal SOC 2 audit opinion.*
