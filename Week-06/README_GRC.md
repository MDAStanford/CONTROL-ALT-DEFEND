# Week 6 — Vendor Risk Review

**Scenario:** Northwind Healthcare is considering ClinicConnect Video for about 60,000 patient visits a month. Launch is four weeks away.

*Fictional case study based on provided documents, not a real vendor audit.*

## Risk and decision

**Risk: Critical.** ClinicConnect would handle sensitive patient information. A long outage could delay patient care. The actual impact would depend on how clinics use the service.

**Decision: Do not approve for launch.** ClinicConnect has not shown it can meet Northwind's recovery, incident-reporting, and access-security requirements. Look for another provider. Delay launch if no provider passes the review.

## Main findings

| Issue | What we found | What we need |
|---|---|---|
| System recovery | ClinicConnect allows **24 hours** to recover; Northwind needs **4 hours**. | Proof it can recover within four hours, or a tested backup plan. |
| Security incident reporting | ClinicConnect allows **30 days after confirming an incident** to report it. Northwind must notify clinics within **5 business days of discovering it**. | Contract terms that give Northwind enough time to meet its commitment. |
| Access reviews | The SOC 2 report flagged **two missed quarterly access reviews**. | A completed access review, proof of fixes, and a plan to keep reviews on schedule. |
| Multi-factor authentication (MFA) | The questionnaire says MFA is required, but **three support engineers did not have it** in Q2. | Sign-in records and proof those accounts are now protected. |
| Video system security | The video relay system was **not covered** by the SOC 2 review, which covered Security controls only. | Security testing, an explanation of how patient data moves, and independent evidence covering the missing system. |
| Overseas support access | Contractors outside the US can remotely access production support tools. | Details of what they can see or change, plus access restrictions, activity logs, and protection of patient data. |
| Contracts and subcontractors | ClinicConnect offers a standard, nonnegotiable Business Associate Agreement (BAA) and uses several other providers. | Legal approval of the BAA, clear subcontractor responsibilities, and proof of where patient data is stored. |

## Claims that need checking

- **MFA:** ClinicConnect says everyone has MFA, but its security report found exceptions. Confirm those accounts were fixed.
- **US data storage:** Overseas access does not prove data is stored outside the US. Check where data is stored and whether overseas staff can view patient information.

## Response to Head of Product

> ClinicConnect does not meet several of our requirements. Its recovery time is too long, it may not notify us quickly enough about security incidents, and there are unresolved concerns about who can access patient information.
>
> I recommend we do not approve ClinicConnect for launch. Product and Procurement should immediately look for another video provider. Legal and Security should review the new provider's contracts, recovery plans, and security controls.
>
> We can continue testing with fake patient data, but we should not allow real patient visits until a provider passes our security review.
>
> If we cannot find a qualified provider within four weeks, we should delay the launch rather than put patient information and care at risk.

**How I assessed it:** I compared the vendor questionnaire, subcontractor list, and SOC 2 report excerpts. I identified gaps and conflicting claims, but did not test the vendor's systems.
