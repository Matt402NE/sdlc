# Workflow 8 — Prototype‑First Workflow  
*A workflow where Product and Engineering create a lightweight prototype early to validate assumptions, reduce ambiguity, and clarify scope before any estimation or backlog commitment.*

---

## Overview
This workflow begins with a **rapid prototype**—low‑fidelity or high‑fidelity depending on the need—before any formal shaping or estimation occurs.  
The prototype is used to validate assumptions, test user flows, expose technical constraints, and surface decision debt early.  
Only after the prototype is reviewed and refined does the team move into feasibility, risk scoring, and backlog readiness.

This workflow is ideal for UX‑heavy features, ambiguous requests, or initiatives where “showing” is more effective than “describing.”

---

## When to Use
- User-facing features with unclear flows or interactions  
- Ambiguous requests where stakeholders struggle to articulate needs  
- Initiatives requiring early user validation  
- Teams wanting to reduce rework caused by misunderstood requirements  
- Situations where visualizing the solution is more efficient than documenting it  

---

## Required Artifacts
1. **Prototype Brief** (product-owned)  
   - Problem statement  
   - Target users  
   - Key scenarios to prototype  
   - Success metrics  
   - Assumptions and open questions  

2. **Rapid Prototype** (product + engineering + design)  
   - Low-fidelity wireframes, clickable mockups, or simple UI flows  
   - Technical feasibility notes (if applicable)  
   - User feedback (optional but encouraged)  

3. **Prototype Review Summary** (cross-functional)  
   - Validated assumptions  
   - Invalidated assumptions  
   - Updated scope boundaries  
   - Decision debt items  
   - Recommended next steps  

4. **Engineering Feasibility Snapshot** (engineering-owned)  
   - T-shirt estimate  
   - Confidence level  
   - Technical unknowns  
   - Required discovery spikes  

---

## Decision Gates
### Gate 1 — Prototype Eligibility  
**Decision Required:** Is the request ambiguous or UX-heavy enough to warrant prototyping?  
- Yes → Build prototype  
- No → Use a simpler workflow  
- Cannot decide → Risk +1 (Ambiguity)

### Gate 2 — Prototype Creation  
**Decision Required:** Is the prototype complete enough to validate assumptions?  
- Yes → Prototype Review  
- No → Continue prototyping  
- Cannot decide → Risk +2 (Scope uncertainty)

### Gate 3 — Prototype Review  
**Decision Required:** Are assumptions validated and scope boundaries clear?  
- Yes → Engineering Feasibility  
- No → Refine prototype  
- Cannot decide → Risk +3 (Misalignment)

### Gate 4 — Engineering Feasibility  
**Decision Required:** Can engineering estimate based on the refined prototype?  
- Yes → Backlog Readiness  
- No → Discovery spike required  
- Cannot decide → Risk +3 (Technical unknowns)

---

## Risk Model (Semi-Quantitative)
Each missing decision or unclear prototype element adds weighted risk:

| Category | Weight | Meaning |
|----------|--------|---------|
| Unvalidated assumptions | +3 | High chance of rework |
| Ambiguous user flows | +2 | UX inconsistency risk |
| Technical unknowns | +3 | Estimation volatility |
| Missing success metrics | +2 | Hard to validate outcomes |
| Prototype gaps | +2 | Scope uncertainty |
| Cross-team misalignment | +2 | Coordination risk |

**Risk Score Interpretation**  
- **0–4** → Low (Green)  
- **5–8** → Moderate (Yellow)  
- **9+** → High (Red)  

High-risk items require explicit acceptance from Product and Engineering before backlog entry.

---

## Pros
- Reduces ambiguity early  
- Helps stakeholders visualize the solution  
- Surfaces UX and technical issues before estimation  
- Encourages user-centered thinking  
- Reduces rework caused by misunderstood requirements  

---

## Cons
- Requires design or prototyping capability  
- May slow intake for simple requests  
- Risk of over-investing in prototypes  
- Requires discipline to keep prototypes lightweight  

---

## How It Protects Engineering Time
- Engineering avoids estimating unclear or ambiguous requests  
- Prototype clarifies flows, reducing rework  
- Technical unknowns are surfaced early  
- Discovery spikes are targeted and justified  

---

## How It Fits a 2-Week Sprint Cadence
- Prototype brief: 1–2 days  
- Prototype creation: 3–5 days  
- Prototype review: 1 day  
- Feasibility snapshot: 1–2 days  

Typically fits within **one sprint**, though complex prototypes may span two.

---

## How It Differs from Design Thinking
- No ideation loops or divergent exploration  
- Prototype is functional, not exploratory  
- Focuses on validation, not creativity  
- Structured gates and risk scoring replace open-ended workshops  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions appear as “prototype gaps”  
- Decision debt is explicitly tracked in the review summary  
- Backlog entry requires acknowledgment of unresolved assumptions  
- Risk score increases for unvalidated flows or unknowns  

---

## Summary
A prototype-first workflow that reduces ambiguity, validates assumptions, and clarifies scope before estimation—ideal for UX-heavy or ambiguous initiatives where visualizing the solution accelerates alignment.