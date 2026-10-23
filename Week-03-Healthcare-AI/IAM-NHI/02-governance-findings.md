# IAM Assessment — Part 2: NHI Governance Findings

## Scope

Identity governance review of the AI support agent's **non-human identity (NHI)** at a fictional healthcare SaaS provider. This section assesses **how the identity and its credentials are managed**, separately from the nine-permission review in Part 1.

## Findings

### 1. Shared token across production and staging
**Severity: HIGH**

**Observation:** The same API token is used in both production and staging.

**Risk:** Reusing credentials across environments weakens environment isolation. If the shared token is exposed in staging, it may also enable access to production.

**Recommendation:** Use distinct credentials for production and staging and manage them independently.

### 2. No assigned NHI owner
**Severity: HIGH**

**Observation:** The identity's owner field is blank.

**Risk:** No person or team is formally accountable for oversight, credential maintenance, access reviews, or lifecycle decisions.

**Recommendation:** Assign a responsible owner and document accountability for ongoing identity governance.

### 3. Inadequate identity lifecycle recordkeeping
**Severity: HIGH**

**Observation:** The identity was created 14 months ago by a contractor who has since left the organization.

**Risk:** Without maintained lifecycle records and ownership handoff, governance continuity and accountability may be lost when the original creator departs.

**Recommendation:** Establish an NHI lifecycle protocol that retains creation records, purpose, responsible owner, ownership transitions, and review history. The contractor's departure is a **governance and recordkeeping issue**; it does **not**, by itself, justify disabling the identity.

### 4. Token has no expiration or defined credential lifecycle
**Severity: HIGH**

**Observation:** The API token has no expiration date.

**Risk:** A non-expiring credential can remain usable indefinitely, including after potential exposure, unless explicitly revoked.

**Recommendation:** Enforce token expiration and establish credential lifecycle management covering issuance, renewal, rotation, revocation, and associated records.

## Summary

| Finding | Severity |
|---|---|
| Shared token across production and staging | HIGH |
| Unassigned NHI owner | HIGH |
| Inadequate identity lifecycle recordkeeping | HIGH |
| Missing token expiration and credential lifecycle | HIGH |

These findings address **NHI governance**, not the appropriateness of individual application permissions. They reflect the documented observations and conclusions from the fictional challenge scenario.

*Training case study; not an assessment of a live environment. Scenario adapted and paraphrased from a cybersecurity learning challenge.*
