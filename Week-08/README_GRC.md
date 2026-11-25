# GRC: The Policy Nobody Follows

**Assessment objective:** Assess Northwind's Access and Device Security Policy, correct deficient controls and identify audit evidence before the SOC 2 audit window opens.

## D1: Policy findings

**Assignment:** List at least five clauses that wouldn't survive an audit. For each, say what's wrong (vague, outdated, unenforceable, contradicted by the checks, or no owner). Also name one clause that's already fine, and why.

### 1. Passwords

**Original policy:** All staff must use strong passwords and change them every 30 days.

**Findings:**
- Vague definition of strong passwords.
- Outdated, unenforced 30-day expiration requirement.
- 85 of 120 accounts have not changed passwords in six months.

### 2. Access reviews

**Original policy:** Access should be reviewed regularly by management.

**Findings:**
- Undefined review frequency.
- Only two of four quarterly reviews documented.
- Potential conflict of interest in approvals.

### 3. Personal devices

**Original policy:** Staff must not store company data on personal devices.

**Findings:**
- 24 of 60 staff surveyed access work email on personal phones.
- No defined method for verifying compliance.
- Email access alone does not prove local data storage.
- Recommend company-owned or managed personal devices.

### 4. Incidents

**Original policy:** Security incidents must be reported promptly to IT.

**Findings:**
- Reporting deadline undefined.
- Reporting delays of 1, 4 and 9 working days.
- Risk to contractual breach notification obligations.

### 5. Vendors

**Original policy:** Vendors may be given access as needed to do their work.

**Findings:**
- Seven guest accounts without expiration dates.
- Three inactive for over 180 days.

### 6. Exceptions

**Original policy:** Exceptions to this policy may be granted by management.

**Findings:**
- Empty exception register.
- MFA exemption (IT-2201) missing from the register.
- No expiration date.
- Recommend documented approvals and time-limited exceptions.

### 7. Laptops: Satisfactory

**Original policy:** All company laptops must have full-disk encryption turned on. The Head of IT checks the monthly device report and signs it off.

**Findings:**
- 95 of 95 laptops encrypted.
- Three consecutive monthly reports signed by the Head of IT.
- Clear requirements, ownership and supporting evidence.

**Policy governance**
- IT is both owner and approver.
- Last reviewed March 2023.
- Recommend independent approval and annual reviews, plus reviews following significant changes.

## D2: Revised clauses

**Assignment:** Rewrite three clauses so each says who does what, how often, and what record proves it. Keep each to two or three sentences that a clinic receptionist could follow.

**Clause 2: Access reviews**
- System owners must review their team's user access every quarter and list permissions requiring changes or removal.
- An independent manager or Security reviewer must approve the results, and IT must retain signed reviews and change tickets.

**Clause 4: Incidents**
- Staff must report suspected incidents to the IT help desk immediately, and Security must document an initial assessment within four hours of receiving the report.
- Security must maintain timestamped incident tickets, track deadlines and escalate potential delays to management.
- Security and management must notify affected clinics within five business days of discovering a breach involving their data and retain notification records.

**Clause 5: Vendors**
- IT must set vendor account expiration dates no more than 90 days out, with renewal requiring written business owner approval.
- IT must disable accounts after 30 days of inactivity and revoke access immediately upon contract termination.
- IT must retain access requests, approvals and account change logs.

## D3: Audit evidence

**Assignment:** For each rewritten clause, name what an auditor would ask to see.

| Access reviews | Incidents | Vendors |
|---|---|---|
| Quarterly reviews | Timestamped incident tickets | Account inventory |
| Independent approvals | Initial assessments | Access approvals |
| Permission changes | Escalation records | Expiration dates |
| Remediation tickets | Dated client notifications | Renewal records |
| | | Sign-in logs |
| | | Contract termination notices |
| | | Disablement records |

## D4: Leadership note

**Assignment:** What you'd change, what staff will notice, and the one decision you need.

**Recommended changes**
- Defined review schedules.
- Independent approvals.
- Time-limited vendor access.
- Documented policy exceptions.
- Measurable incident reporting requirements.

**Staff impact**
- Quarterly access reviews.
- Stricter vendor access renewals.
- Clearer incident reporting procedures.
- Existing five-business-day notification obligation unchanged.

**Decision required:** Approve the revised Access and Device Security Policy.

## Bonus: Password policy

**Assignment:** One of these clauses shouldn't just be tightened up. The rule itself is wrong. Which one, and why?

**Problem:** Mandatory 30-day password changes encourage predictable password modifications.

**Replacement requirements:**
- Minimum 15 characters.
- Permit passphrases.
- Block common and compromised passwords.
- Eliminate mandatory periodic password changes.
- Require changes upon suspected or confirmed compromise.

---

*Fictional training scenario. Proposed control timeframes are recommendations, not mandatory SOC 2 requirements. The four-hour assessment target assumes adequate Security coverage.*
