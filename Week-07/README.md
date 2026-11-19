# Week 7 — IAM: Sign-in Risk Review

## Deliverable 1 — Five Highest-Risk Sign-ins (In Progress)

Review the 15 sign-in events, identify the five highest-risk events, and explain why. Rankings below are provisional; the fifth candidate remains open.

| Priority | Event | Risk | Reason |
|---|---|---|---|
| 1 | #1 — breakglass-02 | Critical | Emergency administrator signed in at 02:47 from an unmanaged device without MFA. A compromise could affect the entire identity environment. Verify authorized emergency use and review administrative actions. |
| TBD | #5 and #6 — j.chen | High | Two successful finance-mail IMAP sign-ins from the same Romanian IP, two minutes apart. Legacy authentication could not perform MFA. Treat as one potential incident. |
| TBD | #12 — t.nguyen-admin | High | Successful privileged admin-console access from a personal unmanaged laptop using SMS MFA. |
| TBD | #15 — s.park | High | Successful patient-portal access from Singapore using an existing session, with no fresh MFA challenge. Verify authorized travel or remote access. |
| TBD | Fifth candidate | Pending | Select after reviewing the remaining events. |

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

## Follow-up for Later Deliverables

- Replace the current 90-day sign-in frequency; provisional clinical-staff target: **8 hours**, with a separate **5-minute device inactivity lock**.
- Review trusted-location MFA exemptions and privileged authentication.
- Resolve shared-tablet authentication without relying on shared identities or blanket MFA exemptions.
- Keep event risk assessment separate from policy design and rollout planning.
