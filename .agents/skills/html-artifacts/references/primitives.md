# Portable Artifact Primitives

Read when choosing or composing an artifact. This is original, renderer-independent guidance informed by PMX Canvas's HTML primitive taxonomy and an existing HTML-artifact workflow. It does not vendor templates, bridge code, branded styles, or personal examples.

The records below describe useful content, not a rigid schema. Omit fields that do not apply; label missing consequential facts instead of inventing them. Use one primary primitive and a few supporting blocks rather than putting every type on a page.

## Planning and decisions

| Primitive | Content to gather | Native structure and constraints |
|-----------|-------------------|----------------------------------|
| `choice-grid` | Options, common criteria, benefits, limitations, cost, evidence, recommendation | CSS Grid of `article` elements or a comparison table. Use consistent criteria and ordering so visual prominence does not disguise unequal evidence. Stack on small screens. |
| `plan-timeline` | Milestones, sequence, dependencies, state, risks, owners/dates if known | Ordered list with visible status text; SVG only when links or branches add meaning. Distinguish sequence from a time-proportional scale. Estimates and proposed dates remain labeled. |
| `triage-board` | Items, stable IDs, proposed buckets, rationale, original state | Labeled lists for Now/Next/Later/Cut or user-selected buckets. Provide buttons or selects to move items; drag-and-drop is optional, never the only method. Export the current complete state, including deferred/cut items. Local moves are not tracker updates. |

## Systems and engineering evidence

| Primitive | Content to gather | Native structure and constraints |
|-----------|-------------------|----------------------------------|
| `system-map` | Components, responsibilities, entry points, labeled relationships | Cards plus inline SVG connectors when necessary. Explain arrow direction and boundary meaning; include a textual relationship list. Do not imply a runtime topology that has not been inspected. |
| `flowchart` | Steps, decisions, branch conditions, failures, terminal states | Labeled SVG nodes/edges with a parallel readable step list. Decision branches need explicit conditions. Ensure narrow-screen access without shrinking text to illegibility. |
| `code-walkthrough` | Purpose, ordered call path, relevant files/lines, snippets, gotchas | Ordered sections, escaped `pre`/`code`, and optionally a system map. Preserve exact snippets; distinguish observed behavior from inferred intent. |
| `review-sheet` | Findings, severity, location, evidence, consequence, proposed fix | Findings grouped by importance, visible severity labels, short code/diff excerpts. Color supplements text. Distinguish actual test results from tests merely proposed. |
| `pr-writeup` | Motivation, before/after, file tour, review focus, tests, rollout | Structured article with sections and an evidence checklist. Link supplied references appropriately; don't turn local paths into fabricated remote URLs or mark unrun checks passed. |

## Visual design

| Primitive | Content to gather | Native structure and constraints |
|-----------|-------------------|----------------------------------|
| `design-sheet` | Directions, audience, rationale, palette, tokens, type samples | Swatch figures, specimen sections, token tables. Label intent and contrast limitations. Use original neutral samples unless the user supplies branding. |
| `component-gallery` | Variants, sizes, default/focus/disabled/error states, accessibility notes | Responsive contact sheet of native controls or component examples. Demo actions must not submit real data; distinguish a specimen from a functional control. |
| `interaction-prototype` | Task, initial state, controls, transition, constraints, open questions | A small live stage, labeled fieldsets, outputs, and explanatory notes. Use realistic synthetic starting state when no real data is supplied. Test transitions and reduced-motion behavior; label simulation clearly. |
| `illustration-set` | Figure purpose, caption, shapes, labels, source if applicable | `figure`, inline SVG with accessible name, and `figcaption`. Add per-figure SVG download only if needed. Avoid embedding proprietary assets or copying branding from unrelated examples. |

## Reports and narrative

| Primitive | Content to gather | Native structure and constraints |
|-----------|-------------------|----------------------------------|
| `status-report` | Reporting period, metrics with units/baselines, shipped/slipped work, risks, next steps | Article with metric `dl`, lists, and accessible tables/charts. Show measurement dates and distinguish output from outcome. Do not fill gaps with decorative statistics. |
| `incident-report` | Impact, known chronology, severity/status, cause evidence, mitigations, follow-ups | Metadata `dl`, chronological `ol`, escaped logs, action table. Use a consistent timezone or explicitly retain source offsets. Keep suspected causes separate from confirmed findings and avoid unnecessary sensitive log content. |
| `deck` | Audience, ordered slide claims, evidence, final decision or takeaway | Sections progressively enhanced with navigation. One main point per slide; short decks only when content warrants it. Preserve all sections in print and no-JS mode. |
| `presentation` | Deck content plus optional notes, fullscreen needs, progress | Deck plus explicit controls and accessible slide announcements. Notes remain part of the delivered file: do not put confidential material there. Fullscreen is an optional enhancement, not a requirement to read. |
| `explainer` | Central question, short answer, steps, examples, FAQ, glossary | Article, ordered sections, `details` for secondary material, `dl` for terminology. Do not hide the core explanation or caveats in disclosures. |

## Local editors

| Primitive | Content to gather | Native structure and constraints |
|-----------|-------------------|----------------------------------|
| `config-editor` | Initial values, allowed values, dependencies, validation, proposed changes | Native form with labels and inline errors, original/current comparison, and JSON or text-diff export. Never apply a configuration to an external system unless separately authorized and implemented. Reject invalid combinations before export or clearly label the export invalid. |
| `prompt-tuner` | Template, variable names, sample inputs, substitution rules | Textarea, labeled inputs, safe text preview, and copy/download. Substitute placeholders without evaluating code or executing the prompt. Show unresolved variables rather than silently dropping them. Preserve literal input safely. |

## Compose from smaller blocks

- **Context header:** Title, purpose, period, and status. Not a forced brand banner.
- **Metric:** Value + unit + definition + comparison + source/date. Unknown is not zero.
- **Evidence figure:** Graphic + caption + source + accessible data or explanation.
- **Decision:** Options, recommendation, rationale, risk, and approval state.
- **Disclosure:** Secondary detail behind a native `details` element; essential content remains visible and prints.
- **Action/export:** Specific label, real effect, success or error feedback, and persistence limits.

## Runtime boundary

Do not emit PMX-specific tool calls, schema commands, iframe bridges, runtime metadata, agent work queues, or assumed host events into a standalone file. DOM events and in-memory state are sufficient for local interactions. If the user explicitly requests embedding in a live Canvas application, inspect that host's current authoritative schema separately; this portable catalog is not an API reference or version guarantee.
