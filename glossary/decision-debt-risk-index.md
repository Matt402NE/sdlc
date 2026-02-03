# Decision Debt Risk Index (DDRI)

## Definition
The **Decision Debt Risk Index (DDRI)** is a semi‑quantitative scoring model that measures the risk created by **unresolved decisions** during SDLC planning.  It evaluates how missing business, product, technical, architectural, dependency, and compliance decisions increase volatility, uncertainty, and delivery risk.

This index provides a clear, color‑coded signal (Green/Yellow/Red) to visualize the risk level.
## How It Thinks / Behaves
- Missing decisions create measurable risk
- Each decision category contributes differently to volatility
- High‑impact decisions (technical, architectural, compliance) carry heavier weight
- Risk is transparent, owned, and must be explicitly accepted
- Decision debt is treated as a first‑class planning artifact

---
## Purpose
The DDRI exists to **quantify ambiguity** and make decision debt visible before work enters the backlog.  It ensures that Product, Business, and Engineering understand the risk created by missing decisions and agree on whether the request is ready to proceed.

Within the planning stage of the SDLC, DDRI:

- Identifies and categorizes unresolved decisions
- Assigns weighted risk to each category
- Produces a single, interpretable risk score
- Maps the score to a RAG threshold (Green/Yellow/Red)
- Requires explicit acceptance of high-risk items
- Protects Engineering from inheriting unstable or ambiguous work
- Helps Product determine backlog readiness

---
## Responsibilities / Components
- Track unresolved decisions across six categories  
- Apply weighted scoring to each decision type
- Calculate the total DDRI score
- Interpret the score using RAG thresholds
- Require explicit acceptance for high-risk items
- Support planning gates and backlog entry decisions

---

## DDRI Scoring Model

### Weighted Categories
Each decision unresolved by its due date adds weighted risk:

| Category | Weight | Meaning |
|----------|--------|---------|
| Business decision missing | +2 | Value or priority unclear |
| Product decision missing | +2 | Scope or success metrics unclear |
| Technical decision missing | +3 | High volatility |
| Architectural decision missing | +3 | Long-term sustainability risk |
| Dependency decision missing | +2 | Scheduling risk |
| Compliance decision missing | +3 | Regulatory exposure |
### Risk Score Interpretation
- **0–5** → **Low (Green)**  
- **6–10** → **Moderate (Yellow)**  
- **11+** → **High (Red)**  

High-risk items require explicit acceptance from Business and Product before backlog entry.

---

# Comparison Matrix: DDRI vs. Industry Risk Frameworks

| Framework                                            | What It Measures                         | How It Scores                                      | Similarity to DDRI | Key Difference                                           |
| ---------------------------------------------------- | ---------------------------------------- | -------------------------------------------------- | ------------------ | -------------------------------------------------------- |
| **[FMEA](risk-fmea.md)**                             | Failure modes & effects                  | Severity × Occurrence × Detection                  | High               | FMEA is failure‑focused; DDRI is decision‑focused        |
| **[RAID Log](risk-raid.md)**                         | Risks, assumptions, issues, dependencies | Descriptive + RAG                                  | Medium             | RAID lacks weighted scoring and decision‑centric framing |
| **[SAFe ROAM](risk-roam.md)**                        | Program-level risks                      | Categorization (Resolved/Owned/Accepted/Mitigated) | Medium             | ROAM doesn’t quantify risk or weight categories          |
| **[PMBOK Qualitative Risk Analysis](risk-pmbok.md)** | Project risks                            | Probability × Impact + RAG                         | High               | PMBOK is event‑based; DDRI is decision‑based             |
| **[COSO ERM](risk-coso.md)**                         | Enterprise risk categories               | Weighted scoring + governance                      | Medium             | COSO is enterprise-level, not backlog-level              |

---
## Summary
The **Decision Debt Risk Index (DDRI)** is a structured, semi‑quantitative model that transforms ambiguity into measurable risk.  It blends the strengths of [FMEA](risk-fmea.md), [PMBOK](risk-pmbok.md), [ROAM](risk-roam.md), and [RAID](risk-raid.md)—but applies them to the unique challenge of **decision debt** in SDLC planning.  By quantifying missing decisions, DDRI protects teams from volatility, improves planning accuracy, and ensures that backlog items enter delivery with clarity and confidence.