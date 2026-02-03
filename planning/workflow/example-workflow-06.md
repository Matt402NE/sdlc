# Workflow 6 — Value–Effort Matrix Workflow  
*A workflow where Product, Business, and Engineering collaboratively score value and effort to determine whether a request is ready for backlog entry, with confidence and decision debt directly influencing priority.*

---

## Overview
This workflow uses a **Value–Effort Matrix** as the central decision mechanism.  
Instead of relying on intuition or loosely defined priorities, each request is evaluated across structured value dimensions (business, user, strategic) and effort dimensions (complexity, unknowns, dependencies).  
Confidence levels and missing decisions directly affect the scoring, making decision debt visible and actionable.

This workflow is ideal for teams that want a more analytical, transparent prioritization process without heavy ceremony.

---

## When to Use
- Teams that want consistent, objective prioritization  
- Organizations where Business and Product disagree on value  
- Environments with limited engineering capacity  
- Teams that want to expose uncertainty and decision debt early  
- Portfolios with many competing requests  

---

## Required Artifacts
1. **Value Scoring Sheet** (business + product)  
   - Business value  
   - User value  
   - Strategic alignment  
   - Revenue or cost impact  
   - Confidence level for each score  

2. **Effort Scoring Sheet** (engineering)  
   - Technical complexity  
   - Integration difficulty  
   - Unknowns and risks  
   - Dependencies  
   - Confidence level for each score  

3. **Value–Effort Matrix Placement** (cross-functional)  
   - Quadrant: Quick Win / Major Project / Fill-In / Avoid  
   - Decision debt indicators  
   - Recommended next steps  

4. **Backlog Readiness Summary** (product-owned)  
   - Final matrix placement  
   - Updated risk score  
   - Go/No-Go recommendation  

---

## Decision Gates
### Gate 1 — Value Scoring  
**Decision Required:** Has Business and Product agreed on value scoring?  
- Yes → Effort Scoring  
- No → Clarify value  
- Cannot decide → Risk +2 (Value uncertainty)

### Gate 2 — Effort Scoring  
**Decision Required:** Has Engineering provided effort scoring with confidence levels?  
- Yes → Matrix Placement  
- No → Discovery spike required  
- Cannot decide → Risk +3 (Technical unknowns)

### Gate 3 — Matrix Placement  
**Decision Required:** Does the team agree on the quadrant and implications?  
- Yes → Backlog Readiness  
- No → Revisit scoring  
- Cannot decide → Risk +2 (Cross-functional misalignment)

### Gate 4 — Backlog Readiness  
**Decision Required:** Is the request ready for backlog entry based on value, effort, and confidence?  
- Yes → Add to backlog  
- No → Additional refinement required  
- Cannot decide → Risk +2 (Strategic uncertainty)

---

## Risk Model (Semi-Quantitative)
Each missing decision or low-confidence score adds weighted risk:

| Category | Weight | Meaning |
|----------|--------|---------|
| Low value confidence | +2 | Value may be overstated |
| Low effort confidence | +3 | High volatility |
| Missing success metrics | +2 | Hard to validate outcomes |
| Technical unknowns | +3 | Estimation risk |
| Dependency uncertainty | +2 | Scheduling risk |
| Strategic misalignment | +2 | Low ROI |

**Risk Score Interpretation**  
- **0–4** → Low (Green)  
- **5–8** → Moderate (Yellow)  
- **9+** → High (Red)  

High-risk items require explicit Business acceptance before backlog entry.

---

## Pros
- Transparent, structured prioritization  
- Makes decision debt visible  
- Encourages alignment across functions  
- Helps avoid overcommitting to low-value, high-effort work  
- Works well for portfolio-level planning  

---

## Cons
- Requires discipline in scoring  
- Can feel “numerical” or rigid to some stakeholders  
- May slow intake for simple requests  
- Confidence scoring requires maturity  

---

## How It Protects Engineering Time
- Engineering only estimates effort after value is clear  
- Effort scoring focuses on complexity, not solutioning  
- Low-confidence scores trigger discovery spikes before commitment  
- Prevents engineering from inheriting low-value work  

---

## How It Fits a 2-Week Sprint Cadence
- Value scoring: 1–2 days  
- Effort scoring: 1–2 days  
- Matrix placement: 1 day  
- Backlog readiness: 1 day  

Entire workflow fits comfortably within **one sprint**.

---

## How It Differs from Design Thinking
- No ideation or prototyping  
- Focuses on structured evaluation, not exploration  
- Uses scoring and matrices instead of qualitative insights  
- Designed for prioritization, not creativity  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions reduce confidence and increase risk  
- Decision debt is explicitly reflected in the matrix  
- Low-confidence items may be deprioritized or require spikes  
- Backlog entry requires acknowledgment of remaining uncertainty  

---

## Summary
A structured, analytical workflow that uses value and effort scoring to drive prioritization, expose decision debt, and ensure only high-value, well-understood requests enter the backlog.