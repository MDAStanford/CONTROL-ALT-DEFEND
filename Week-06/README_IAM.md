# Week 06 — IAM: The Role Cleanup

## Role catalogue (proposed)

| Role | Standard permissions |
|---|---|
| Finance Analyst | VI |
| Billing Specialist | VI, CI, EI, IR |
| Finance Manager | VI, AR |
| Support Agent | VI |
| IT Admin | AD |
| External Auditor | VI |

VI = view invoices; CI = create invoices; EI = edit invoices; DI = delete invoices; AR = approve refunds; IR = issue refunds; EX = export patient billing data; AD = admin settings.

**Principle:** Set standard access by job, identify excess permissions, then review exceptions individually. DI and EX are not part of any standard role. Invoice viewing should expose only billing information needed for the job, not unnecessary clinical details; the supplied VI permission does not specify field-level restrictions.

## Access outliers — working findings

| User(s) | Excess access against proposed role |
|---|---|
| Ana, Ben | EX |
| Chloe | CI, EI, EX |
| Farid | DI, AR, EX |
| Hana | CI, EI, DI, IR, EX, AD |
| Jo | IR |
| Kai | VI |
| Lena | EI, EX |

Dev, Elena, Grace, and Ivan match their proposed roles. All changes are **recommendations**, not live account changes.

## Segregation of duties — to complete

Refund approval (AR) and refund issuance (IR) should be separated. Additional conflict review pending.

## Safe rollout — to complete

Pending completion of the access review and exception process.
