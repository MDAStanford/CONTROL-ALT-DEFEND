# Bonus Assessment — Autonomous Refund Authority and Mission Creep

## Position

**Could an AI agent ever approve refunds autonomously?** Potentially yes, where refund processing is expressly included in the agent's approved business purpose and bounded by an organizationally approved transaction threshold, eligibility rules, audit logging, cumulative limits, and escalation controls.

**Should this support agent approve refunds?** **No.** Its stated mission is to answer clinic staff questions about appointment and billing status, create support tickets, and draft responses for human approval. **Processing or approving refunds is outside that mission.** Granting refund authority would constitute **mission creep**, even when individual refunds fall below the existing $500 limit.

## Where to draw the line

The first boundary is **authorized business purpose**, not the dollar amount. A transaction being technically permitted or below a configured limit does not establish that the NHI should perform it.

- **Least privilege:** Do not grant refund authority to an NHI whose duties do not require it.
- **Separation of duties:** Keep financial approval and execution with appropriately authorized personnel or a separately approved workflow.
- **Scope control:** Any proposal to expand the agent's mission into refund processing requires a formal business decision, risk assessment, updated permissions, and enforced authorization controls.
- **Thresholds are secondary:** Only after refund authority has been explicitly approved should the organization establish and enforce appropriate per-transaction and cumulative limits, logging, and escalation requirements.

## Conclusion

**Autonomous refunds may be appropriate for a purpose-built, explicitly authorized AI agent with bounded authority. They are not appropriate for this support agent under its current mission.** The existing $500 threshold does not resolve the underlying governance problem.

*Fictional training case study; not an assessment of a live environment. Scenario adapted and paraphrased from a cybersecurity learning challenge.*
