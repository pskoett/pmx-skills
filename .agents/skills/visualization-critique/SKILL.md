---
name: visualization-critique
description: "Critiques charts, dashboards, and data graphics for integrity, clarity, accessibility, and evidential limits. Use when asked to review, audit, improve, or compare a visualization or visualization plan."
---

# Visualization Critique

Evaluate whether a visualization communicates the available evidence accurately and efficiently, then propose concrete improvements.

## Workflow

1. **Establish the job.** Identify the intended audience, decision or question, medium, and supplied data. Reuse answers already provided. If a missing artifact or context blocks a useful review, ask only for that item; otherwise state assumptions and proceed.
2. **Check graphical integrity.** Inspect scales, baselines, intervals, units, denominators, sorting, aggregation, encodings, and transformations. Flag truncation or dual axes when they could distort comparison. Distinguish values shown from interpretations inferred.
3. **Test the form against the task.** Decide whether the chart supports comparison, trend, distribution, relationship, composition, or geography. Recommend small multiples when shared scales make groups easier to compare. Never claim correlation, sequence, or visual proximity establishes causality.
4. **Reduce friction.** Preserve useful ink and remove decoration that competes with data. Prefer direct labels where practical, remove redundant legends or repeated text, and check titles, annotations, label collisions, clipping, density, and reading order. Decoration is acceptable when it serves comprehension or audience needs.
5. **Review accessibility and uncertainty.** Check contrast, color-vision-safe distinctions, non-color cues, legible type, descriptive titles or alternatives, keyboard or screen-reader support for interactive work, and usable fallback tables when appropriate. Show uncertainty, missingness, sample size, estimates, and data limitations when material.
6. **Prioritize changes.** Separate correctness issues from comprehension issues and polish. Give specific changes, their rationale, and any tradeoff. Do not redesign merely for novelty.

Use available chart images, data, specifications, or selected external references when helpful, but no tool or source is required. Do not invent unseen data or defects.

## Expected Output

- **Purpose and evidence:** what the graphic appears to answer and what is actually supported.
- **Findings:** prioritized as misleading/correctness, comprehension, accessibility, and polish.
- **Recommended changes:** concrete edits tied to each important finding.
- **Limits:** missing evidence, uncertainty, and claims the chart cannot establish.

If the chart or underlying values are unavailable, provide a bounded review of the described design and request only the evidence needed for a stronger verdict.

## Synthetic Example

For a quarterly revenue bar chart whose vertical axis starts at 90, uses 3D columns, and colors regions red and green, note that the truncated scale exaggerates modest differences, perspective impairs length comparison, and color alone excludes some readers. Recommend a zero baseline for bars (or a clearly labeled dot plot if small differences matter), flat marks, direct values, and color-plus-shape or labels. If revenue rose alongside a campaign, describe association only; do not say the campaign caused the increase without causal evidence.

## Boundaries

- Critique communication and evidence; do not fabricate values, sources, user goals, or causal conclusions.
- Do not require a specific charting library, integration, or sibling skill.
- Preserve intentional style unless it harms accuracy, comprehension, or access.
- Do not silently edit or publish artifacts; provide guidance unless implementation is explicitly requested.
