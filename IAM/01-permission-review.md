# 1. Permission Review

**Question:** Which permissions does the AI support agent's NHI need?

| # | Permission | Answer | Reasoning |
|---|---|---|---|
| 1 | Read help-center articles | **Needed** | Supports staff questions; limit access to relevant articles. |
| 2 | Read all patient records (full ePHI) | **Not needed** | Full records exceed the task; apply least privilege and data minimization. |
| 3 | Read billing summaries | **Needed** | Open, paid, or pending status supports billing inquiries. |
| 4 | Read full billing and payment data | **Not needed** | Reporting status does not require complete payment information. |
| 5 | Update patient contact details | **Not needed** | Changing patient information is outside the agent's mission. |
| 6 | Issue refunds up to $500 without approval | **Not needed** | Refund processing is outside its mission; separation of duties applies. |
| 7 | Send email as support@ | **Not needed** | The agent drafts responses for human approval, not independent sending. |
| 8 | Create and update support tickets | **Needed with conditions** | Creation is authorized; updates must be narrowly scoped and auditable. |
| 9 | Delete ticket history | **Not needed** | Deletion is outside its mission and undermines auditability. |
