# Control + Alt + Defend — SSO Go-Live

## Scenario
Pre-launch SAML SSO testing uncovered three issues in a billing application: failed sign-ins, unmatched user accounts, and excessive privileges.

## DELIVERABLE 1 — Root Cause Analysis
- **Invalid audience:** Entra and Billing use different SAML audience identifiers due to a trailing slash.
- **Identity mismatch:** Seven employees have UPNs that differ from their email addresses. Billing expects email identifiers.
- **Excessive access:** Billing grants Admin access to any group containing "Billing," including `Billing-Readers`.

## DELIVERABLE 2 — Remediation & Validation
1. **Audience:** Align identifiers, remove the temporary workaround, and retest SSO.
2. **Authorization:** Correct group-to-role mappings and contain excessive Admin access.
3. **Identity matching:** Configure Entra to send the expected email attribute.

Validate each correction against affected users and the broader Billing population. Compare approved permissions against actual access.

## DELIVERABLE 3 — Authentication vs. Authorization
- **Authentication:** Sam successfully authenticates through Entra, but Billing cannot match his identifier to an account.
- **Authorization:** Lena authenticates successfully but incorrectly receives Admin privileges.

## DELIVERABLE 4 — Security Assessment
- Suspend the faulty Admin mapping to contain unauthorized access.
- Audit Billing users for excessive privileges.
- Do not retain relaxed audience validation or broad group-matching rules.

## DELIVERABLE 5 — Go-Live Decision
**NO-GO until remediation and validation are complete.**

Approve launch only after testing confirms correct identity matching, least-privilege access, and successful SSO across the intended user population.

## BONUS — Trailing Slash
SAML audience identifiers must match the application's configured expected value. A trailing slash changes the identifier and can cause the application to reject the assertion.

*Fictional training scenario; not a production assessment.*
