# FMEA (Failure Modes & Effects Analysis)

## Definition
FMEA is a structured, bottom-up method for identifying how a system, process, or component might fail, analyzing the effects of each failure, and prioritizing which risks to address based on their impact and likelihood. It converts qualitative discussions about “what could go wrong” into a scored, ranked view of failure modes that can be systematically mitigated.

**How It Thinks / Behaves**
- Assumes things will fail and asks “where, how, and with what effect?” rather than “if.”  
- Focuses on the chain from root causes → failure modes → effects on customers, operations, and safety.  
- Uses simple scoring (e.g., severity, occurrence, detectability) to prioritize attention, not to create false precision.  
- Encourages cross-functional collaboration between design, engineering, operations, and quality.  

---
## Purpose
FMEA exists to proactively surface and prioritize potential failures before they occur, so teams can design controls, tests, and safeguards into the system rather than reacting to incidents after release. It provides a repeatable way to focus limited mitigation effort on the most critical risks, improving reliability, safety, and customer experience.

In an SDLC or planning context, FMEA informs design decisions, test planning, and rollout strategies by highlighting which parts of the system are most fragile and what failure effects are unacceptable. It can be used as an input to gates (e.g., design reviews, launch readiness) by checking whether high-risk failure modes have been identified, addressed, and—where appropriate—retested.

---
## Responsibilities / Components
- **Define scope and system boundaries:** Clarify which product, feature, process, or component is being analyzed and at what level of detail.  
- **Identify failure modes and effects:** For each step or component, list how it can fail, why it might fail (causes), and what happens if it does (effects).  
- **Score and prioritize risks:** Assign severity, occurrence, and detection ratings (or similar), derive a risk priority ranking, and focus on the highest-risk items.  
- **Plan and track actions:** Define mitigation or control actions, assign owners and due dates, and update scores after actions are implemented.  
- **Document and revisit:** Keep the FMEA as a living artifact that is updated when designs change, incidents occur, or new information emerges.  
