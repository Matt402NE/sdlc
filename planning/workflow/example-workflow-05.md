# Workflow 5 — Risk‑First Planning Workflow  
*A workflow where every request is evaluated, shaped, and prioritized based on its risk profile before any estimation or backlog commitment is made.*

---

## Overview
This workflow flips the traditional intake model: instead of starting with scope, value, or feasibility, it begins with **risk identification and risk scoring**.  
Product, Business, and Engineering collaborate early to surface ambiguity, technical unknowns, strategic uncertainty, and dependency risks.  
Only once the risk profile is understood does the team shape scope, estimate effort, or consider backlog entry.

This workflow is ideal for organizations that frequently encounter surprises late in delivery or want to proactively manage decision debt.

---

## When to Use
- Teams that struggle with late‑stage surprises or unclear requirements  
- Organizations with complex systems or high dependency environments  
- Initiatives where risk is a better predictor of effort than scope  
- Teams wanting to make risk visible early to Business stakeholders  
- Environments where decision debt frequently accumulates  

---

## Required Artifacts
1. **Risk Identification Canvas** (cross-functional)  
   - Ambiguity risks  
   - Technical risks  
   - Strategic risks  
   - Dependency risks  
   - Budget/timeline risks  
   - Compliance or regulatory risks  

2. **Risk Scoring Matrix** (product-owned)  
   - Weighted scoring across categories  
   - Decision debt indicators  
   - Confidence levels  

3. **Risk Mitigation Plan** (product + engineering)  
   - Actions to reduce risk  
   - Required discovery spikes  
   - Decisions needed and deadlines  
   - Owners for each mitigation item  

4. **Backlog Readiness Summary** (product-owned)  
   - Updated risk score  
   - Mitigation status  
   - Go/No-Go recommendation  

---

## Decision Gates
### Gate 1 — Risk Identification  
**Decision Required:** Have all major risks been identified?  
- Yes → Risk Scoring  
- No → Continue identification  
- Cannot decide → Risk +2 (Ambiguity)

### Gate 2 — Risk Scoring  
**Decision Required:** Is the risk score complete and agreed upon?  
- Yes → Mitigation Planning  
- No → Clarify scoring  
- Cannot decide → Risk +2 (Misalignment)

### Gate 3 — Mitigation Planning  
**Decision Required:** Are mitigation steps defined and owned?  
- Yes → Backlog Readiness  
- No → Continue planning  
- Cannot decide → Risk +3 (Execution uncertainty)

### Gate 4 — Backlog Readiness  
**Decision Required:** Is the risk profile acceptable for backlog entry?  
- Yes → Add to backlog  
- No → Additional mitigation required  
- Cannot decide → Risk +3 (Strategic uncertainty)

---

## Risk Model (Semi-Quantitative)
Each risk category is scored 1–5 for **Likelihood** and **Impact**, then multiplied:

```
text{Risk Score} = text{Likelihood} times text{Impact}
```

Weighted categories:

| Category | Weight | Notes |
|----------|--------|-------|
| Ambiguity | ×1 | Missing clarity or decisions |
| Technical | ×2 | Unknowns, integrations, architecture |
| Strategic | ×2 | Alignment, value, prioritization |
| Dependencies | ×1 | Cross-team or external |
| Budget/Timeline | ×1 | Investment uncertainty |
| Compliance | ×3 | Regulatory or legal exposure |

**Risk Score Interpretation**  
- **0–10** → Low (Green)  
- **11–20** → Moderate (Yellow)  
- **21+** → High (Red)  

High-risk items require explicit Business acceptance before backlog entry.

---

## Pros
- Makes risk visible early  
- Reduces late-stage surprises  
- Encourages cross-functional alignment  
- Helps prioritize work based on volatility, not just value  
- Forces early decision-making or explicit acceptance of decision debt  

---

## Cons
- More ceremony than value-first workflows  
- Requires maturity in risk thinking  
- May slow intake for low-risk items  
- Business may resist early risk exposure  

---

## How It Protects Engineering Time
- Engineering only estimates after risk is understood  
- Technical unknowns are surfaced before any commitment  
- Discovery spikes are targeted and justified  
- Reduces rework caused by hidden complexity  

---

## How It Fits a 2-Week Sprint Cadence
- Risk identification: 1–2 days  
- Risk scoring: 1 day  
- Mitigation planning: 2–3 days  
- Backlog readiness: 1 day  

Entire workflow fits within **one sprint**, even for complex items.

---

## How It Differs from Design Thinking
- No ideation or prototyping unless needed for mitigation  
- Focuses on uncertainty, not creativity  
- Uses structured scoring instead of qualitative exploration  
- Designed to reduce volatility, not generate ideas  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions directly increase the risk score  
- Decision debt is explicitly tracked and visible  
- Business must accept risk before backlog entry  
- Mitigation plans can include “decision deadlines”  

---

## Summary
A risk‑driven planning workflow that surfaces uncertainty early, quantifies decision debt, and ensures Product, Business, and Engineering align on risk before committing work to the backlog.