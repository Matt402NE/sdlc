# Workflow 7 — Design‑Guardrail Workflow  
*A workflow where Product and Engineering establish non‑negotiable guardrails early—technical, UX, architectural, and strategic—before shaping scope or estimating effort.*

---

## Overview
This workflow centers on defining **guardrails** before any solutioning or estimation begins.  
Guardrails are the constraints, principles, and boundaries that shape what *cannot* happen or what *must* be true for a request to proceed.  
By establishing these early, the team prevents architectural drift, UX fragmentation, and scope explosion.

This workflow is ideal for organizations with multiple teams, shared platforms, or a history of inconsistent design or technical decisions.

---

## When to Use
- Multi-team environments with shared systems or platforms  
- Organizations with strict UX, security, or architectural standards  
- Teams that frequently encounter scope creep or inconsistent solutions  
- Initiatives with high integration or compliance requirements  
- Situations where constraints matter more than creativity  

---

## Required Artifacts
1. **Business Intake Brief** (business-owned)  
   - Problem statement  
   - Success metrics  
   - Budget guardrail  
   - Dependencies  
   - Strategic alignment  

2. **Guardrail Definition Sheet** (product + engineering)  
   - Technical guardrails  
   - UX guardrails  
   - Architectural constraints  
   - Compliance/security requirements  
   - Non-negotiable boundaries  
   - Decision debt indicators  

3. **Solution Exploration Notes** (product-owned)  
   - Possible solution directions  
   - Impact of guardrails on scope  
   - Open questions  

4. **Engineering Feasibility Snapshot** (engineering-owned)  
   - T-shirt estimate  
   - Confidence level  
   - Technical unknowns  
   - Required discovery spikes  

---

## Decision Gates
### Gate 1 — Intake Validation  
**Decision Required:** Is the business request clear enough to define guardrails?  
- Yes → Guardrail Definition  
- No → Returned to Business  
- Cannot decide → Risk +1 (Ambiguity)

### Gate 2 — Guardrail Definition  
**Decision Required:** Are guardrails defined, agreed upon, and non-negotiable?  
- Yes → Solution Exploration  
- No → Continue guardrail alignment  
- Cannot decide → Risk +3 (Constraint uncertainty)

### Gate 3 — Solution Exploration  
**Decision Required:** Are solution directions viable within the guardrails?  
- Yes → Engineering Feasibility  
- No → Revisit guardrails or scope  
- Cannot decide → Risk +2 (Scope uncertainty)

### Gate 4 — Engineering Feasibility  
**Decision Required:** Can engineering estimate within the defined guardrails?  
- Yes → Backlog Readiness  
- No → Discovery spike required  
- Cannot decide → Risk +3 (Technical unknowns)

---

## Risk Model (Semi-Quantitative)
Each missing or unclear guardrail adds weighted risk:

| Category | Weight | Meaning |
|----------|--------|---------|
| Missing technical guardrails | +3 | Risk of architectural drift |
| Missing UX guardrails | +2 | Risk of inconsistent user experience |
| Missing compliance/security guardrails | +3 | Regulatory exposure |
| Ambiguous scope boundaries | +2 | Scope creep risk |
| Technical unknowns | +3 | Estimation volatility |
| Cross-team dependencies | +2 | Scheduling risk |

**Risk Score Interpretation**  
- **0–4** → Low (Green)  
- **5–8** → Moderate (Yellow)  
- **9+** → High (Red)  

High-risk items require explicit acceptance from Product and Engineering before backlog entry.

---

## Pros
- Prevents architectural drift and UX inconsistency  
- Creates clarity before solutioning  
- Reduces scope creep  
- Encourages alignment across Product and Engineering  
- Ideal for multi-team or platform environments  

---

## Cons
- Requires discipline to define guardrails well  
- May feel restrictive to creative stakeholders  
- Can slow intake if guardrails are unclear  
- Requires strong cross-functional alignment  

---

## How It Protects Engineering Time
- Engineering avoids exploring solutions that violate constraints  
- Guardrails reduce rework caused by misaligned expectations  
- Estimates are more accurate because constraints are known upfront  
- Discovery spikes are targeted and justified  

---

## How It Fits a 2-Week Sprint Cadence
- Intake validation: 1–2 days  
- Guardrail definition: 2–4 days  
- Solution exploration: 1–2 days  
- Feasibility snapshot: 1–2 days  

Typically fits within **one sprint**, but guardrail-heavy initiatives may span two.

---

## How It Differs from Design Thinking
- No ideation loops or divergent exploration  
- Focuses on constraints, not creativity  
- Guardrails replace open-ended brainstorming  
- Designed to reduce variability, not generate ideas  

---

## How It Handles “Kick the Can” Decisions
- Missing guardrails directly increase risk  
- Decision debt is explicitly tracked in the guardrail sheet  
- Product and Engineering must accept risk before proceeding  
- Backlog entry requires acknowledgment of unresolved constraints  

---

## Summary
A constraint-first planning workflow that establishes non-negotiable guardrails early, ensuring alignment, reducing scope creep, and protecting engineering from misaligned or inconsistent solution directions.