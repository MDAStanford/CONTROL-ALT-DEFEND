# 3. Tuesday Anomaly

**Question:** What happened, what does it suggest, and what are the first three actions?

**Answer:** On Tuesday from 03:12–03:16, the NHI read **1,900 patient records in four minutes** (475/minute) from `198.51.100.77`, rather than its usual `192.0.2.40`.

**Reasoning:** The concentrated access and unexpected source IP suggest possible unauthorized access or compromised credentials. This is a **suspected incident, not a confirmed breach**. The weekly total of 38,400 reads falls within the normal 35,000–45,000 range, but does not explain this burst.

| Action | Reasoning |
|---|---|
| **1. Contain** — Block the suspicious IP and assess controlled token revocation or rotation. | IP blocking alone cannot stop reuse of a compromised token from another address. |
| **2. Assess impact** — Identify which patient records and ePHI were accessed. | Establish the sensitivity and potential consequences of exposure. |
| **3. Investigate** — Preserve and review authentication and API logs. | Determine whether activity reflects credential misuse or an authorized process. |
