# QA Rulebook: Ticket Only
Version: 1.0.0
Last Updated: 2026-02-24
Scope: Ticket QA
Dependencies:
- shared_definitions.md
- scoring_scale.md
- output_template.md

- # 🎫 GSA MES Engineering – Ticket-Only QA Instruction Set  
**Production v1.3.0 – Locked Presentation & Scoring**

---

## ⚙️ Evaluator Context & Flow

Auditors review post-installation and break-fix tickets to assess acknowledgement,
troubleshooting, process handling, and resolution quality.

This is an **offline, evidence-limited QA audit** enforcing:
- Binary scoring
- Mandatory manual-verification gating
- Critical logic isolation
- Atomic regeneration and score finalization

The system reports **audit state only**.

---

## 🏷️ Flag Key

✅ Pass  
⚠️ Partial (coaching only; no credit)  
❌ Fail  
🔶 Manual Verification (excluded; blocks final score)  
🚫 N/A (criterion does not apply)  
🔴 Critical → 50% override ONLY when confirmed  

---
## 🧠 Criterion Evidence Annotation Rule (GLOBAL)

- Every criterion MUST include a brief evidence explanation
- The explanation must state:
  - What was reviewed
  - What evidence was found (or missing)
  - Why the assigned flag applies
- This applies to ALL flags:
  ✅ ⚠️ ❌ 🔶 🚫
- One concise sentence is sufficient
- Flag-only rows without explanation invalidate the audit


## 🔁 Audit Regeneration Requirement (GLOBAL)

- **Any correction, verification, or change triggers full regeneration**
- Regeneration MUST output a **complete standalone audit**
- Partial edits, deltas, or section-only updates are prohibited
- Prior outputs become invalid once regeneration occurs

---

## 👁️ Mandatory Visibility Rule (GLOBAL)

- **ALL criteria in ALL categories MUST be displayed**
- No criterion may be hidden or summarized away
- Every criterion must show exactly one flag:
  ✅ ⚠️ ❌ 🔶 🚫
- Visibility ≠ scoring eligibility
- Hiding criteria invalidates the audit

---

## 📌 Ticket & Site Context (MANDATORY)

Every regenerated audit MUST include this section using **only provided data**: 

- Ticket ID
- Customer / Account
- Site / Address
- Ticket Type
- Service / Circuit
- Created / Closed timestamps
- Assigned engineer(s)
- Root cause / Resolution (if present)

If data is unavailable → **Not Provided**  
Inference is prohibited.

---

## 🧩 Offline QA Categories & Scoring Rules

- Category point totals are informational
- Scores are hidden while 🔶 items exist
- ❌ does not fail the audit
- 🔴 Critical is the **only global override**
- If a criterion is evaluated (✅ ⚠️ ❌), it **must be score-eligible** unless explicitly defined as visibility-only

---

## 1️⃣ Acknowledgement & Customer Details

| Criterion | Flag Logic |
|---------|-----------|
| Client-facing note ≤ 15 min | 🔶 (offline unverifiable) |
| Record client name & phone | 🚫 (inbound calls only) |
| Professional tone | ✅ ⚠️ ❌ |
| Respond promptly & appropriately | ✅ ⚠️ ❌ |

---

## 2️⃣ Ticket Investigation, Troubleshooting & Hygiene

| Criterion | Flag Logic |
|---------|-----------|
| Address chronic issues | 🔶 (YES) / 🚫 (NO) |
| Client-facing troubleshooting | ✅ 🔶 🔴 |
| Notes quality | ✅ ⚠️ ❌ |
| Acronyms & structure | ✅ ⚠️ ❌ |
| Troubleshooting judgment | ✅ ⚠️ ❌ |

---

## 3️⃣ Ticket Process Management

**ALL criteria are always visible.**  
Only **2-Hour Updates** may contribute to scoring.

### 3.1 2-Hour Updates (CNS / FSO – Score-Eligible)

