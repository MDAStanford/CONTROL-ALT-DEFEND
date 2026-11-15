# Week 06 — Billing System Access Cleanup

## Overview

Billing-system permissions were copied between employees without checking what each job required. This left some people with unnecessary access and created conflicts around invoices and refunds.

**Recommendation:** Define access by job, remove unnecessary permissions, and test the changes before rolling them out.

## Deliverables

### 1. Proposed Roles and Permissions

| Job Title | Description of Duties | Permissions Needed |
|---|---|---|
| Finance Analyst | Review billing records | View invoices |
| Billing Specialist | Process invoices and refunds | View, create, edit invoices; issue refunds |
| Finance Manager | Oversee billing and authorize refunds | View invoices; approve refunds |
| Support Agent | Answer billing questions | View invoices |
| IT Admin | Maintain system configuration | Manage system settings |
| External Auditor | Review billing records for compliance | View invoices |

No standard role can delete invoices. Exporting patient billing data requires separate approval.

### 2. Access Review

Eight employees have extra permissions. **Farid and Hana are the highest priorities** because their access combines duties that should be separate.

| Employee | Permissions to Remove |
|---|---|
| Ana | Export billing data |
| Ben | Export billing data |
| Chloe | Create invoices, edit invoices, export billing data |
| Farid | Delete invoices, approve refunds, export billing data |
| Hana | Create invoices, edit invoices, delete invoices, issue refunds, export billing data, manage settings |
| Jo | Issue refunds |
| Kai | View invoices |
| Lena | Edit invoices, export billing data |

**Total:** 18 permission grants proposed for removal. Dev, Elena, Grace, and Ivan already match their proposed roles.

### 3. Conflicting Duties

One person should not be able to:

- Approve **and** issue refunds.
- Create **and** delete invoices.
- Edit invoices **and** approve refunds.

Farid and Hana currently have all three conflicts.

### 4. Safe Cleanup Plan

1. Confirm job needs and record existing permissions.
2. Remove Farid's and Hana's conflicting access first.
3. Pilot the new roles; test both permitted and blocked actions.
4. Fix problems and roll out in stages, with a rollback plan.
5. Save evidence, check final permissions, and review access quarterly.

**Status:** Proposed changes only; no live accounts were modified.
