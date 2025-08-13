# 📝 Use Case: HR Resume Drift Detection

## Overview

This use case shows how the AIX-7 framework was applied to a real-world scenario: a hiring platform that uses machine learning to rank job candidates based on their resumes.

Every morning, the ML system flagged "Data Drift Detected" — yet recruiter satisfaction stayed high and the model seemed to work fine.

## ⚠️ The Problem

The ML model began flagging drift in resumes due to:

- New university names
- Updated degree formats
- Slight job title variations

The engineering team was stopping their work to retrain the model — despite no clear impact on ranking quality.

## ✅ Applying the AIX-7 Framework

### 1. Assess
- Drift detection was confirmed (e.g., new universities, formats).
- Model accuracy and recruiter feedback showed no degradation.
- Business KPIs were stable — % of hired candidates remained consistent.

### 2. Clarify
- The drift was cosmetic, not semantic.
- Bullet point styles or new degree phrasing should not trigger retraining.

### 3. Shape
- A threshold was set: retrain only if accuracy drops >3% and recruiter satisfaction <85%.

### 4. Prioritize
- Engineering teams were losing 2 weeks per quarter retraining unnecessarily.
- This issue was prioritized to save effort and rebuild trust in monitoring alerts.

### 5. Own
- Data Science → Adjust drift thresholds and validate impact.
- MLOps → Added sampling logic to dashboards.
- Product → Updated decision rules and playbooks.

### 6. Sprint
- Built a sampling tool: detect drift → sample new resumes → compare model output vs. recruiter feedback.

### 7. Optimize
- Over 2 months, drift noise reduced 70%.
- Engineers regained focus.
- Model performance stayed stable.

## 📈 Outcome

- ⚙️ False alarms reduced by 70%
- 🧠 Team trust in monitoring restored
- 📉 Zero drop in hiring quality
- 💰 Saved 4 weeks of dev time annually

## 🔁 Key Takeaway

> Not all ML drift requires reaction. AIX-7 helped us respond with impact, not overengineering.
