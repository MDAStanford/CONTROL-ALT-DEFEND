# IAM: Who Approved This App?
*Control + Alt + Defend | Week 08*

**Organization:** Northwind  
**Date:** November 23, 2026  
**Subject:** Application access review and recommended actions

Tabletop exercise / no controls implemented or tested

## Executive summary

Northwind allows employees to connect third-party apps to their work accounts without IT approval or monitoring.

Eight applications were reviewed.

| Decision | Applications |
|---|---:|
| Remove | 2 |
| Restrict | 4 |
| Keep | 2 |

**Immediate concern:** DocuSharePro has access to 112 employee accounts, with 83 approvals occurring over the weekend. Its permissions and unusual activity warrant immediate removal and investigation.

**Additional concern:** ExportBot can read every company mailbox. Its owner left five weeks ago, and its secret has never been changed.

**Business continuity:** Preserve Marketing's email tool for its nine existing users while introducing tighter access controls.

**Management recommendation:** Approve the proposed application restrictions, incident response actions and future approval policy.

## 1. Priority findings

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

## 2. Application decisions

**Question:** Decide all eight applications: keep, restrict or remove, with one line of reasoning for each.

### Remove

| Application | Action |
|---|---|
| DocuSharePro | Remove access for all 112 users. The app has too much access, unusual activity and no owner. |
| PDF Tools Online | Remove access for all 17 users. The app has not been used in 190 days and has too much access. |

### Restrict

| Application | Action |
|---|---|
| SchedulePro | Limit calendar access to free/busy information if supported. Confirm a named individual owner within Sales Ops. |
| MailMerge Plus | Keep all 9 Marketing users working. Limit access and consent eligibility to authorized Marketing staff; require admin approval, monitor mail, apply sending limits if supported and confirm a named Marketing owner. |
| TaskBoard | Check whether calendar write access is needed and remove unnecessary permissions. Confirm a named individual owner within Engineering. |
| ExportBot | Name a new owner, replace the secret and limit mailbox access to what the report needs. Test the report and promptly retire the old secret. |

### Keep

| Application | Action |
|---|---|
| HRLink | It only needs basic profile information for sign-in. Confirm a named point of contact within HR. |
| SignFast | It only accesses files selected by the user. Check protections for sensitive documents and confirm a named Legal contact. |

## 3. Incident response — DocuSharePro

**Question:** What are your first three actions on DocuSharePro, in order, and why?

### 1. Contain

- Remove application access for all 112 users.
- Block new approvals.
- Verify existing tokens can no longer access company data.
- End affected user sessions where necessary.

**Why:** Stop further access to company data.

### 2. Investigate

- Review activity for all 112 accounts from November 20 onward.
- Preserve evidence.
- Identify unauthorized access, file changes or data exposure.
- Fix any damage found.

**Why:** Establish what happened, who was affected and what data may have been exposed.

### 3. Prevent recurrence

- Limit what employees can approve.
- Require admin approval for higher-risk applications.
- Log and monitor application approvals.

**Why:** Stop the same problem from happening again.

**Incident status:** Suspicious activity identified. Data theft has not been confirmed.

## 4. Future approval policy

**Question:** No more than four sentences on who can approve what, and how Marketing's tool keeps working.

1. Employees can only approve delegated permissions from verified publishers requesting approved, low-risk access.
2. All application permissions, higher-risk delegated permissions and apps from unverified publishers require IT Security admin approval and a written business reason from a named owner.
3. Log every app approval and alert IT Security.
4. Keep MailMerge Plus running for its 9 existing Marketing users under admin approval without repeated approval requests, limit access to authorized Marketing staff, and monitor outgoing email with sending limits where supported.

## 5. Additional risk — ExportBot

**Bonus question:** ExportBot is built in-house and used every night, which makes it look safe. Why could it be more dangerous than DocuSharePro?

**Response:** ExportBot can read every company mailbox without anyone signing in or completing multi-factor authentication (MFA). Its former owner may still have the secret, but anyone who obtains it could potentially access company-wide email. This creates a potential insider threat and a much larger mailbox exposure than DocuSharePro.

| Risk factor | DocuSharePro | ExportBot |
|---|---|---|
| Access type | Delegated | Application |
| Mailbox exposure | 112 users | Entire company |
| Ownership | None | Owner left |
| Business necessity | Unknown | Established |
| Suspicious activity | Observed | None reported |

The owner left five weeks ago, and the secret was created in March 2025 and has never been changed. No insider misuse has been reported.

## 6. Supporting evidence

### Current approval controls

Employees can approve any application requesting user consent without IT review or alerts.

Northwind's identity system can:

- Require admin approval.
- Limit user consent to low-risk apps from verified publishers.
- Remove application access for everyone or selected users.
- End user sessions.
- Alert IT Security when applications are approved.

Only admins can approve application permissions.

### Application inventory

| App | Publisher | Permissions | Type | Users | Approved | Last used | Owner |
|---|---|---|---|---:|---|---|---|
| SchedulePro | Verified | Profile; calendar read | Delegated | 64 | Mar 2025 | Today | Sales Ops |
| DocuSharePro | Unverified | All mail read; all files read/write; offline access | Delegated | 112 | Nov 20 | Today (auto) | None |
| MailMerge Plus | Verified | Send as user; contacts read | Delegated | 9 | Jun 2025 | 2 days ago | Marketing |
| HRLink | Verified | Profile (sign-in only) | Delegated | 118 | Jan 2025 | Today | HR |
| PDF Tools Online | Unverified | All files read/write | Delegated | 17 | Mar 2026 | 190 days ago | None |
| SignFast | Verified | Selected files read/write | Delegated | 31 | Aug 2025 | Yesterday | Legal |
| TaskBoard | Verified | Profile; calendar read/write | Delegated | 41 | Oct 2025 | Today | Engineering |
| ExportBot | In-house | All mailboxes read | Application | All mailboxes | Mar 2025 | Today, 03:00 (nightly) | J. Patel (left 5 weeks ago) |

DocuSharePro's publisher registered on Nov 18, 2026.

IT did not approve DocuSharePro or PDF Tools Online. ExportBot builds a nightly clinic-usage report.

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

## Conclusion

Northwind needs to regain control over which applications can access company data without disrupting legitimate business functions.

Remove unnecessary access, investigate suspicious activity, confirm application ownership and require approval based on the permissions requested.

Protect the business without getting in the way of legitimate work.
