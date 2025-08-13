# 🧠 AIX-7: Product Response Loop – Detailed Step Guide

> This document breaks down each step in the AIX-7 framework to help AI/ML product leaders solve system issues with precision, not panic.

---

## 🔁 The 7-Step Loop

The AIX-7 framework follows a circular product decision-making cycle:

1. **Assess**  
2. **Clarify**  
3. **Shape**  
4. **Prioritize**  
5. **Own**  
6. **Sprint**  
7. **Optimize**

Each step builds alignment between business goals, model behavior, and team action.

---

## 1. 🔍 Assess – Do we have a real issue?

**Goal:** Confirm that a system signal (drift, feedback, bug, alert) actually indicates a problem worth exploring.

**How to do it:**
- Check input signals: drift logs, changes in input schema, new patterns in data.
- Check model outputs: accuracy, precision, recall, ranking quality.
- Check business indicators: drop in conversions, user complaints, NPS.
- Use user-facing metrics (e.g., satisfaction score, usage patterns) to validate.

**Example:**  
Drift alert fires because resumes now include newer university names — but recruiter feedback shows no drop in quality. The alert is a false alarm.

---

## 2. 🧠 Clarify – What kind of issue is it?

**Goal:** Identify the **nature** of the issue — not all issues are critical.

**How to do it:**
- Is it cosmetic or behavioral?
- Does it affect output format or output meaning?
- Use sampling to trace changes across model layers (input → features → output).

**Tip:** Build a drift taxonomy:
- Cosmetic drift (e.g., resume formatting)
- Feature shift (e.g., new degree names)
- Prediction quality shift (e.g., less relevant recommendations)
- User perception drift (e.g., reduced trust despite same accuracy)

---

## 3. 🎯 Shape – What defines a meaningful fix?

**Goal:** Set **thresholds for action** that prevent overreaction.

**How to do it:**
- Define what metrics must change to trigger retraining, rollback, or redesign.
- Create rules like:  
  *"Retrain only if accuracy drops > 3% AND user approval < 85%"*

**Deliverable:**  
A **decision matrix** — what action to take for each level of impact.

---

## 4. ⚖️ Prioritize – Is it the right thing to act on now?

**Goal:** Evaluate **effort vs. outcome** to guide urgency.

**How to do it:**
- Use RICE, ICE, or Impact/Effort matrix.
- Estimate:
  - Engineering time lost due to false alerts
  - Value of resolving this issue now vs. later
  - Tradeoffs vs. roadmap items

**Example:**  
If fixing a hallucination in an internal LLM chatbot will take 3 sprints, but is only used by 2% of the team — it may not be worth it yet.

---

## 5. 🧩 Own – Who does what?

**Goal:** Assign **accountability** across the cross-functional team.

**How to do it:**
- Break down workstreams:
  - Data Science → Evaluate metrics + sampling
  - MLOps → Adjust alerts, deploy patch pipelines
  - Product → Approve fix triggers, update documentation
  - QA → Define new acceptance criteria

**Tip:** Include it in your runbook or Notion playbook.

---

## 6. 🚀 Sprint – What’s the minimal way to test?

**Goal:** Test the proposed fix with minimal waste.

**How to do it:**
- Build a simulation loop:
  - Sample recent inputs
  - Run both current + proposed model
  - Compare predictions + business metrics
- Only deploy if simulation shows improvement

**Deliverable:**  
A mini test harness or a post-deployment performance gate.

---

## 7. 🔄 Optimize – What did we learn?

**Goal:** Close the loop and tune your system for the next signal.

**How to do it:**
- Log false positives and true failures
- Adjust thresholds or models accordingly
- Add new alerts, remove noisy ones
- Update the runbook and document what triggered retraining

**Tip:**  
Track the ratio of real issues to false alerts → Aim to improve this over time.

---

## 📌 Summary Flow (Visual)

[Insert diagram here → decision-loop.png]

---

## 📈 Example Use Cases Covered by AIX-7

| Use Case | Example System | What AIX-7 Helps Decide |
|----------|----------------|--------------------------|
| Resume scoring | ML hiring platform | Whether data drift alert is valid |
| LLM hallucinations | Chatbot answering legal queries | Whether user complaints need fine-tuning or guardrails |
| Model bias | University-skewed ranking | Whether to retrain or reweigh the model |
| Ecom search | Ranking irrelevant products | Whether to adjust user signals or retrain embeddings |

---

## ✍️ Authored by

Honey Srivastava  
Product & AI Strategy Leader | [aixproduct.ai](https://aixproduct.ai)

---

