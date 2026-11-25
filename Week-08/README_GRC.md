# GRC — The Policy Nobody Follows

## Overview

Northwind's SOC 2 audit window opens in approximately five months. Management requested an assessment of its Access and Device Security Policy to identify deficiencies, rewrite three clauses and establish appropriate audit evidence.

Scenario date: November 23, 2026. Policy version: 2.1. Last reviewed: March 2023. Owner and approver: IT. Northwind must notify affected clinics within five business days of discovering a breach involving their data.

## D1 — Find the problems

**Question:** Identify at least five deficient clauses, explain what is wrong with each and identify one satisfactory clause.

| Clause | Finding | Recommendation |
|---|---|---|
| 1. Passwords | Vague password requirements, outdated expiration rule and lack of enforcement. | Establish minimum password length and require changes when compromise is suspected or confirmed. |
| 2. Access reviews | Undefined frequency, inconsistent completion and potential approval conflicts. | Quarterly reviews with independent approval. |
| 3. Personal devices | Policy does not clearly address personal device access or how compliance is verified. | Issue company-owned devices or require managed personal devices. |
| 4. Incidents | Subjective reporting requirement and documented reporting delays. | Establish measurable reporting and assessment deadlines, with documented escalation. |
| 5. Vendors | No access expiration dates or inactivity controls. | Maximum 90-day access lifecycle; disable accounts after 30 days of inactivity. |
| 6. Exceptions | Undocumented MFA exception with no expiration date. | Maintain an exception register with documented approval and time limits. |
| 7. Laptops | **Satisfactory.** Clear requirement, defined accountability, monthly reviews and documented compliance. | Retain existing control. |

**Additional policy governance findings:**

| Finding | Recommendation |
|---|---|
| IT is both policy owner and approver. | Establish independent policy approval. |
| Policy has not been reviewed in approximately 44 months. | Establish annual policy reviews and additional reviews following significant changes. |

The personal device findings warrant further verification: accessing work email does not necessarily prove that company data is stored locally.

## D2 — Rewrite three clauses

**Question:** Rewrite three clauses so each says who does what, how often and what record proves it, in two or three sentences.

### Clause 2 — Access reviews

System owners must review their team's user access every quarter and list any permissions that need to be changed or removed. An independent manager or Security reviewer must approve the results, and IT must keep the signed review form and change tickets on file.

### Clause 4 — Incidents

All staff must report suspected security incidents to the IT help desk immediately, and Security must log an initial assessment within four hours. Security must keep timestamped incident tickets, track breach deadlines, and escalate any potential delays to management. Security and management must notify affected clinics within five business days of discovering a breach involving their data and save copies of those notices.

### Clause 5 — Vendors

IT must set an expiration date of no more than 90 days on all vendor accounts, and renewal requires written approval from the business owner. IT must disable vendor accounts after 30 days of inactivity and remove access immediately when a vendor's contract ends. IT must keep all access requests, owner approvals, and account change logs on file.

## D3 — Evidence test

**Question:** For each rewritten clause, name what an auditor would ask to see.

| Clause | Audit evidence |
|---|---|
| 2. Access reviews | Quarterly access review records, independent approvals, permission changes, and remediation tickets. |
| 4. Incidents | Timestamped incident tickets, initial assessments, escalation records, and dated client notifications. |
| 5. Vendors | Vendor account inventory, access approvals, expiration dates, reauthorization records, sign-in logs, vendor contract termination notices, and account disablement records. |

## D4 — Leadership note

**Question:** In 120 words maximum, explain what you'd change, what staff will notice, and the one decision you need.

Our review identified outdated policy requirements, inconsistent access reviews, delayed incident reporting, and inadequate vendor access controls.

We recommend establishing defined review schedules, independent approvals, time-limited vendor access, documented policy exceptions, and measurable incident reporting requirements.

Staff will notice quarterly access reviews, stricter vendor access renewal requirements, and clearer incident reporting procedures. The existing five-business-day client notification obligation remains unchanged.

**Decision required:** Leadership approval of the revised Access and Device Security Policy.

## Bonus — Challenge the rule

**Question:** Which clause should not simply be tightened because the rule itself is wrong, and why?

Clause 1 — Passwords.

Mandatory 30-day password changes are outdated and encourage predictable password modifications.

Replace the existing requirement with:

- Minimum password length of 15 characters.
- Passphrases permitted.
- Common and compromised passwords blocked.
- No mandatory periodic password changes.
- Password changes required when compromise is suspected or confirmed.

This approach aligns with modern NIST password guidance.

---

*Fictional training scenario. Proposed control timeframes are recommendations, not mandatory SOC 2 requirements. The four-hour assessment target assumes adequate Security coverage.*
