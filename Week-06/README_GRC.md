# Week 6 — Third-Party Risk Assessment

**Scenario:** Northwind Healthcare is evaluating ClinicConnect Video for approximately 60,000 patient visits per month, with a proposed launch in four weeks. *Fictional portfolio exercise; findings are based on supplied scenario evidence, not an actual vendor audit.*

## Risk assessment

**Tier: Critical.** The service handles sensitive patient information at scale, and an extended outage could interrupt time-sensitive care. Criticality reflects potential impact; the clinical consequences would need confirmation against actual use cases.

**Decision: Reject on current evidence.** ClinicConnect cannot demonstrate alignment with Northwind's recovery and breach-notification commitments. Product and Procurement should assess equivalent vendors; delay launch if none passes due diligence.

## Findings and evidence required

| Finding | Risk / gap | Required evidence or action |
|---|---|---|
| Recovery | Vendor RTO **24 hours** vs Northwind **4 hours** | Tested four-hour recovery or validated continuity alternative |
| Incident notification | Vendor: **30 days after confirmation**; Northwind: **5 business days after discovery** | Legal-approved terms enabling Northwind to meet its deadline |
| Access governance | Qualified SOC 2 opinion: two missed quarterly reviews | Comprehensive current access review, remediation records, and recurring review controls |
| MFA | Three support engineers lacked MFA in Q2 despite questionnaire claim | Policy coverage, authentication logs, and targeted retesting of affected accounts |
| Video infrastructure | Media relay excluded from SOC 2 scope; report covers Security only | Relevant independent assurance, architecture/data-flow documentation, and security testing |
| Offshore support | Contractors remotely access production support tooling | Privilege inventory, ePHI access assessment, least-privilege restrictions, PIM, masking, and logs |
| BAA and subcontractors | Standard nonnegotiable BAA; multiple subprocessors | Legal review, signed acceptable BAA, subcontractor obligations, and US-storage evidence |

## Questionnaire cross-check

1. **MFA:** The claim of universal production MFA is undermined by the SOC 2 support-tool exception; determine whether the issue is remediated.
2. **US hosting:** US-region storage is **not disproved** by offshore support access, but remote access may expose patient data and requires verification of privileges, transfers, and safeguards.

## Response to Head of Product

> ClinicConnect does not meet several of our requirements. Its recovery time is too long, it may not notify us quickly enough about security incidents, and there are unresolved concerns about who can access patient information.
>
> I recommend we do not approve ClinicConnect for launch. Product and Procurement should immediately look for another video provider. Legal and Security should review the new provider's contracts, recovery plans, and security controls.
>
> We can continue testing with fake patient data, but we should not allow real patient visits until a provider passes our security review.
>
> If we cannot find a qualified provider within four weeks, we should delay the launch rather than put patient information and care at risk.

**Assessment method:** Reviewed the supplied vendor questionnaire, subprocessor list, and SOC 2 Type II excerpts; identified discrepancies and evidence gaps. No live control tests or independent validation were performed.
