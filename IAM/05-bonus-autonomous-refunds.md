# Bonus: Autonomous Refunds

**Question:** Should an AI agent ever approve refunds on its own? Where is the line?

**Answer:** Potentially yes, for an agent **explicitly authorized** to process refunds, subject to approved transaction and cumulative thresholds, eligibility rules, logging, and escalation. **Not for this support agent.**

**Reasoning:** This agent's mission is to answer appointment and billing-status questions, create tickets, and draft responses. Refund approval would be **mission creep**. A refund below the existing $500 limit is not automatically appropriate: **authorized business purpose comes before the dollar threshold**. Least privilege and separation of duties require keeping refund authority outside this NHI unless its mission is formally changed and assessed.
