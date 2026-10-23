# Northwind Health — AI Governance Risk Assessment

*Fictional case study — proposed controls, not production findings.*

## Assessment register

| Case | Use case | Risk | Proposed disposition | Primary control / condition |
| --- | --- | --- | --- | --- |
| 1 | Public-help-article website chatbot (live) | Low, assuming low-stakes output | Approve, subject to scope validation | Restrict to approved help content; guard against clinical advice and sensitive visitor inputs |
| 2 | Resume screener auto-rejecting bottom 50% (live) | High | Pause automated rejection | Qualified human review **before** rejection; documented job-related criteria; independent bias assessment |
| 3 | AI coding assistant receiving production logs (live) | High where logs contain ePHI | Approve with conditions | Redact/mask patient-related identifiers and sensitive content **before** submission; validate filtering |
| 4 | Clinical visit-note summarizer sending ePHI to vendor API (planned) | High | Conditional approval; do not launch until controls verified | Pre-launch privacy/security review of vendor data handling and retention; enable zero retention or approve a justified alternative; verify BAA and safeguards |
| 5 | AI sales-call recorder/transcriber with no customer notice (live) | High, pending full legal/privacy review | Pause recording until compliant | Determine applicable recording-notice and consent requirements; implement notice/consent and appropriate data-handling controls |


## First investigation priority

**Case 5 — Sales recording.** Undisclosed recording is an active practice with potential consent, privacy, litigation, and business-continuity exposure. Immediately establish the relevant jurisdictions, what notices/consents exist, which calls and data are retained, and whether recording should remain paused pending remediation.

## Universal AI governance rules (under 100 words combined)

1. **Risk assessment:** Every AI system requires a documented pre-deployment risk assessment, periodic reassessment, and additional review after material changes.
2. **Data protection:** Employees may submit confidential information, PII, or ePHI only to AI systems explicitly approved for that data, with verified safeguards.
3. **Human oversight:** AI systems influencing consequential decisions require accountable human reviewers with authority to review, challenge, and override outcomes before they take effect.

## Bonus — HR screener

A vendor's claim that its model is unbiased is **not independent evidence** of fairness. Automated rejection should not resume without qualified human review of adverse outcomes, documented job-related criteria, and credible bias testing.
