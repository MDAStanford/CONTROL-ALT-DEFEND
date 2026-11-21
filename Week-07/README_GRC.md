# Week 7 — The $90,000 Security Budget

**Control + Alt + Defend | Northwind Healthcare**

*Fictional risk assessment exercise; proposed decisions, not verified remediation.*

## Objective

Evaluate seven security risks and allocate a $90,000 remediation budget.

**My approach:** Before spending money, determine whether the problem can be corrected using existing resources. Prioritize business continuity, patient safety, and measurable risk reduction.

## Risk Assessment

| Risk | Finding | Likelihood | Impact | Score | Rating |
|---|---|---:|---:|---:|---|
| R1 | Shared integration keys | 3 | 4 | 12 | Medium |
| R2 | Weak administrator authentication | 3 | 4 | 12 | Medium |
| R3 | Unsupported reminder server | 3 | 4 | 12 | Medium |
| R4 | Security awareness gaps | 3 | 3 | 9 | Medium |
| R5 | Missing SOC 2 audit evidence | 5 | 3 | 15 | High |
| R6 | Missing EDR on production servers | 3 | 4 | 12 | Medium |
| R7 | Unauthorized patient data transfer | 5 | 4 | 20 | High |

*R7 likelihood reflects an ongoing, confirmed contractual data-handling violation—not the probability of an external attack.*

## Decisions & Reasoning

### 1. Funded Remediation — $75,000

| Risk | Allocation | Decision & Reasoning |
|---|---:|---|
| R1 | $25,000 | Eliminate shared integration credentials and establish individual accountability. |
| R2 | $12,000 | Strengthen administrator authentication and reduce privileged access exposure. |
| R3 | $8,000 | Isolate the unsupported reminder server. Consider shutdown if operationally feasible. |
| R6 | $30,000 | Deploy Endpoint Detection and Response (EDR) to 13 additional servers. Prioritize business continuity and patient safety against ransomware exposure. |
| **Total** | **$75,000** | |

### 2. Operational & Contractual Remediation — $0

| Risk | Decision | Reasoning |
|---|---|---|
| R4 | Management enforcement | “We need to establish a culture of security, not throw money at it.” |
| R5 | Correct evidence retention | Fix ownership, documentation, and sign-off using existing systems rather than purchase $18,000 in tooling. |
| R7 | Enforce vendor obligations | Reject continued unauthorized patient-data transfers. Require correction and verification before approving additional expenditure. |

Choosing not to fund these items does not mean accepting their risks. Each requires corrective action and verification.

## Residual Risks & Dependencies

| Risk | Outstanding Requirement |
|---|---|
| R1–R2 | Verify access-control improvements |
| R3 | Validate isolation or approve shutdown |
| R4 | Measure training completion and enforce accountability |
| R5 | Address missing historical evidence with the auditor |
| R6 | Confirm EDR coverage and disclose the remaining exception to the insurer |
| R7 | Verify the vendor's correction and investigate previously transferred patient data |

## Budget Summary

| Category | Amount |
|---|---:|
| Available budget | $90,000 |
| Funded remediation | $75,000 |
| Operational and contractual remediation | $0 |
| **Unallocated reserve** | **$15,000** |

## Final Assessment

The objective was not to spend the entire budget. It was to identify which risks required financial investment and which could be addressed through operational accountability or contractual enforcement.

The $15,000 reserve provides flexibility for unexpected remediation costs.

**Success depends on verified risk reduction, not simply money saved.**
