# Week 7 — IAM: Sign-in Risk Review

## Deliverable 1 — Five Highest-Risk Sign-ins

Review the 15 sign-in events, identify the five highest-risk events, and explain why. Events #5 and #6 are two sign-ins that may be part of one incident.

| Priority | Event | Risk | Reason |
|---|---|---|---|
| 1 | #1 — breakglass-02 | Critical | Emergency administrator signed in at 02:47 from an unmanaged device without MFA. A compromise could affect the entire identity environment. Verify authorized emergency use and review administrative actions. |
| 2 | #5 — j.chen | High | Successful legacy IMAP mail access from Romania without MFA capability. Investigate alongside #6. |
| 3 | #6 — j.chen | High | Second successful legacy IMAP sign-in from the same Romanian IP two minutes later; likely related to #5. |
| 4 | #12 — t.nguyen-admin | High | Successful privileged admin-console access from a personal unmanaged laptop using SMS MFA. |
| 5 | #15 — s.park | High | Successful patient-portal access from Singapore using an existing session, with no fresh MFA challenge. Verify authorized travel or remote access. |

## Other Events Reviewed

| Event | Preliminary risk | Observation |
|---|---|---|
| #2 — k.malik | Low | HQ, managed compliant device; trusted-location MFA exemption is a policy weakness. |
| #3 — dr.okafor | Low | Normal-hours patient-portal access; MFA passed, but device is personal and unmanaged. |
| #4 — svc-reports | Low | Internal non-interactive service-account API access; no obvious anomaly. |
| #7 — v.santos | Medium | External partner used an unmanaged device and trusted-VPN MFA exemption. |
| #8 — m.reyes | Medium | Executive sign-in from Portugal; managed device and MFA passed; verify travel. |
| #10 — fd-clinic12 | Low | MFA timed out and access failed on a managed shared tablet; operational problem. |
| #11 — fd-clinic12 | Medium | Shared account successfully accessed patient portal through IT-ticket MFA exemption; accountability gap. |
| H. Lee — Toronto | Medium | Verify clinic footprint, work location, and authorization; event number pending. |

## Deliverable 2 — Authentication Policies

Six proposed controls to reduce sign-in risk while keeping clinical operations running.

| # | Policy | Decision |
|---|---|---|
| 1 | Device compliance | Require managed, compliant devices for sensitive applications and privileged access. Block unmanaged, noncompliant, or unknown-status devices until verified. |
| 2 | Named locations | Define HQ and approved clinics. Apply stricter MFA, device, and risk checks outside those locations. Location alone never grants an MFA exemption; block high-risk sign-ins. |
| 3 | Sign-in frequency | Reduce clinical-staff sign-in frequency from 90 days to 8 hours. Separately lock unattended devices after 5 minutes; require fresh authentication or block when risk warrants. |
| 4 | Phishing-resistant MFA | Require phishing-resistant authentication for privileged accounts: FIDO2 security keys for appropriate workstations and Windows Hello for Business on individually assigned managed Windows devices. Do not rely on SMS for administrators. |
| 5 | Legacy authentication | Block legacy authentication methods that cannot enforce modern MFA, including the IMAP access seen in events #5 and #6. Check dependencies before enforcement. |
| 6 | External partner access | Require MFA for guest and partner access regardless of partner VPN or trusted network. Apply least privilege and device/risk checks to sensitive resources. |

**Emergency-access exception:** Maintain dedicated break-glass accounts with secure credentials, tightly controlled use, immediate alerts, and review of every sign-in. Test emergency access before enforcing broad policies.

**Operational safeguard:** Test policies in report-only/pilot stages and validate clinical workflows before organization-wide enforcement.

## Follow-up for Later Deliverables

- Replace the current 90-day sign-in frequency; provisional clinical-staff target: **8 hours**, with a separate **5-minute device inactivity lock**.
- Review trusted-location MFA exemptions and privileged authentication.
- Resolve shared-tablet authentication without relying on shared identities or blanket MFA exemptions.
- Keep event risk assessment separate from policy design and rollout planning.
