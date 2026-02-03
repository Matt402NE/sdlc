# Workflow 1 — Lightweight Product-Led Intake Gate  
*A minimal-ceremony workflow that filters out unclear or low-value requests before they reach engineering.*

---

## Overview
This workflow creates a **lightweight intake gate** owned primarily by [Product](product.md).  
It emphasizes clarity, business value, and success criteria without requiring heavy documentation.  
Engineering is only pulled in for a **t‑shirt estimate** once the request is sufficiently shaped.

---

## When to Use
- Teams that want to stay agile and avoid upfront over‑design  
- Organizations where business partners frequently submit ideas of varying quality  
- Environments where engineering time is scarce and must be protected  
- Early-stage or fast-moving teams that want structure without bureaucracy

---

## Required Artifacts (All Lightweight)
1. **One-Page Intake Brief** (business-owned)
   - Problem statement  
   - Target users  
   - Success criteria (qualitative or quantitative)  
   - Business value narrative  
   - Budget guardrail (if known)  
   - Dependencies or constraints (if known)

2. **Product Readiness Checklist** (product-owned)
   - Is the problem clearly defined?  
   - Is success measurable?  
   - Is the scope small enough for a t-shirt estimate?  
   - Are there any obvious blockers?

3. **Engineering T-Shirt Estimate** (engineering-owned)
   - XS / S / M / L / XL  
   - Confidence level (High / Medium / Low)

---

## Decision Gates
### Gate 1 — Intake Completeness  
**Decision Required:** Is the one-page brief complete enough to evaluate?  
- If **yes** → Product Review  
- If **no** → Returned to business with specific gaps  
- If **decision cannot be made** → Risk +1 (Ambiguity)

### Gate 2 — Product Readiness  
**Decision Required:** Is the problem well-defined and aligned with strategy?  
- If **yes** → Engineering sizing  
- If **no** → Returned to business  
- If **decision cannot be made** → Risk +2 (Strategic misalignment)

### Gate 3 — Engineering Feasibility (High-Level)  
**Decision Required:** Can engineering provide a t-shirt estimate with current info?  
- If **yes** → Added to Product Backlog  
- If **no** → Requires a short discovery spike  
- If **decision cannot be made** → Risk +3 (Technical unknowns)

---

## Risk Model (Semi-Quantitative)
Each missing decision adds weighted risk:

| Category | Weight | Meaning |
|---------|--------|---------|
| Ambiguous problem | +1 | May cause rework later |
| Unclear success metrics | +2 | Hard to validate outcomes |
| Missing budget guardrail | +2 | Higher chance of overrun |
| Technical unknowns | +3 | Could expand scope significantly |
| Cross-team dependencies | +2 | Scheduling risk |

**Risk Score Interpretation**  
- **0–2** → Low risk (Green)  
- **3–5** → Moderate risk (Yellow)  
- **6+** → High risk (Red)  

High-risk items can still proceed, but Product must explicitly acknowledge the risk.

---

## Pros
- Very low ceremony  
- Fast turnaround  
- Protects engineering time  
- Encourages business clarity  
- Easy to adopt without cultural friction  

---

## Cons
- Limited depth may hide complexity  
- Risk scoring is approximate  
- Engineering may still need discovery spikes  
- Business may resist writing the intake brief  

---

## How It Protects Engineering Time
- Engineering only engages once Product validates clarity  
- No detailed design or PRD required  
- T-shirt sizing is intentionally shallow  
- Discovery spikes are time-boxed  

---

## How It Fits a 2-Week Sprint Cadence
- Intake brief review: 1–2 days  
- Product readiness review: 1–2 days  
- Engineering sizing: 1–2 days  
- Entire workflow fits comfortably inside a single sprint  

---

## How It Differs from Design Thinking
- No workshops or ideation loops  
- No prototyping required  
- Focuses on clarity and feasibility, not exploration  
- Designed to move quickly toward backlog readiness  

---

## How It Handles “Kick the Can” Decisions
- Missing decisions don’t block progress  
- Each missing decision increases the risk score  
- Product can choose to proceed with eyes open  
- Engineering can flag low-confidence estimates  

---

## Summary
A fast, low-ceremony intake workflow that ensures basic clarity, protects engineering time, and introduces a simple risk model without slowing down the organization.