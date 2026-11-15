# Week 06 — IAM: The Role Cleanup

## Proposed access

| Employee | Role | Allowed access | Remove |
|---|---|---|---|
| Ana | Finance Analyst | View invoices | Export |
| Ben | Finance Analyst | View invoices | Export |
| Chloe | Finance Analyst | View invoices | Create, edit, export |
| Dev | Billing Specialist | View, create, edit invoices; issue refunds | — |
| Elena | Billing Specialist | View, create, edit invoices; issue refunds | — |
| Farid | Billing Specialist | View, create, edit invoices; issue refunds | Delete, approve refunds, export |
| Grace | Billing Specialist | View, create, edit invoices; issue refunds | — |
| Hana | Finance Manager | View invoices; approve refunds | Create, edit, delete, issue refunds, export, admin |
| Ivan | Support Agent | View invoices | — |
| Jo | Support Agent | View invoices | Issue refunds |
| Kai | IT Admin | Manage system settings | View invoices |
| Lena | External Auditor | View invoices | Edit, export |

**Export:** No standing export permission in standard roles. Hana confirms the business need; approved access is assigned by Kai, preferably temporarily where supported. Invoice views should exclude unnecessary patient details where supported.

## Three conflicts

| Forbidden combination | Original accounts |
|---|---|
| Approve and issue refunds | Farid, Hana |
| Create and delete invoices | Farid, Hana |
| Edit invoices and approve refunds | Farid, Hana |

Temporary access must not bypass these rules. A manager who edited an invoice must not approve a refund involving that invoice later. Test that the system blocks this and permits independent approval; confirm the application can enforce it.

## Safe rollout

1. Record current access and confirm job requirements.
2. Correct Farid's and Hana's high-risk conflicts first.
3. Pilot with a small group; test allowed and blocked actions.
4. Fix failures, retest, and expand in stages; keep a rollback plan.
5. Audit final access and approved exceptions; repeat reviews quarterly.

Keep test results, screenshots, and logs in a secure evidence repository.

**Finding:** 18 excess individual permission grants identified for review/removal. These are proposed changes, not live account changes.
