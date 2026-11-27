# IAM: Who Approved This App?
*Control + Alt + Defend | Application Consent Governance*

**Scenario:** Northwind — November 23, 2026

This is a tabletop exercise. None of the proposed controls have been implemented or tested.

## Scenario overview

Employees can give apps access to company data without IT approval or monitoring. Management wants to fix this without taking away Marketing's email tool.

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
| 1 — Immediate | DocuSharePro | 112 users, broad access to mail and files, unusual approval activity and no owner. |
| 2 — Urgent | ExportBot | Can read every company mailbox. Its owner left and its secret has never been changed. |
| 3 — Prompt | PDF Tools Online | Can read and change files, comes from an unverified publisher, has not been used in 190 days and has no known business need. |

| Probably fine | Rationale |
|---|---|
| SchedulePro | It reads calendars to help employees schedule meetings. |
| HRLink | It has 118 users but only needs basic profile information for sign-in. |

Acceptable risk is not zero risk.

## Deliverable 2 — Application access review

**Question:** Decide all eight: a table with keep, restrict or remove for each, and one line of reasoning.

**Response:** 2 keep, 4 restrict, 2 remove.

| App | Decision | Reasoning and action |
|---|---|---|
| DocuSharePro | REMOVE | Remove access for all 112 users. The app has too much access, unusual activity and no owner. |
| PDF Tools Online | REMOVE | Remove access for all 17 users. The app is unused and has too much access. |
| SchedulePro | RESTRICT | Limit access to free/busy calendar information if possible. Name an owner. |
| MailMerge Plus | RESTRICT | Allow only approved Marketing staff to use it. Monitor outgoing email and name an owner. |
| TaskBoard | RESTRICT | Check whether it needs to change calendars. Remove access it does not need and name an owner. |
| ExportBot | RESTRICT | Name a new owner, replace the secret and limit access to the mailboxes needed for the report. |
| HRLink | KEEP | It only needs basic profile information. Name an owner. |
| SignFast | KEEP | It only accesses selected files. Check that documents are protected and name an owner. |

## Deliverable 3 — The 112 people

**Question:** Your first three actions on DocuSharePro, in order, and why each comes where it does.

### Approval activity

112 users approved the app, including 83 over the weekend. The publisher registered on November 18. The app was still running automatically on November 23.

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
| 1. Contain | Remove access for all 112 users, block new approvals and check that existing access tokens no longer work. | Stop the app from accessing more data. |
| 2. Investigate | Review activity for all 112 accounts, preserve evidence and fix any damage found. | Find out what happened and how much data was affected. |
| 3. Prevent recurrence | Limit what employees can approve, require IT approval for higher-risk apps and monitor approvals. | Stop the same problem from happening again. |

The activity is suspicious, but we do not know whether any data was stolen.

## Deliverable 4 — Future approval policy

**Question:** No more than four sentences on who can approve what, and how Marketing's tool keeps working.

**Response**

1. Employees can only approve apps from verified publishers that request approved, low-risk permissions.
2. Apps that request higher-risk permissions or come from unverified publishers need IT Security approval and a written business reason from a named owner.
3. Log every app approval and alert IT Security.
4. Keep MailMerge Plus running with admin approval, limit access to approved Marketing staff, and monitor and audit outgoing email.

## Bonus — ExportBot

**Question:** ExportBot is built in-house and used every night, which makes it look safe. Why could it be more dangerous than DocuSharePro?

**Response:** ExportBot can read every company mailbox without anyone signing in. Its former owner may still have the secret, which creates a potential insider threat affecting the entire company.

| Risk factor | DocuSharePro | ExportBot |
|---|---|---|
| Access type | Delegated | Application |
| Mailbox exposure | 112 users | Entire company |
| Ownership | None | Owner left |
| Business necessity | Unknown | Established |
| Suspicious activity | Observed | None reported |

The owner left five weeks ago, and the secret has not been changed since March 2025. There is no evidence of insider misuse.

## Key takeaways

- A verified publisher does not mean an app is safe.
- A useful app should not have more access than it needs.
- Non-human identities need owners, and their credentials need to be managed and rotated.
- Deal with immediate threats first, without ignoring other serious risks.
- Protect the business without getting in the way of legitimate work.
