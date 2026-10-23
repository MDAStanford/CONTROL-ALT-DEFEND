# 4. Target-State Controls

**Question:** Which five controls should govern the AI agent's NHI, including actions that change data or move money?

| Control | Answer and reasoning |
|---|---|
| **1. Ownership and lifecycle** | Assign business and technical owners; record purpose, ownership transfers, and periodic reviews to maintain accountability. |
| **2. Credential management** | Separate staging and production tokens; enforce expiration, rotation, secure storage, and revocation to limit credential exposure. |
| **3. Least privilege** | Limit patient and billing access to information needed for status inquiries; remove unrelated write and payment permissions. |
| **4. Human approval** | Require authorized human approval before changing patient data, issuing refunds, or sending external messages. Enforce approval in the application workflow and log execution; the NHI must not bypass it. |
| **5. Monitoring** | Log authentication and API activity; alert on unusual access volume, source IPs, and token usage to support timely investigation. |
