# IAM: Who Approved This App?
*Control + Alt + Defend | Application Consent Governance*

**Scenario:** Northwind — November 23, 2026

This is a tabletop exercise; controls are proposed, not implemented or tested.

## Scenario overview

Employees can authorize third-party applications without IT review or monitoring. Management wants risky access addressed without disrupting Marketing's valuable email tool.

## Application inventory

| App | Publisher | Permissions | Type | Users | Owner |
|---|---|---|---|---:|---|
| SchedulePro | Verified | Profile, calendar read | Delegated | 64 | Sales Ops |
| DocuSharePro | Unverified | Mail read, files read/write, offline access | Delegated | 112 | None |
| MailMerge Plus | Verified | Send mail as user, read contacts | Delegated | 9 | Marketing |
| HRLink | Verified | Basic profile | Delegated | 118 | HR |
| PDF Tools Online | Unverified | All files read/write | Delegated | 17 | None |
| SignFast | Verified | Selected files read/write | Delegated | 31 | Legal |
| TaskBoard | Verified | Profile, calendar read/write | Delegated | 41 | Engineering |
| ExportBot | In-house | All mailboxes read | Application | All | Departed employee |

## Deliverable 1 — Triage

**Question:** Pick the three apps you'd act on first, in order, with one line each. Name two that look worrying but are probably fine, and say why.

**Response**

| Priority | App | Rationale |
|---|---|---|
| 1 — Immediate | DocuSharePro | Large attack surface, extensive permissions, suspicious approval activity and no ownership. |
| 2 — Urgent | ExportBot | Company-wide blast radius, orphaned ownership and unchanged application secret. |
| 3 — Prompt | PDF Tools Online | Excessive permissions, unverified publisher, dormant for 190 days and no established business need. |

| Probably fine | Rationale |
|---|---|
| SchedulePro | Calendar access is read-only and supports a legitimate scheduling function. |
| HRLink | Despite 118 connected users, access is limited to basic profile information for authentication. |

Acceptable risk is not zero risk.

## Deliverable 2 — Application access review

**Question:** Decide all eight: a table with keep, restrict or remove for each, and one line of reasoning.

**Response:** 2 keep, 4 restrict, 2 remove.

| App | Decision | Reasoning and action |
|---|---|---|
| DocuSharePro | REMOVE | Revoke access due to excessive permissions, suspicious activity and lack of ownership. |
| PDF Tools Online | REMOVE | Revoke dormant, excessive permissions for all 17 users. |
| SchedulePro | RESTRICT | Reduce calendar access to free/busy availability if supported; assign named owner. |
| MailMerge Plus | RESTRICT | Limit to authorized Marketing personnel, monitor outbound email and assign named owner. |
| TaskBoard | RESTRICT | Validate calendar write requirements, remove unnecessary permissions and assign named owner. |
| ExportBot | RESTRICT | Assign new ownership, rotate credentials and reduce mailbox access to business requirements. |
| HRLink | KEEP | Minimal permissions are appropriate; assign named owner. |
| SignFast | KEEP | File access is appropriately scoped; validate document safeguards and assign named owner. |

## Deliverable 3 — The 112 people

**Question:** Your first three actions on DocuSharePro, in order, and why each comes where it does.

### Approval activity

112 users; 83 weekend approvals. Publisher registered November 18. Automatic activity continues on November 23.

| Date | Approvals |
|---|---:|
| Fri 20 | 6 |
| Sat 21 | 31 |
| Sun 22 | 52 |
| Mon 23 | 23 |

Monday is a partial day.

**Response**

| Sequence | Action | Rationale |
|---|---|---|
| 1. Contain | Revoke all 112 consent grants, block further approvals and verify existing tokens can no longer be used. | Stop further exposure. |
| 2. Investigate | Run activity reports for all affected accounts, preserve evidence and remediate identified damage. | Determine whether compromise occurred and establish its extent. |
| 3. Prevent recurrence | Implement consent restrictions, administrative approval and monitoring. | Address the underlying governance failure. |

Suspicious activity warrants containment, but data theft has not been confirmed.

## Deliverable 4 — Future approval policy

**Question:** No more than four sentences on who can approve what, and how Marketing's tool keeps working.

**Response**

1. Employees may only approve applications from verified publishers requesting approved, low-risk permissions.
2. Applications requesting elevated permissions or coming from unverified publishers require IT Security approval and documented business justification from a named business owner.
3. All application approvals must be logged and generate alerts for IT Security.
4. MailMerge Plus will remain operational under administrative approval, with access restricted to authorized Marketing personnel and outbound email activity monitored and audited.

## Bonus — ExportBot

**Question:** ExportBot is built in-house and used every night, which makes it look safe. Why could it be more dangerous than DocuSharePro?

**Response:** ExportBot has access to every company mailbox and operates independently of interactive user authentication. Its former owner may still possess the unchanged application secret, creating a potential insider threat with a company-wide blast radius.

| Risk factor | DocuSharePro | ExportBot |
|---|---|---|
| Access type | Delegated | Application |
| Mailbox exposure | 112 users | Entire company |
| Ownership | None | Orphaned |
| Business necessity | Unknown | Established |
| Suspicious activity | Observed | None reported |

The owner departed five weeks ago; the secret has remained unchanged since March 2025. No insider misuse has been established.

## Key takeaways

- Verified publishers are not necessarily secure publishers.
- Legitimate business functions do not justify excessive permissions.
- Non-human identities require ownership and credential lifecycle management.
- Risk prioritization must distinguish immediate threats from potential exposure.
- Security controls should protect the business without unnecessarily disrupting it.
