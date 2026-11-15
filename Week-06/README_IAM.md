# Week 06 — Billing System Access Cleanup

## Overview

Employees were given access by copying other people's permissions. Some can now do things their jobs don't require.

**My recommendation:** Give each job a defined set of permissions, remove extra access, and separate duties that could allow fraud or mistakes.

## Deliverables

### 1. Who should be able to do what?

| Job | Access needed |
|---|---|
| Finance Analyst | View invoices |
| Billing Specialist | View, create, and edit invoices; issue refunds |
| Finance Manager | View invoices; approve refunds |
| Support Agent | View invoices |
| IT Admin | Manage system settings |
| External Auditor | View invoices |

Deleting invoices is not standard access. Exporting patient billing data requires separate approval.

### 2. Whose access needs fixing?

**Farid and Hana first.** Both can perform combinations of actions that should be kept separate.

Six others also have extra permissions: **Ana, Ben, Chloe, Jo, Kai, and Lena**.

In total, **18 permission grants** need review and possible removal. The [access review sheet](https://docs.google.com/spreadsheets/d/1bdljKwdV7xa1EomWg46Lw6sCnK_xmc2GxbPTYvvWMf0/edit) shows exactly what each person should keep or lose.

### 3. What must never be combined?

- Approving **and** issuing a refund.
- Creating **and** deleting an invoice.
- Editing an invoice **and** approving its refund.

Farid and Hana currently have all three conflicts.

### 4. How would I fix it safely?

1. Save a record of current access and confirm what each job needs.
2. Resolve Farid's and Hana's conflicting access first.
3. Test the new permissions with a small group, including actions that must be blocked.
4. Fix any failures, then move everyone else over in stages. Keep a rollback option.
5. Check the final access, save test evidence, and review permissions every quarter.

**Status:** Proposed plan only. No real accounts were changed.
