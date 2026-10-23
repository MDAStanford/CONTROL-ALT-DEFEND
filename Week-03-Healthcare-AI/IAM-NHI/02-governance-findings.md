# 2. NHI Governance Findings

**Question:** What identity-management problems exist, separate from permissions?

| Finding | Severity | Reasoning |
|---|---|---|
| Same API token in staging and production | **High** | Credential exposure in one environment could affect the other. Use separate tokens. |
| No assigned NHI owner | **High** | No clear accountability for reviews, credential maintenance, or oversight. Assign an owner. |
| Created 14 months ago by a departed contractor | **High** | Lifecycle records and ownership handoffs must be maintained when personnel leave. The departure alone does not justify disabling the NHI. |
| Token has no expiration | **High** | An exposed token may remain usable indefinitely. Enforce expiration and a credential lifecycle covering issuance, rotation, and revocation. |
