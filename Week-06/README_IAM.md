# Week 06 — IAM: The Role Cleanup

## Overview

Access to the billing system has grown without clear rules. Employees inherited permissions from coworkers, leaving some with more access than their jobs require.

The goal is to assign access by job responsibility, remove unnecessary permissions, and prevent conflicting financial transactions.

## Deliverables

### 1. Role Structure

Six standard roles: Finance Analyst, Billing Specialist, Finance Manager, Support Agent, IT Admin, and External Auditor.

Each role receives only the permissions needed for its job. Patient billing exports require separate approval.

### 2. Access Review

Eight employees have excessive permissions. Farid and Hana present the highest risk.

**18 unnecessary permission grants** were identified for review or removal.

### 3. Segregation of Duties

Three prohibited combinations:

- Approving and issuing refunds.
- Creating and deleting invoices.
- Editing invoices and approving refunds.

Farid and Hana currently violate all three.

### 4. Remediation Plan

1. Document existing access.
2. Address Farid and Hana first.
3. Test new roles with a small group.
4. Correct problems and roll out in stages.
5. Audit results and review access quarterly.

### 5. Validation

Confirm employees can perform their jobs without unnecessary access. Test that conflicting transactions are blocked and retain evidence of the results.

## Supporting Detail

[Employee-by-employee access review (Google Sheet)](https://docs.google.com/spreadsheets/d/1bdljKwdV7xa1EomWg46Lw6sCnK_xmc2GxbPTYvvWMf0/edit)

*These are proposed changes, not live account modifications.*
