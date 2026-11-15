# Week 06 — IAM: The Role Cleanup

## Role catalogue

| Role | Standard permissions |
|---|---|
| Finance Analyst | VI |
| Billing Specialist | VI, CI, EI, IR |
| Finance Manager | VI, AR |
| Support Agent | VI |
| IT Admin | AD |
| External Auditor | VI |

VI = view invoices; CI = create invoices; EI = edit invoices; DI = delete invoices; AR = approve refunds; IR = issue refunds; EX = export patient billing data; AD = admin settings.

**Decision:** Assign standard access by job. DI and EX are excluded from standard roles. Export requests require a documented business reason, approval, and limited access where technically supported. Kai administers approved access but does not receive EX by default. Limit invoice views to necessary billing data where supported.

## Access outliers

| User(s) | Excess permissions to review/remove |
|---|---|
| Ana, Ben | EX |
| Chloe | CI, EI, EX |
| Farid | DI, AR, EX |
| Hana | CI, EI, DI, IR, EX, AD |
| Jo | IR |
| Kai | VI |
| Lena | EI, EX |

Dev, Elena, Grace, and Ivan already match the proposed roles. These are proposed changes, not live account modifications. Confirm business requirements before removal.

## Segregation of duties

| Forbidden combination | Original violators |
|---|---|
| Approve + issue refunds (AR + IR) | Farid, Hana |
| Create + delete invoices (CI + DI) | Farid, Hana |
| Edit invoices + approve refunds (EI + AR) | Farid, Hana |

Temporary access must not permit conflicting actions. If Hana edits an invoice, the application should block her from approving a refund involving that invoice later, even after her editing access ends. A different authorized approver can review it. Confirm the application supports transaction-level enforcement.

## Safe rollout

Record current permissions and confirm role requirements with business owners. Address Farid's and Hana's high-risk conflicts promptly. Pilot the new roles with a small group, test permitted and blocked actions, and retain screenshots, logs, and results in a secure evidence repository. Investigate failures, remediate, and retest before expanding. Keep a rollback plan. Migrate remaining users in stages, then audit actual permissions against approved roles and documented exceptions. Conduct quarterly access reviews and review access when staff change roles or leave.

**Result:** 18 excess individual permission grants identified for review/removal. Role membership replaces appropriate individual grants; this is not a count of all grants converted.
