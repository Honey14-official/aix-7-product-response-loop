# 🤖 Use Case: LLM Hallucinations in a Legal Chatbot

## Overview

This case study shows how the AIX-7 framework was applied to a real-world issue with a Large Language Model (LLM) based chatbot used by a legal tech platform.

Users reported that the chatbot was confidently citing **non-existent legal cases**, causing trust issues and internal escalation.

## ⚠️ The Problem

The LLM was trained on diverse legal content but lacked real-time citation verification. Users received hallucinated case laws like:

- "ABC vs. State, 2021 SCC 3499" — which doesn't exist.
- Invented court verdicts that were confidently presented as real.

Trust in the system dropped, and users began cross-checking everything manually — defeating the product’s core value.

## ✅ Applying the AIX-7 Framework

### 1. Assess
- Multiple hallucinated responses were traced in user logs.
- Trust dropped — NPS fell from 34 to 11 in two weeks.
- Internal audit found 6+ incorrect citations in recent queries.

### 2. Clarify
- The hallucination stemmed from the model’s generative limits, not retrieval error.
- Responses sounded factually correct but had no grounding.

### 3. Shape
- Defined action thresholds: flag if 2+ hallucinations are detected in a batch of 100.
- Retrain only if error rate exceeds 3% across top queries.

### 4. Prioritize
- Immediate fix needed due to reputational risk and legal sensitivity.
- Ranked high on both business impact and user experience degradation.

### 5. Own
- Data Science → Added grounding checks and citation verification.
- MLOps → Built a fallback to retrieval-based templates.
- Product → Issued communication and added disclaimer to UI.

### 6. Sprint
- Introduced a verification layer using a legal case database.
- Deployed post-response filtering and hallucination scoring.

### 7. Optimize
- Weekly hallucination rate dropped by 82%.
- NPS recovered to 28 in 30 days.
- Product team added an “Explain This” button to improve transparency.

## 📈 Outcome

- 🚫 82% drop in false case citations
- 🧠 Improved user trust and retention
- 🧪 Added guardrails and verification logic without disabling LLM flexibility

## 🔁 Key Takeaway

> Hallucinations aren’t always a model bug. AIX-7 helped us redesign the system around trust — not just text generation.
