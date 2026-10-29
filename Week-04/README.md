# Control + Alt + Defend — Week 4

## IAM Case Study: The MFA Reset Social Engineering Attempt

## DELIVERABLE 1 — Red Flags

- **Refusal of an independent callback:** Resistance to a trusted-channel callback undermines confidence.
- **Weak identity evidence:** Knowing personal or employee details does not establish account ownership.
- **Sensitive recovery request:** Reassigning MFA could give an attacker control of a high-value account.
- **Location and contact inconsistency:** A UK phone number paired with an Austin, TX claim warrants scrutiny, though it is not proof of fraud.
- **Manufactured urgency and authority:** References to the CEO, board, or an immediate deadline are pressure tactics, not authorization.

**Decision:** Treat the caller's identity as unverified. Do not reset MFA based on urgency, rank, or information supplied during the call.

## DELIVERABLE 2 — Immediate Response

- **Stay professional:** Follow the established recovery procedure.
- **Document:** Open a ticket and record relevant details.
- **Verify independently:** Use trusted internal contact information, not caller-provided details.
- **Escalate:** Notify security if the call appears suspicious.
- **Protect access:** No MFA reset or temporary credentials before verification and approval.

## DELIVERABLE 3 — Identity Verification

- **Plan for lost access:** The phone may contain all registered authenticators.
- **Use a backup:** Verify with a previously enrolled security key or other independent authenticator, if available.
- **Use approved recovery:** If no backup exists, follow a high-assurance identity verification process.
- **Reject weak proof:** Personal details and caller-provided contact information are insufficient.
- **Fail closed:** If identity cannot be verified, deny recovery and escalate. Verification permits review, not automatic approval.

## DELIVERABLE 4 — Privileged / High-Risk MFA Recovery

The design is **vendor-agnostic**. It uses Zero Trust, least privilege, separation of duties, and defense in depth. High-risk accounts warrant stronger safeguards; executive status alone does not necessarily mean administrative privilege.

| Step | Action | Required outcome |
|---|---|---|
| **1. Triage** | Open a ticket; classify account sensitivity, circumstances, and security indicators. Begin lost-device containment when warranted. | A documented risk-based route. |
| **2. Verify Identity** | Use an independent authenticator or approved high-assurance recovery method. | Verified identity, or a fail-closed stop. |
| **3. Authorize** | Have a separate authorized IAM/security approver review the evidence, risk, and justification. | Explicit approval or denial; no self-approval. |
| **4. Execute Recovery** | Use a restricted, approved recovery workflow; issue short-lived, tightly scoped recovery access only if needed; securely enroll a replacement authenticator. | Access restored without a standing MFA bypass. |
| **5. Post-Mortem** | Validate the new authenticator, revoke temporary access and obsolete authentication methods, review sessions and sign-ins, confirm containment status, preserve audit evidence, and identify improvements. | Recovery and remaining exposure documented and addressed. |

**Technical enforcement:** An approval requirement should be enforced by workflow and privilege design, not merely by asking staff to obtain a second signature. Alternative administrative and API paths must be controlled and monitored to reduce bypass risk.

**Lost-device containment:** Revoke sessions and authenticators immediately. Wipe corporate devices; selectively remove company data from personal devices, per policy. Confirm wipe status.

## DELIVERABLE 5 — Post-Call Incident Response

- **Document the attempt:** Preserve an audit trail for future investigations.
- **Identify patterns:** Repeated calls may indicate a coordinated vishing attack.
- **Escalate and monitor:** Notify security, review sign-ins and recovery activity, and alert the help desk.
- **Maintain business continuity:** Restrict recovery actions without unnecessarily locking Dana's account.
- **Check financial activity:** Have Finance review corporate cards, payments, and vendor banking changes for anomalies.
- **Contain if needed:** Escalate protections if evidence of compromise emerges.
