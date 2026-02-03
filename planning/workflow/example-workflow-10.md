

# Workflow 10 — Decision‑Debt–Driven Workflow  
*A workflow where the primary goal is to identify, quantify, and resolve decision debt before any shaping, estimation, or backlog entry occurs. Every step revolves around clarifying who owes which decisions and by when.*

---
## Overview
This workflow treats **decision debt** as the central organizing principle.  
Instead of focusing first on value, feasibility, or scope, the team begins by identifying all missing decisions—business, product, technical, compliance, dependency, and strategic.  
Each missing decision is assigned an owner, a due date, and a risk weight.  
Only once decision debt is reduced to an acceptable level does the team proceed to shaping or estimation.

This workflow is ideal for organizations where ambiguity, unclear ownership, or slow decision-making frequently derail delivery.

---
## When to Use
- Teams that struggle with unclear or slow decision-making  
- Organizations with many stakeholders or cross-team dependencies  
- Environments where ambiguity repeatedly causes rework  
- Initiatives with high strategic or architectural impact  
- Teams wanting to make decision ownership explicit and enforceable  

---
## Required Artifacts
1. **Decision Debt Register** (cross-functional)  
   - List of all missing decisions  
   - Decision owners  
   - Due dates  
   - Risk weights  
   - Impact of delay  
   - Dependencies  

2. **Decision Clarification Brief** (product-owned)  
   - Problem statement  
   - Success metrics  
   - Known decisions  
   - Unknown decisions  
   - Stakeholder map  

3. **Engineering Technical Decision Map** (engineering-owned)  
   - Technical unknowns  
   - Architectural decisions required  
   - Integration decisions  
   - Feasibility blockers  

4. **Decision Resolution Summary** (cross-functional)  
   - Resolved decisions  
   - Remaining decision debt  
   - Updated risk score  
   - Go/No-Go recommendation  

---
## Decision Gates
### Gate 1 — Decision Debt Identification  
**Decision Required:** Have all missing decisions been identified?  
- Yes → Decision Ownership Assignment  
- No → Continue identification  
- Cannot decide → Risk +2 (Ambiguity)

### Gate 2 — Decision Ownership Assignment  
**Decision Required:** Does every decision have a clear owner and due date?  
- Yes → Decision Resolution Cycle  
- No → Assign owners  
- Cannot decide → Risk +3 (Ownership uncertainty)

### Gate 3 — Decision Resolution Cycle  
**Decision Required:** Has decision debt been reduced to an acceptable level?  
- Yes → Engineering Feasibility  
- No → Continue resolution  
- Cannot decide → Risk +3 (Strategic uncertainty)

### Gate 4 — Engineering Feasibility  
**Decision Required:** Can engineering estimate based on the resolved decisions?  
- Yes → Backlog Readiness  
- No → Discovery spike required  
- Cannot decide → Risk +3 (Technical unknowns)

---
## Risk Model (Semi-Quantitative)
Each unresolved decision adds weighted risk:

| Category | Weight | Meaning |
|----------|--------|---------|
| Business decision missing | +2 | Value or priority unclear |
| Product decision missing | +2 | Scope or success metrics unclear |
| Technical decision missing | +3 | High volatility |
| Architectural decision missing | +3 | Long-term sustainability risk |
| Dependency decision missing | +2 | Scheduling risk |
| Compliance decision missing | +3 | Regulatory exposure |

**Risk Score Interpretation**  
- **0–5** → Low (Green)  
- **6–10** → Moderate (Yellow)  
- **11+** → High (Red)  

High-risk items require explicit acceptance from Business and Product before backlog entry.

---
## Pros
- Makes decision debt visible and actionable  
- Forces clarity and ownership early  
- Reduces rework caused by late decisions  
- Encourages cross-functional accountability  
- Ideal for complex or multi-stakeholder environments  

---
## Cons
- Requires strong discipline and transparency  
- May feel bureaucratic to teams unused to explicit decision tracking  
- Can slow intake if stakeholders delay decisions  
- Requires a culture that supports accountability  

---
## How It Protects Engineering Time
- Engineering does not estimate until decision debt is reduced  
- Technical unknowns are explicitly tracked and resolved  
- Prevents engineering from inheriting ambiguous or unstable requests  
- Reduces rework caused by shifting decisions  

---
## How It Fits a 2-Week Sprint Cadence
- Decision identification: 1–2 days  
- Ownership assignment: 1 day  
- Resolution cycle: 3–5 days  
- Feasibility snapshot: 1–2 days  

Fits within **one sprint**, though high-debt initiatives may span two.

---
## How It Differs from Design Thinking
- No ideation or prototyping  
- Focuses on decision clarity, not creativity  
- Uses decision registers instead of user research artifacts  
- Designed to reduce ambiguity, not explore possibilities  

---
## How It Handles “Kick the Can” Decisions
- Every deferred decision increases risk  
- Decision debt is tracked explicitly with owners and deadlines  
- Backlog entry requires acknowledgment of unresolved decisions  
- High-debt items cannot proceed without explicit acceptance  

---
## Summary
A decision‑debt–driven workflow that forces clarity, ownership, and accountability before shaping or estimation—ideal for complex environments where missing decisions repeatedly derail delivery.