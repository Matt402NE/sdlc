# Workflow 4 — Dual-Track Discovery Workflow  
*A workflow where Product and Engineering run parallel discovery tracks to reduce ambiguity, validate feasibility, and converge on a clear, low-risk backlog-ready request.*

---

## Overview
This workflow introduces **two parallel discovery tracks**—one led by Product (Problem Discovery) and one led by Engineering (Technical Discovery).  
The goal is to reduce ambiguity early, expose risks, and ensure that both the problem and the solution space are well understood before committing to delivery.

This workflow is ideal for complex, ambiguous, or high-impact initiatives where early clarity dramatically reduces downstream risk.

---

## When to Use
- Requests with unclear problem framing or multiple possible solutions  
- Initiatives involving new technology, integrations, or architectural changes  
- Situations where Product and Engineering need to explore in parallel  
- Teams wanting to avoid waterfall while still reducing early uncertainty  
- High-risk or high-visibility projects where decision debt is expensive  

---

## Required Artifacts
1. **Product Problem Discovery Brief** (product-owned)  
   - Refined problem statement  
   - User needs and pain points  
   - Success metrics  
   - Assumptions and open questions  
   - Early scope boundaries  

2. **Engineering Technical Discovery Brief** (engineering-owned)  
   - Technical unknowns  
   - Integration points  
   - Architectural considerations  
   - Risks and constraints  
   - Required spikes or prototypes  

3. **Joint Discovery Summary** (product + engineering)  
   - Agreed problem framing  
   - Feasible solution directions  
   - Updated risk score  
   - Recommended next steps  
   - Go/No-Go recommendation for backlog entry  

---

## Decision Gates
### Gate 1 — Discovery Eligibility  
**Decision Required:** Is the request ambiguous or complex enough to warrant dual-track discovery?  
- Yes → Begin parallel discovery  
- No → Use a simpler workflow  
- Cannot decide → Risk +1 (Ambiguity)

### Gate 2 — Product Problem Discovery  
**Decision Required:** Is the problem clearly defined and validated?  
- Yes → Engineering Technical Discovery  
- No → Continue Product discovery  
- Cannot decide → Risk +2 (Problem uncertainty)

### Gate 3 — Engineering Technical Discovery  
**Decision Required:** Is the technical approach feasible and understood?  
- Yes → Joint Discovery Summary  
- No → Continue Engineering discovery  
- Cannot decide → Risk +3 (Technical unknowns)

### Gate 4 — Joint Discovery Review  
**Decision Required:** Are both tracks aligned on a viable, low-risk path forward?  
- Yes → Backlog entry  
- No → Additional discovery required  
- Cannot decide → Risk +2 (Cross-functional misalignment)

---

## Risk Model (Semi-Quantitative)
Each missing or deferred decision adds weighted risk:

| Category | Weight | Meaning |
|---------|--------|---------|
| Unclear problem | +2 | May cause rework or misalignment |
| Unvalidated assumptions | +2 | Risk of building the wrong thing |
| Technical unknowns | +3 | High volatility and estimation risk |
| Integration complexity | +2 | Scheduling and dependency risk |
| Architectural uncertainty | +3 | Long-term sustainability risk |
| Cross-team misalignment | +2 | Coordination and delivery risk |

**Risk Score Interpretation**  
- **0–4** → Low (Green)  
- **5–8** → Moderate (Yellow)  
- **9+** → High (Red)  

High-risk items require explicit acceptance from both Product and Engineering before proceeding.

---

## Pros
- Strong alignment between Product and Engineering  
- Reduces ambiguity early  
- Ideal for complex or high-risk initiatives  
- Encourages parallel exploration without waterfall  
- Produces a clear, shared understanding before backlog entry  

---

## Cons
- More ceremony than previous workflows  
- Requires dedicated time from both Product and Engineering  
- May slow intake for simpler requests  
- Requires discipline to avoid over-discovery  

---

## How It Protects Engineering Time
- Engineering only explores technical unknowns—not full solutions  
- Discovery spikes are time-boxed  
- Engineering avoids deep design until Product validates the problem  
- Joint summary prevents misaligned expectations  

---

## How It Fits a 2-Week Sprint Cadence
- Product discovery: 3–5 days  
- Engineering discovery: 3–5 days  
- Joint review: 1 day  

Dual-track discovery typically fits within **one sprint**, but can extend into two for complex initiatives.

---

## How It Differs from Design Thinking
- No workshops or ideation loops  
- No prototyping unless needed for technical discovery  
- Focuses on clarity and feasibility, not creativity  
- Structured gates and risk scoring replace open-ended exploration  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions increase risk but do not block discovery  
- Product and Engineering track decision debt separately  
- Joint summary explicitly lists unresolved decisions  
- Backlog entry requires acknowledgment of remaining risk  

---

## Summary
A structured, parallel discovery workflow that reduces ambiguity, aligns Product and Engineering early, and ensures complex initiatives enter the backlog with clarity, feasibility, and shared understanding.