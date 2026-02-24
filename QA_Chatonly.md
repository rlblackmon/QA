# QA Rulebook: Chat Only
Version: 1.4.12
Last Updated: 2026-02-24
Scope: Chat transcript QA
Dependencies:
- shared_definitions.md
- scoring_scale.md
- output_template.md

# 💬 GSA MES Engineering – Chat QA Instruction Set  
**Production v1.4.12 – Evaluation vs. Resolution Clarification Patch**

---

## ⚙️ Evaluator Context & Flow

Chats are evaluated under the **GSA MES Engineering QA 2025 Framework**.

This audit enforces:
- Context-first evaluation
- Mandatory manual-verification gating
- Critical logic isolation
- Binary criterion indicators
- Atomic regeneration and finalization

**Initial evaluation is CONTEXT-ONLY**:
- Chat transcript
- Engagement metadata

**Ticket notes MUST NOT be reviewed** during initial evaluation and are introduced **ONLY during Manual Verification or Supervisor Override**.

The system reports **audit state only**.

---

## 🛡️ Coaching-Only Audit Classification (GLOBAL ASSUMPTION)

This Chat QA Audit is **NOT** a formal employee performance evaluation, disciplinary action, or HR assessment.

All indicators, summaries, and observations are used **exclusively for coaching, process improvement, and best-practice reinforcement**.

Constraints:
- No HR classification
- No compensation or promotion linkage
- No disciplinary inference

---

## 🤖 Model Execution Boundary (GLOBAL)

This framework defines **evaluation structure and logic**, not external system certification.

The evaluator:
- MAY analyze chat transcripts for observable evidence
- MUST respect manual-gate defaults
- MUST allow supervisor authority to finalize gated items

Platform limitations do **NOT** invalidate the audit when best-effort adherence is applied.

---

## 🏷️ Indicator Key

🟩 Observed  
🟥 Not Observed  
🔶 Manual Verification Required  
🚫 N/A (not applicable)  
🔴 High-Risk (Non-Scored, Outcome-Impacting)

---

## 🧠 Evidence Annotation Rule (GLOBAL)

- **Every criterion MUST include an evidence statement**
- Evidence must state:
  - What source was reviewed
  - What was observed (or not observed)
  - Why the indicator applies
- Applies to **all indicators**
- Indicator-only rows invalidate the audit

---

## 🔁 Regeneration Rule (GLOBAL)

Any correction, override, or verification:
- Triggers **full regeneration**
- Partial edits are prohibited
- Prior outputs become invalid

---

## 👁️ Visibility Rule (GLOBAL)

- **ALL criteria MUST be displayed**
- No hiding or summarization
- One indicator per criterion
- Visibility ≠ resolution

---

## 📌 Engagement Context (MANDATORY)

Each audit MUST include:

- Engagement ID  
- Agent / Engineer  
- Technician / Contact  
- End Customer  
- Chat Channel  
- Chat Start / End  
- Final Disposition  
- Ticket Number(s) (if referenced)

If unavailable → **Not Provided**  
Inference is prohibited.

---

## 🔑 Evaluation vs. Resolution Rule (CRITICAL CLARIFICATION)

Some criteria are **evaluated from the chat transcript** but **cannot be finalized** without supervisor authority.

This distinction is mandatory.

---

## ⏱️ Acknowledgement Timing Criteria – SPECIAL HANDLING

**Applies to:**
- Client-facing acknowledgement ≤ 3 minutes  
- Client-facing acknowledgement ≤ 15 minutes  

Rules:

- Chat transcript timestamps **MUST be evaluated**
- Observed timing evidence **MUST be documented**
- Indicator **MUST default to 🔶 Manual Verification Required**
- Transcript evidence **DOES NOT auto-finalize**
- **Supervisor MAY override** using transcript evidence alone
- Absence of override = remains 🔶

🚫 These criteria are **NOT auto-blocked** from transcript evaluation  
🚫 These criteria are **NOT auto-finalized** by transcript alone

---

## 🧪 Test-Out Data Validation – SOURCE-OF-TRUTH LOCK

- Test-out validation **MUST NOT rely on chat transcript**
- Verbal confirmation is insufficient
- Acceptable sources:
  - Ticket notes
  - Monitoring artifacts
  - Screenshots / telemetry
- Default indicator: 🔶 Manual Verification Required
- Supervisor override **requires ticket-level evidence**

---

## 🎯 Scoring Unit Definition

- Each **non–High-Risk** criterion = 1 point
- **High-Risk criteria are NON-SCORED**
- Total scored criteria = **13**
- High-Risk failure impacts outcome but does not add points

---

## 🔓 Supervisor Authority (GLOBAL)

A Supervisor:
- MAY override **any criterion**
- MAY resolve 🔶 indicators
- MAY use transcript evidence where permitted
- Is the **final authority** on audit resolution

Overrides MUST be explicitly stated.

---

## 1️⃣ Acknowledgement & Respond Appropriately (4 Criteria)

| Criterion | Indicator | Evidence |
|---------|-----------|----------|
| Client-facing acknowledgement ≤ 3 minutes | 🔶 | Chat timestamps evaluated; supervisor confirmation required |
| Client-facing acknowledgement ≤ 15 minutes | 🔶 | Chat timestamps evaluated; supervisor confirmation required |
| Compliance script at chat start (High-Risk) | 🟩 | Script presence confirmed in transcript |
| Professional, respectful engagement | 🟩 | Tone and interaction observed throughout |

---

## 2️⃣ Own the Support Process (5 Criteria)

| Criterion | Indicator | Evidence |
|---------|-----------|----------|
| Correct Break/Fix structure followed | 🟩 | Structured workflow observed |
| Client-facing troubleshooting documented (High-Risk) | 🟩 | Steps visible in chat |
| Required troubleshooting completed (High-Risk) | 🟩 | Full workflow completed |
| Relevant test-out data validated | 🔶 | Requires ticket or monitoring evidence |
| Correct chat disposition used | 🟩 | Disposition matches outcome |

---

## 3️⃣ Effortless Chat Flow (3 Criteria)

| Criterion | Indicator | Evidence |
|---------|-----------|----------|
| Technician did not repeat requests | 🟩 | No repetition observed |
| Clear, readable communication | 🟩 | Instructions clear and sequenced |
| Proactive status updates | 🟩 | Updates provided throughout |

---

## 4️⃣ Technical Proficiency (1 Criterion)

| Criterion | Indicator | Evidence |
|---------|-----------|----------|
| Sound troubleshooting judgment | 🟩 | Correct diagnosis and execution |

---

## 5️⃣ Customer Interaction / Conduct (High-Risk)

| Criterion | Indicator | Evidence |
|---------|-----------|----------|
| No unprofessional or abusive conduct | 🟩 | No policy violations observed |

---

## 🔶 Manual Verification Disclosure (MANDATORY)

Indicators marked 🔶:
- Were evaluated where permitted
- Require supervisor resolution
- Do not auto-finalize

“This coaching-focused QA audit includes criteria requiring supervisor validation. Indicators marked 🔶 remain unresolved until explicitly overridden.”

---

## 🧾 Coaching Summary (MANDATORY)

- Observed strengths
- One or two targeted improvement areas
- No performance classification
