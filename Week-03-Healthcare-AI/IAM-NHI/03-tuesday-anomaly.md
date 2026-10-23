# IAM Assessment — Part 3: Tuesday Access Anomaly (In Progress)

## Observed activity

On Tuesday, from **03:12 to 03:16**, the AI support agent's non-human identity (NHI) was associated with **1,900 patient-record reads in four minutes**, approximately **475 records per minute**.

- **Observed source IP:** `198.51.100.77`
- **Normal source IP:** `192.0.2.40`
- **Seven-day total:** 38,400 patient-record reads
- **Normal weekly range:** 35,000–45,000 patient-record reads

The seven-day aggregate falls within the stated normal range; that does not establish that this particular four-minute burst was expected or authorized.

## Preliminary interpretation

The learner identified two concerning indicators:

1. **Concentrated access volume:** 1,900 records were read in a four-minute interval.
2. **Unexpected source IP:** The requests originated from an IP different from the agent's normal source.

Together, these observations raise concern about **possible unauthorized access or compromised NHI credentials**, including possible bulk access to patient information. This is a **suspected security incident / potential breach**, not a confirmed breach. The excerpt alone does not establish who initiated the activity or whether there was an authorized explanation.

## First three response actions

**Pending learner assessment.** No response actions have been selected or finalized yet.

## Status

**In progress:** The event description and preliminary interpretation are documented. The required first three actions remain open.

*Fictional training case study, not a live security incident. Scenario adapted and paraphrased from a cybersecurity learning challenge.*
