---
name: first-principle-thinking
description: "Breaks problems down into evidence, assumptions, constraints, and causal mechanisms, then rebuilds testable solutions. Use when asked to think from first principles, challenge assumptions, rethink a strategy, diagnose a bottleneck, or decide between options when conventional wisdom is not enough."
---

# First-Principle Thinking

Reconstruct a solution from what is supported and what must hold, rather than inheriting the proposed solution or copying convention.

## Workflow

1. **Frame the decision.** State the problem without embedding a solution. Identify who needs what outcome, the success measure, time horizon, and consequences of being wrong. Ask only for missing information that would materially change the answer; otherwise state assumptions and proceed.
2. **Separate the evidence.** Distinguish observed facts, user-reported claims, assumptions, unknowns, and preferences. A stakeholder's confident assertion is not a verified fact. Cite supplied evidence or accessible sources when relevant; do not fabricate research. Label estimates and include units and ranges where useful.
3. **Find the fundamentals.** Decompose the problem into needs, inputs, resources, incentives, and causal mechanisms. Ask why a constraint exists until reaching an observable mechanism, a binding obligation, or an explicit value choice. Do not call an intuition a fundamental truth. Stop decomposing when it no longer changes the decision.
4. **Classify constraints.** Separate physical, legal, safety, contractual, and genuinely fixed resource limits from habits, implementation choices, and negotiable policies. Treat binding limits as binding unless an authorized change is established. Preferences are legitimate tradeoffs, not mistakes to eliminate.
5. **Challenge load-bearing assumptions.** Pick the few assumptions whose failure would change the recommendation. For each, state the evidence for it, plausible contrary evidence, and the cheapest way to check it. Seek an alternative explanation rather than arguing only for the user's diagnosis.
6. **Rebuild options.** Derive a small set of meaningfully different options from the fundamentals. Include the status quo or a minimal intervention as a baseline. Explain the mechanism by which each could improve the outcome. First principles can validate an existing solution; novelty is not the goal.
7. **Compare and choose.** Compare expected impact, cost, time, dependencies, risks, and reversibility against the same objective. Use rough calculations only where they clarify the choice; show inputs, units, and sensitivity to uncertain assumptions. Do not use invented scoring precision to hide uncertainty.
8. **Make it testable.** Recommend an option, state what would change your mind, and propose the smallest useful experiment. Specify an observable success threshold, a time box, and a stop or rollback condition. Proposing a test does not authorize executing it or changing external systems.

## Output

Scale the structure to the task. For a quick question, use a few paragraphs; for a consequential decision, use this brief:

- **Decision:** Problem, intended outcome, and recommendation.
- **What holds:** Supported facts and binding constraints, with sources where available.
- **What may not hold:** Load-bearing assumptions, unknowns, and contrary evidence.
- **Options:** Alternatives and their causal mechanisms, costs, and tradeoffs.
- **Next test:** Hypothesis, measurement, success threshold, time box, stop condition, and evidence that would reverse the recommendation.

Give a concise, checkable rationale, not a transcript of private deliberation. If evidence is insufficient to choose, say what remains unresolved and recommend information-gathering rather than pretend certainty.

## Example

User: "We need to hire more support agents because response times doubled. Think from first principles."

Reframe the objective as restoring an acceptable response time, not increasing headcount. Treat the reported increase as a claim to verify. Separate arrival volume, handling time, available coverage, routing, and backlog. Hiring helps a capacity deficit, but not necessarily misrouting or a few recurring defects. Compare added coverage with routing changes or removing a frequent contact cause. Recommend measuring demand and service capacity by interval before choosing; set an agreed response-time target and monitor resolution quality so a faster first reply does not merely move the queue elsewhere.