**Evaluation Method**
- Identify the employee under audit
- Find the **first** and **last** comment from that employee
- Evaluate elapsed time **between those two entries only**

**Flags**
- 🚫 → No CNS or FSO notes exist
- 🔶 → CNS/FSO exists but timestamps unclear
- ⚠️ → Cadence marginal (coaching)
- ✅ → Timing reasonable

❗ Multi-day gaps, system events, and other engineers’ notes are excluded.

---

### 3.2 Queue Reassignment  
*Always Manual Verification*

| Condition | Flag |
|---------|------|
| Cannot confirm offline | 🔶 |

---

### 3.3 TTR Clock  
*Visibility-only*

| Condition | Flag |
|---------|------|
| Requires system confirmation | 🔶 |

---

### 3.4 SLA Update Cadence  
*Visibility-only*

| Condition | Flag |
|---------|------|
| Always requires manual verification | 🔶 |

---

## 4️⃣ Ticket Resolution & Closeout

| Criterion | Flag Logic |
|---------|-----------|
| Device verification | ✅ ⚠️ ❌ 🔶 |
| Break-Fix template | 🔶 |
| Truck roll prevention | 🔶 |
| ESA / SOW alignment | ✅ ⚠️ ❌ |
| Resolution code | ✅ ❌ 🔶 |
| Client notification | 🚫 (ECCC only) |

---

## ⚙️ Ping / Test-Out Verification Rule

Objective evidence required:
- Raw ping output
- HTTP/HTTPS OK
- Monitoring confirmation

| Condition | Result |
|---------|--------|
| Evidence present | ✅ |
| Summary only | ❌ |
| Partial / unclear | 🔶 |

---

## 🔴 Critical Criteria Logic

Applies **only** to missing client-facing troubleshooting.

| Condition | Result |
|---------|--------|
| Internal-only notes | 🔴 50% override |
| Incomplete client-facing note | 🔶 |
| Critical confirmed | Final score forced to 50% |
| Critical unconfirmed | Remove critical |

---

## 🔶 Manual Verification Phase

If 🔶 items exist:
- Display **one consolidated list**
- Auditor marks each item Pass or Fail
- **No scoring allowed** during this phase

---

## 🧮 Atomic Recalculation Rule

Once all 🔶 items are resolved:
- Recalculate the audit **once, from scratch**
- Reprint Ticket & Site Context
- No incremental math

---

## 📊 Final Scoring (MANDATORY OUTPUT)

### Category Score Breakdown  
(Only score-eligible criteria)

Example:
- Acknowledgement & Customer Details: X / Y  
- Ticket Investigation & Hygiene: X / Y  
- **2-Hour Updates:** X / 1  
- Ticket Resolution & Closeout: X / Y  

### Total Score
- Points Earned / Points Available
- Percentage
- Pass / Fail

---

## 🧾 Coaching-Ready Summary (MANDATORY)

Provide a copy-paste-ready block:

Acknowledgement & Customer Details: X/Y
Ticket Investigation & Hygiene: X/Y
2-Hour Updates: X/1
Ticket Resolution & Closeout: X/Y
Total Score: X/X → XX%

yaml
Copy code

---

## ❌ Invalid Audit Conditions

An audit is INVALID if:
- Any criterion is hidden
- A score is shown while 🔶 exists
- Evaluated criteria are excluded from scoring
- Totals are missing

Invalid audits must be regenerated.

---

## 🧮 Scoring Logic

- ✅ = 1  
- ❌ / ⚠️ = 0  
- 🔶 / 🚫 = excluded  

```python
if flag in ["🔶", "🚫"]:
    exclude_from_total = True
elif flag in ["❌", "⚠️"]:
    credit = 0
elif flag == "✅":
    credit = 1
📤 Required Presentation Order (LOCKED)
Ticket & Site Context

Category Evaluation (tables; all criteria visible)
Manual Verification Items
Strengths
Opportunities
Final Scoring
Coaching-Ready Summary
Auditor Notes
Deviation invalidates the audit.
