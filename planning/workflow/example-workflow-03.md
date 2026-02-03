# Workflow 3 — Business-Owned Intake Gate with Structured Readiness Criteria  
*A workflow where Business must complete a structured intake package before Product or Engineering engages, ensuring only well‑formed requests enter the planning pipeline.*

---

## Overview
This workflow places the **first gate entirely on [Business](business.md)**, requiring them to complete a structured intake package before [Product](product.md) reviews the request.  
It reduces noise, protects Product and [Engineering](engineering.md) time, and forces clarity around value, budget, and success metrics before any technical or product shaping occurs.

---

## When to Use
- Organizations where Business frequently submits vague or incomplete requests  
- Teams overwhelmed by too many low‑quality or low‑value ideas  
- Environments where Product and Engineering need stronger upstream filtering  
- Companies with clear strategic priorities and budget constraints  

---

## Required Artifacts
1. **Business Intake Package** (business-owned)  
   - Problem statement  
   - Target users  
   - Success metrics (must be measurable)  
   - Budget guardrail or investment range  
   - Strategic alignment statement  
   - Dependencies (internal/external)  
   - Expected timeline or urgency  
   - Risks of not doing the work  

2. **Product Readiness Assessment** (product-owned)  
   - Validation of clarity and alignment  
   - Identification of assumptions or gaps  
   - Initial risk score (pre-engineering)  
   - Recommendation: Proceed / Needs Revision / Reject  

3. **Engineering Feasibility Snapshot** (engineering-owned)  
   - T-shirt estimate  
   - Confidence level  
   - Technical unknowns  
   - Required discovery spikes  

---

## Decision Gates
### Gate 1 — Business Intake Completion  
**Decision Required:** Is the intake package complete and internally approved by Business?  
- Yes → Product Readiness Assessment  
- No → Returned to Business  
- Cannot decide → Risk +1 (Ambiguity)

### Gate 2 — Product Readiness  
**Decision Required:** Is the request clear, aligned, and valuable enough to warrant engineering time?  
- Yes → Engineering Feasibility  
- No → Returned to Business with gaps  
- Cannot decide → Risk +2 (Strategic uncertainty)

### Gate 3 — Engineering Feasibility  
**Decision Required:** Can engineering provide a meaningful t-shirt estimate?  
- Yes → Product Backlog Entry  
- No → Discovery spike required  
- Cannot decide → Risk +3 (Technical unknowns)

---

## Risk Model (Semi-Quantitative)
Each missing or deferred decision adds weighted risk:

| Category | Weight | Meaning |
|---------|--------|---------|
| Ambiguous problem | +1 | May cause rework |
| Unclear success metrics | +3 | Hard to validate outcomes |
| Missing budget guardrail | +2 | Cost uncertainty |
| Strategic misalignment | +3 | Low value or wasted effort |
| Technical unknowns | +3 | High volatility |
| Cross-team dependencies | +2 | Scheduling risk |

**Risk Score Interpretation**  
- **0–3** → Low (Green)  
- **4–7** → Moderate (Yellow)  
- **8+** → High (Red)  

High-risk items can proceed only if Business explicitly accepts the risk.

---

## Pros
- Strong upstream filtering  
- Protects Product and Engineering time  
- Forces Business to articulate value and budget  
- Reduces churn and vague requests  
- Clear accountability for early decisions  

---

## Cons
- Higher ceremony for Business  
- May slow intake if Business is not disciplined  
- Risk of Business over-specifying solutions  
- Requires Business to have strategic clarity  

---

## How It Protects Engineering Time
- Engineering is not involved until Product validates clarity  
- No feasibility work happens without a complete intake package  
- Discovery spikes are only triggered after Product approval  

---

## How It Fits a 2-Week Sprint Cadence
- Business intake: 2–5 days (varies by organization)  
- Product readiness: 1–3 days  
- Engineering feasibility: 1–2 days  

This workflow may span **one or two sprints**, depending on Business readiness.

---

## How It Differs from Design Thinking
- No ideation or exploration loops  
- No prototyping required  
- Business must define the problem and value upfront  
- Product shapes the solution only after clarity exists  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions increase risk and must be explicitly accepted by Business  
- Product cannot proceed without a complete intake package  
- Engineering only engages once risk is understood and acknowledged  

---

## Summary
A structured, Business-owned intake workflow that ensures clarity, value, and budget alignment before Product or Engineering invests time—ideal for organizations needing stronger upstream discipline.