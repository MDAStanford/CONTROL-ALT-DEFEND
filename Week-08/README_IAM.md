# IAM: Who Approved This App?
*Control + Alt + Defend | Application Consent Governance*

**Scenario:** Northwind — November 23, 2026, mid-afternoon

Tabletop exercise / no controls implemented or tested

## Scenario overview

Employees can give apps access to company data without IT approval or monitoring. Management wants to fix this without taking away Marketing's email tool.

The identity system can require admin approval, limit user consent to low-risk apps from verified publishers, remove app access for everyone or selected users, end user sessions and alert on app approvals. Only admins can approve application permissions.

## Application inventory

| App | Access | Users | Owner |
|---|---|---:|---|
| SchedulePro | Profile; calendar read | 64 | Sales Ops |
| DocuSharePro | All mail read; all files read/write; offline | 112 | None |
| MailMerge Plus | Send as user; contacts read | 9 | Marketing |
| HRLink | Basic profile (sign-in) | 118 | HR |
| PDF Tools Online | All files read/write | 17 | None |
| SignFast | Selected files read/write | 31 | Legal |
| TaskBoard | Profile; calendar read/write | 41 | Engineering |
| ExportBot | All mailboxes read | All mailboxes | J. Patel (left 5 weeks ago) |

| App | Publisher / type | First approved | Last used |
|---|---|---|---|
| SchedulePro | Verified / delegated | Mar 2025 | Today |
| DocuSharePro | Unverified / delegated | Nov 20 | Today (automatic) |
| MailMerge Plus | Verified / delegated | Jun 2025 | 2 days ago |
| HRLink | Verified / delegated | Jan 2025 | Today |
| PDF Tools Online | Unverified / delegated | Mar 2026 | 190 days ago |
| SignFast | Verified / delegated | Aug 2025 | Yesterday |
| TaskBoard | Verified / delegated | Oct 2025 | Today |
| ExportBot | In-house / application | Mar 2025 | Today, 03:00 (nightly) |

DocuSharePro's publisher registered on Nov 18, 2026.

IT did not approve DocuSharePro or PDF Tools Online. ExportBot builds a nightly clinic-usage report.

## Deliverable 1 — Triage

**Question:** Pick the three apps you'd act on first, in order, with one line each. Name two that look worrying but are probably fine, and say why.

**Response**

| Priority | App | Rationale |
|---|---|---|
| 1 — Immediate | DocuSharePro | 112 users, 83 weekend approvals, broad mail and file access, offline access, a new unverified publisher and no owner. |
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
| PDF Tools Online | REMOVE | Remove access for all 17 users. The app has not been used in 190 days and has too much access. |
| SchedulePro | RESTRICT | Limit calendar access to free/busy information if supported. Confirm a named individual owner within Sales Ops. |
| MailMerge Plus | RESTRICT | Keep all 9 Marketing users working. Limit access and consent eligibility to authorized Marketing staff; require admin approval, monitor mail, apply sending limits if supported and confirm a named Marketing owner. |
| TaskBoard | RESTRICT | Check whether calendar write access is needed and remove unnecessary permissions. Confirm a named individual owner within Engineering. |
| ExportBot | RESTRICT | Name a new owner, replace the secret and limit mailbox access to what the report needs. Test the report and promptly retire the old secret. |
| HRLink | KEEP | It only needs basic profile information for sign-in. Confirm a named point of contact within HR. |
| SignFast | KEEP | It only accesses files selected by the user. Check protections for sensitive documents and confirm a named Legal contact. |

## Deliverable 3 — The 112 people

**Question:** Your first three actions on DocuSharePro, in order, and why each comes where it does.

### Approval activity

112 users approved the app, including 83 over the weekend. The publisher registered on November 18, 2026. The app was still accessing accounts automatically on November 23.

| Date | Approvals |
|---|---:|
| Fri Nov 20 | 6 |
| Sat Nov 21 | 31 |
| Sun Nov 22 | 52 |
| Mon Nov 23 | 23 |
| **Total** | **112** |

Monday is a partial day.

**Response**

| Sequence | Action | Rationale |
|---|---|---|
| 1. Contain | Remove access for all 112 users, block new approvals and verify existing tokens cannot access company data. End affected user sessions where necessary. | Stop the app from accessing more data. |
| 2. Investigate | Review activity for all 112 accounts from November 20 onward, preserve evidence and fix any damage found. | Find out what happened and how much data was affected. |
| 3. Prevent recurrence | Limit what employees can approve, require IT approval for higher-risk apps and monitor approvals. | Stop the same problem from happening again. |

The activity is suspicious, but we do not know whether any data was stolen.

## Deliverable 4 — Future approval policy

**Question:** No more than four sentences on who can approve what, and how Marketing's tool keeps working.

**Response**

1. Employees can only approve delegated permissions from verified publishers requesting approved, low-risk access.
2. All application permissions, higher-risk delegated permissions and apps from unverified publishers require IT Security admin approval and a written business reason from a named owner.
3. Log every app approval and alert IT Security.
4. Keep MailMerge Plus running for its 9 existing Marketing users under admin approval without repeated approval requests, limit access to authorized Marketing staff, and monitor outgoing email with sending limits where supported.

## Bonus — ExportBot

**Question:** ExportBot is built in-house and used every night, which makes it look safe. Why could it be more dangerous than DocuSharePro?

**Response:** ExportBot can read every company mailbox without anyone signing in or completing multi-factor authentication (MFA). Its former owner may still have the secret, but anyone who obtains it could potentially access company-wide email. This creates a potential insider threat and a much larger mailbox exposure than DocuSharePro.

| Risk factor | DocuSharePro | ExportBot |
|---|---|---|
| Access type | Delegated | Application |
| Mailbox exposure | 112 users | Entire company |
| Ownership | None | Owner left |
| Business necessity | Unknown | Established |
| Suspicious activity | Observed | None reported |

The owner left five weeks ago, and the secret was created in March 2025 and has never been changed. No insider misuse has been reported.

## Key takeaways

- A verified publisher does not mean an app is safe.
- A useful app should not have more access than it needs.
- Non-human identities need owners, and their credentials need to be managed and rotated.
- Deal with immediate threats first, without ignoring other serious risks.
- Protect the business without getting in the way of legitimate work.
