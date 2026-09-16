# PMX-Skills
Product Management AI Skills

## How to use these skills

These skills support the context-first workflow described in these articles:

1. [Agent-Driven Product Management: 101](https://medium.com/@peterskoett/agent-driven-product-management-101-f7d3e1da2719) - build a working context stack so an agent can reason across your product, goals, decisions, stakeholders, and active work.
2. [Agent-Driven Product Management: 201](https://medium.com/@peterskoett/agent-driven-product-management-201-01e54c6b92ed) - install common skills for generic work, create your own skills for recurring workflows, evaluate them, and keep the portfolio focused.

Start with useful context, add one skill for a recurring workflow, and automate only after that workflow works reliably. The bundled PM skills below provide reusable starting points; adapt them to your context and decision logic rather than treating their output as a substitute for judgment.

## Bundled PM skills

| Skill | Purpose |
|-------|---------|
| [first-principle-thinking](.agents/skills/first-principle-thinking/SKILL.md) | Challenge assumptions, identify fundamentals, and build a testable recommendation. |
| [ghost-writer](.agents/skills/ghost-writer/SKILL.md) | Learn a user's voice from their own writing, draft in context, and improve from corrections. |
| [weekly-prioritization](.agents/skills/weekly-prioritization/SKILL.md) | Reconcile goals, evidence, capacity, and active work into priority decisions. |
| [feedback-triage](.agents/skills/feedback-triage/SKILL.md) | Find customer needs and traceable themes, then propose proportionate actions. |
| [okr-coach](.agents/skills/okr-coach/SKILL.md) | Improve objectives and results, review measured progress, and gather confidence. |
| [business-review](.agents/skills/business-review/SKILL.md) | Connect outcomes, learning, risks, and next-period decisions in a review or deck outline. |
| [team-context-update](.agents/skills/team-context-update/SKILL.md) | Share relevant behind-the-scenes context without repeating the delivery board. |
| [knowledge-base-curator](.agents/skills/knowledge-base-curator/SKILL.md) | Bootstrap or maintain a source-backed Markdown wiki. |
| [decision-log](.agents/skills/decision-log/SKILL.md) | Capture established decisions in a wiki with rationale, consequences, and provenance. |
| [visualization-critique](.agents/skills/visualization-critique/SKILL.md) | Review charts for accuracy, clarity, accessibility, and evidential limits. |
| [product-planning-interview](.agents/skills/product-planning-interview/SKILL.md) | Elicit product needs, boundaries, risks, and success criteria before planning. |
| [html-artifacts](.agents/skills/html-artifacts/SKILL.md) | Build portable HTML reports, comparisons, decks, maps, and local interactive artifacts. |
| [discovering-pmx-companion-skills](.agents/skills/discovering-pmx-companion-skills/SKILL.md) | Recommend optional companion skills directly from their upstream maintainers. |

These skills live in `.agents/skills/` for project discovery. To use them elsewhere, copy the desired skill directory, including its references, into that project's `.agents/skills/` directory. In a compatible client, invoke `/first-principle-thinking` or `/ghost-writer`, or ask for the described task naturally.

The bundled workflow skills work independently from supplied context with optional integrations. No bundled skill requires a private repository or organization-specific service. Examples and evaluation scenarios are synthetic. Keep personal profiles, customer records, and actual business knowledge in an appropriate user-controlled workspace, not in this shared skill collection.

## Curated upstream skills

The plugin includes [`discovering-pmx-companion-skills`](.agents/skills/discovering-pmx-companion-skills/SKILL.md), a lightweight catalog containing the upstream links and direct install commands. It lets an agent recommend the optional companion skills after the plugin is loaded without copying those skills into this repository.

The linked skills remain in their original repositories and are not included in the `pmx-skills` plugin. Their maintainers remain the source of truth, and `gh skill update --all` can update installed copies from their recorded origins.

## Agent Plugin

The repository root is also a skills-only [Agent Plugins 1.0.0](https://agent-plugins.org/specification) package named `pmx-skills`. Its [plugin.json](plugin.json) manifest targets the portable standard.

```text
plugin.json
skills -> .agents/skills
.agents/skills/
└── <skill-name>/
    ├── SKILL.md
    ├── evals/
    └── references/  (where needed)
```

Load the **repository root** through an Agent Plugins-compatible client's local-directory plugin installation flow. The client must support the skills component type; installation commands, namespacing, and enablement are client-specific and not defined by the standard. Do not enable both the plugin and separately installed copies of the same skills unless the client handles duplicates.

The `skills` directory is a relative symbolic link to the existing `.agents/skills` source of truth. All targets and bundled resources stay inside the plugin root, as required by the specification. Edit skills in `.agents/skills/`; no generation or synchronization step is needed, and existing project skill discovery remains unchanged.

Clone or copy the **complete package**, including `.agents/skills`, with symlinks preserved. On systems or packaging tools without symlink support, materialize `skills/` as a real copy of `.agents/skills/` in a separate distribution directory, with `plugin.json` at that directory's root. Do not replace the tracked link with a second maintained copy. Copying only the manifest and the link leaves an incomplete package.

This plugin has no MCP servers, hooks, executable entry point, credentials, or client extensions. Loading the plugin does not authorize publishing files or accessing private accounts.

## Claude Code plugin

Claude Code uses its own plugin manifest and marketplace format. This repository provides both under `.claude-plugin/` while sharing the same root `skills/` directory as the portable Agent Plugin. No second copy of the skills is maintained.

Install it from the repository-hosted marketplace:

```bash
claude plugin marketplace add pskoett/pmx-skills
claude plugin install pmx-skills@pmx-skills
```

Claude Code exposes the bundled skills as `/pmx-skills:<skill-name>`. The catalog of optional upstream companions is `/pmx-skills:discovering-pmx-companion-skills`; those linked skills remain separate installs.

For local development, validate and load the repository root:

```bash
claude plugin validate .
claude --plugin-dir .
```

### Examples

- **First principles:** "We think we need a new onboarding tool. Challenge that assumption and suggest the smallest experiment that would tell us what to do."
- **Ghost writing:** "Here are three emails I wrote. Learn my voice, then draft a reply using the facts below."
- **Recalibration:** "This sounds too formal. Here is how I would write it. Update my email style to reflect this."

`ghost-writer` starts by requesting user-authored samples. It adapts within the conversation and can save a voice profile at a user-approved private location when asked. Personal samples and profiles do not belong in this shared repository. No personal identity, language, employer, or writing style is preconfigured.

### Starting a wiki

Use [PMX Context Frame Example](https://github.com/pskoett/pmx-context-frame-example) as the reference knowledge-base structure: maintained knowledge in `wiki/`, source evidence in `raw/`, unprocessed intake in `inbox/`, and generated outputs in `artifacts/`. Its wiki includes navigation, a dated change log, product context, decisions, and testable assumptions. It is a template with placeholders, not a populated product dataset. The skill describes and links to it; its files are not bundled here.

`knowledge-base-curator` includes its own bootstrap guidance. It first looks for an existing knowledge base in the selected workspace and reuses its conventions. If none exists, it confirms the destination and privacy expectations, then creates a minimal structure such as:

```text
wiki/
├── index.md
└── pilot-decision.md
```

Topic pages are created from actual source material, not empty templates. A `sources/` folder is optional and created only when retaining local source copies is authorized. No Obsidian, QMD, database, or pre-existing wiki is needed. The skill preserves sources, links claims to evidence, and avoids duplicate pages on repeated ingestion. Without file-writing access, it returns copyable Markdown instead of claiming it saved a wiki.

Grow toward the reference structure only as needed. If the workspace already uses `raw/` for evidence, reuse it instead of adding a duplicate `sources/` folder. Neither the example's agent runbook nor its full folder hierarchy is required.

### HTML artifacts

`html-artifacts` combines a single-file authoring workflow with a portable catalog of 19 PMX Canvas-inspired primitive types. It maps comparisons, timelines, maps, reports, decks, galleries, and local editors to native HTML/CSS/SVG—not Canvas runtime APIs. No specific branding, CDN, framework, or backend is required.

Example: "Turn these rollout options into an offline HTML decision one-pager with a comparison grid and milestone timeline. Check desktop, mobile, and print layouts. Do not publish it."

The skill includes guidance for evidence integrity, safe text rendering, keyboard interaction, print/no-JavaScript fallbacks, and actual export verification. Browser rendering checks apply to generated artifacts; the bundled evaluation prompts are scenarios to run, not pre-rendered templates or a claim that all primitive types have been browser-tested.

## License

The bundled collection is licensed under [MIT](LICENSE). Curated upstream skills retain their own licenses and are not part of this repository.
