# IAM Assessment — Part 4: Target-State NHI Controls

## Objective

Design five controls for an AI support agent's **non-human identity (NHI)** at a fictional healthcare SaaS provider, addressing identity governance, credential security, authorized access, approval of consequential actions, and anomaly detection.

## 1. NHI ownership and lifecycle governance

Assign a designated **business owner** and **technical owner**. Maintain identity creation records, documented business purpose, ownership transitions when personnel leave, and periodic reviews of continued access and business justification.

**Addresses:** Orphaned identities, missing accountability, and weak lifecycle recordkeeping.

## 2. Credential lifecycle and environment isolation

Use **distinct credentials for staging and production**. Enforce token expiration, scheduled rotation, secure credential storage, and prompt revocation when credentials are suspected to be compromised. Record credential lifecycle events.

**Addresses:** Shared credentials across environments and indefinite token validity.

## 3. Least privilege and data minimization

Grant only the access necessary to answer appointment and billing-status questions, create authorized support tickets, and draft responses. Restrict full patient-record and payment-detail access, and remove independent write or transaction authority not required by the agent's defined role.

**Addresses:** Excessive access to electronic protected health information (ePHI), sensitive financial data, and unauthorized operations.

## 4. Human-in-the-loop authorization for consequential actions

Require **authorized human approval** before changing patient information, issuing refunds, or sending external communications. Enforce the approval gate in the **application workflow and authorization controls**, rather than relying solely on the AI agent's instructions.

**Workflow:**
1. AI agent reads only authorized information and prepares a proposed action.
2. Authorized human reviews and approves or rejects the proposal.
3. Controlled application workflow validates the approval, executes the permitted action, and records an audit trail.

The NHI must not have a direct path to bypass approval. A refund below an existing dollar threshold still requires the appropriate authorization under this target-state design.

**Addresses:** Unauthorized changes to data, financial transactions, and unapproved external communications.

## 5. Continuous monitoring and anomaly detection

Log NHI authentication events and API activity. Alert on unusual record-access velocity, unexpected source IPs, unauthorized operations, and anomalous token use. Maintain procedures for investigation, containment, and evidence preservation.

**Addresses:** Delayed identification and response to suspicious or compromised NHI activity.

## Target-state summary

| Control | Primary security principle |
|---|---|
| Ownership and lifecycle governance | Accountability and lifecycle management |
| Credential lifecycle and environment isolation | Credential hygiene and isolation |
| Least privilege and data minimization | Access minimization |
| Human-in-the-loop authorization | Separation of duties and controlled execution |
| Continuous monitoring and anomaly detection | Detection and response |

**Status: Finalized.** These five controls form the proposed target state for the fictional training scenario. The bonus question about whether an AI agent should *ever* autonomously approve refunds is a separate consideration.

*Training case study; not a live environment assessment. Scenario adapted and paraphrased from a cybersecurity learning challenge.*
