# Workflow 2 — Joint Product/Engineering Readiness Gate  
*A collaborative intake workflow where Product and Engineering jointly validate clarity, feasibility, and risk before a request enters the product backlog.*

---

## Overview
This workflow creates a **shared gate** owned by both Product and Engineering.  
It emphasizes early technical feasibility, clearer decision points, and a more structured risk model than [Workflow #1](example-workflow-01.md).  
Business still initiates the request, but Product and Engineering jointly decide when it is ready for backlog entry.

---

## When to Use
- Teams where engineering wants earlier visibility into upcoming work  
- Organizations with complex systems or integrations  
- Environments where technical unknowns frequently derail estimates  
- Teams that want to avoid waterfall but need more rigor than a simple intake brief

---

## Required Artifacts
1. **Business Intake Brief** (business-owned)  
   - Problem statement  
   - Target users  
   - Success criteria  
   - Budget guardrail  
   - Dependencies (internal/external)  
   - Urgency and strategic alignment  

2. **Product Clarification Addendum** (product-owned)  
   - Refined problem framing  
   - Proposed scope boundaries  
   - Assumptions and open questions  
   - Initial risk score (pre-engineering)  

3. **Engineering Feasibility Snapshot** (engineering-owned)  
   - Technical unknowns  
   - Integration points  
   - Rough t-shirt estimate  
   - Confidence level  
   - Required discovery spikes (if any)

---

## Decision Gates
### Gate 1 — Business Intake Validation  
**Decision Required:** Is the intake brief complete enough for Product to refine?  
- Yes → Product Clarification  
- No → Returned to business  
- Cannot decide → Risk +1 (Ambiguity)

### Gate 2 — Product Clarification  
**Decision Required:** Is the problem well-defined and aligned with strategy?  
- Yes → Engineering Feasibility  
- No → Returned to business  
- Cannot decide → Risk +2 (Strategic uncertainty)

### Gate 3 — Engineering Feasibility  
**Decision Required:** Can engineering provide a meaningful t-shirt estimate?  
- Yes → Joint Readiness Review  
- No → Discovery spike required  
- Cannot decide → Risk +3 (Technical unknowns)

### Gate 4 — Joint Readiness Review  
**Decision Required:** Is the request ready for the product backlog?  
- Yes → Added to backlog  
- No → Returned with specific gaps  
- Cannot decide → Risk +2 (Cross-functional misalignment)

---

## Risk Model (Semi-Quantitative)
Each missing or deferred decision adds weighted risk:

| Category | Weight | Meaning |
|---------|--------|---------|
| Ambiguous problem | +1 | May cause rework |
| Unclear success metrics | +2 | Hard to validate outcomes |
| Missing budget guardrail | +2 | Cost uncertainty |
| Technical unknowns | +3 | High volatility |
| Integration complexity | +2 | Scheduling risk |
| Cross-team alignment gaps | +2 | Coordination risk |

**Risk Score Interpretation**  
- **0–3** → Low (Green)  
- **4–7** → Moderate (Yellow)  
- **8+** → High (Red)  

High-risk items can still proceed but require explicit acknowledgment from both Product and Engineering.

---

## Pros
- Balanced ownership between Product and Engineering  
- Early technical visibility reduces surprises  
- Clearer decision gates than [Workflow #1](example-workflow-01.md)  
- Stronger risk modeling  
- Encourages alignment before backlog entry  

---

## Cons
- Slightly more ceremony than [Workflow #1](example-workflow-01.md)
- Requires consistent participation from engineering leads  
- May slow intake if engineering bandwidth is limited  
- Business may feel less autonomous  

---

## How It Protects Engineering Time
- Engineering only engages after Product clarifies the request  
- Feasibility snapshot prevents premature deep dives  
- Discovery spikes are time-boxed and optional  
- Joint review ensures engineering doesn’t inherit unclear work  

---

## How It Fits a 2-Week Sprint Cadence
- Business intake: 1–2 days  
- Product clarification: 2–3 days  
- Engineering feasibility: 2–3 days  
- Joint review: 1 day  

Entire workflow fits within a single sprint or can span two sprints for complex items.

---

## How It Differs from Design Thinking
- No ideation loops or prototyping required  
- Focuses on feasibility and alignment, not exploration  
- Decisions are explicit, not emergent  
- Risk scoring replaces qualitative “gut feel”  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions increase risk but do not block progress  
- Product and Engineering jointly decide whether to proceed  
- Risk score is visible to Business before backlog entry  
- Deferred decisions are logged as “decision debt” items  

---

## Summary
A balanced, collaborative intake workflow that increases clarity, reduces technical surprises, and introduces structured decision gates without drifting into waterfall.