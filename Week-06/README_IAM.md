# Week 06 — Billing System Access Cleanup

## Overview

Employees inherited billing-system permissions from coworkers rather than receiving access based on their jobs. Some now have unnecessary or conflicting permissions.

**Recommendation:** Set access by role, remove excess permissions, and test before rollout.

## Deliverables

### 1. Role Structure

| Job Title | Duties | Permissions Needed |
|---|---|---|
| Finance Analyst | Review billing records | View invoices |
| Billing Specialist | Process invoices and refunds | View, create, edit invoices; issue refunds |
| Finance Manager | Oversee billing and authorize refunds | View invoices; approve refunds |
| Support Agent | Answer billing questions | View invoices |
| IT Admin | Maintain system configuration | Manage settings |
| External Auditor | Review records for compliance | View invoices |

Deleting invoices is not standard access. Exporting patient billing data requires separate approval.

### 2. Access Review

| Employee | Remove |
|---|---|
| Ana | Export |
| Ben | Export |
| Chloe | Create, edit, export |
| Farid | Delete, approve refunds, export |
| Hana | Create, edit, delete, issue refunds, export, admin settings |
| Jo | Issue refunds |
| Kai | View invoices |
| Lena | Edit, export |

**18 excess permissions** identified. Dev, Elena, Grace, and Ivan already match their proposed roles.

**Highest risk:** Farid and Hana can approve and issue refunds, create and delete invoices, and edit invoices while approving refunds. Those combinations must be separated.

### 3. Remediation

1. Confirm job requirements and record current access.
2. Remove excess permissions, starting with Farid and Hana; pilot and roll out in stages with a rollback plan.
3. Test allowed and blocked actions, retain evidence, and review access quarterly.

**Status:** Recommendations only; no live accounts changed.
