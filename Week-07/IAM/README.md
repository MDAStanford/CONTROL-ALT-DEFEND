# Week 7 — IAM: Sign-in Risk and Authentication

**Goal:** Reduce risky access without interrupting patient care.

## 1. Five highest-risk sign-ins

| Rank | Event | Risk | Reason |
|---|---|---|---|
| 1 | #1 — breakglass-02 | Critical | Emergency admin access at 02:47, unmanaged device, no MFA; potentially organization-wide impact. Verify authorized use. |
| 2 | #5 — j.chen | High | Successful legacy IMAP sign-in from Romania without MFA. |
| 3 | #6 — j.chen | High | Second successful IMAP sign-in from the same Romanian IP; investigate with #5 as one possible incident. |
| 4 | #12 — t.nguyen-admin | High | Admin console accessed from personal unmanaged laptop using SMS MFA. |
| 5 | #15 — s.park | High | Patient portal accessed from Singapore using an existing session without fresh MFA; verify travel and session use. |

## 2. Six authentication policies

| # | Control | Decision |
|---|---|---|
| 1 | Device compliance | Require compliant devices for sensitive systems; block unmanaged or noncompliant access. |
| 2 | Named locations | Define HQ and clinics; apply stronger checks outside approved locations. Location alone never exempts MFA. |
| 3 | Session frequency | Reduce clinical sign-in frequency from 90 days to 8 hours; lock unattended devices after 5 minutes. |
| 4 | Phishing-resistant MFA | Use FIDO2 security keys or Windows Hello for Business for privileged access; avoid SMS. |
| 5 | Legacy authentication | Block legacy methods that cannot enforce modern MFA, after checking dependencies. |
| 6 | Partner access | Require MFA and least privilege for guests and partners, including connections over partner VPNs. |

**Emergency access:** Keep dedicated break-glass accounts available, secured, alerted on every use, and reviewed afterward.

## 3. Shared tablets

- **Windows:** Individual Entra accounts; Windows Hello for Business PINs on supported managed tablets; switch users between sessions.
- **iPad:** Shared iPad with Apple Business Manager/MDM, separate Managed Apple Accounts and sessions, where supported.
- **Both:** Five-minute inactivity lock, individual application audit trails, and no shared credentials.

**Trade-off:** Windows is simpler for Entra integration; iPad requires additional Apple management and app compatibility checks. Test handoff speed before rollout.

## 4. Rollout

1. **Inventory:** Identify affected users, devices, applications, and legacy authentication dependencies.
2. **Pilot:** Test policies with IT, Finance, and a small clinical group.
3. **Validate:** Confirm clinicians can access patient records, shared tablets work, and emergency accounts remain available.
4. **Deploy:** Roll out policies in stages, prioritizing privileged access and high-risk authentication.
5. **Monitor:** Review sign-in failures, blocked access, help-desk tickets, and clinical disruptions. Adjust where necessary.

Enable controls in stages, not all at once, to protect patient care.
