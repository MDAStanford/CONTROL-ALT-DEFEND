# IAM Assessment — Part 1: Permission Review

## Scenario and scope

Independent access review of an AI-powered support agent at a **fictional healthcare SaaS provider**. The case is adapted and paraphrased from a Northwind Health cybersecurity learning challenge; organization and identity names are anonymized. This is a training case study, not an assessment of a production environment.

The AI agent answers clinic staff questions about appointment and billing status, creates support tickets, and drafts responses for human approval. Its service account is a **non-human identity (NHI)**. The review evaluates whether nine existing permissions are justified by these assigned responsibilities.

## Permission decisions

| # | Existing permission | Decision | Rationale |
|---|---|---|---|
| 1 | Read help-center articles | **Needed** | Relevant help-center documentation supports accurate answers to clinic staff questions. Access should be limited to material relevant to the agent's duties. |
| 2 | Read all patient records (full ePHI) | **Not needed** | Appointment and billing inquiries do not require unrestricted access to complete medical records. **Least privilege** and **data minimization** support limiting access to only necessary patient information. |
| 3 | Read billing summaries | **Needed** | Reporting billing status is a core business function. Summaries can indicate whether an invoice is **open, paid, or pending** without exposing full payment records. |
| 4 | Read full billing and payment data | **Not needed** | The agent reports billing status; it does not process payments. Full transaction and payment data exceed the stated business need. |
| 5 | Update patient contact details | **Not needed** | The agent answers questions, creates tickets, and drafts responses; it is not authorized to change patient information. |
| 6 | Issue refunds up to $500 without approval | **Not needed** | The agent reports billing information rather than processing refunds. Autonomous refund authority exceeds **least privilege** and raises **separation of duties** concerns. |
| 7 | Send email as the support mailbox | **Not needed** | The agent drafts replies **for human approval**; unrestricted authority to send as the support mailbox could bypass that review. |
| 8 | Create and update support tickets | **Needed with conditions** | Creating tickets is explicitly authorized. Updating should be limited to defined workflows, such as adding relevant information to authorized tickets; no unrestricted modification. |
| 9 | Delete ticket history | **Not needed** | Deletion is outside the agent's duties and would undermine auditability and record integrity. Records should follow the organization's retention policy. |

## Review summary

- **Needed:** 2 permissions
- **Needed with conditions:** 1 permission
- **Not needed:** 6 permissions

The review distinguishes the AI agent's business function from the access granted to its **non-human identity (NHI)**. Key principles include **least privilege**, **data minimization**, **separation of duties**, human approval for communications, and auditability.

## Assessment status

**Part 1 complete — permission classifications.** Other challenge components (identity governance findings, activity review, and target-state controls) are not yet assessed.

*This document presents an IAM permission review of a fictional scenario. It does not claim hands-on validation in a live system.*
