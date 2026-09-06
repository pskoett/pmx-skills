# PMX-Skills
Product Management AI Skills

## Skills

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
| [visualization-critique](.agents/skills/visualization-critique/SKILL.md) | Review charts for accuracy, clarity, accessibility, and evidential limits. |
| [product-planning-interview](.agents/skills/product-planning-interview/SKILL.md) | Elicit product needs, boundaries, risks, and success criteria before planning. |

The skills live in `.agents/skills/` for project discovery. To use them elsewhere, copy the desired skill directory, including its references, into that project's `.agents/skills/` directory. In a compatible client, invoke `/first-principle-thinking` or `/ghost-writer`, or ask for the described task naturally.

Each skill works independently from supplied context. Integrations are optional; none requires a private repository, organization-specific service, or another skill. Examples and evaluation scenarios are synthetic. Keep personal profiles, customer records, and actual business knowledge in an appropriate user-controlled workspace, not in this shared skill collection.

### Examples

- **First principles:** "We think we need a new onboarding tool. Challenge that assumption and suggest the smallest experiment that would tell us what to do."
- **Ghost writing:** "Here are three emails I wrote. Learn my voice, then draft a reply using the facts below."
- **Recalibration:** "This sounds too formal. Here is how I would write it. Update my email style to reflect this."

`ghost-writer` starts by requesting user-authored samples. It adapts within the conversation and can save a voice profile at a user-approved private location when asked. Personal samples and profiles do not belong in this shared repository. No personal identity, language, employer, or writing style is preconfigured.

### Starting a wiki

`knowledge-base-curator` includes its own bootstrap guidance. It first looks for an existing knowledge base in the selected workspace and reuses its conventions. If none exists, it confirms the destination and privacy expectations, then creates a minimal structure such as:

```text
wiki/
├── index.md
└── pilot-decision.md
```

Topic pages are created from actual source material, not empty templates. A `sources/` folder is optional and created only when retaining local source copies is authorized. No Obsidian, QMD, database, or pre-existing wiki is needed. The skill preserves sources, links claims to evidence, and avoids duplicate pages on repeated ingestion. Without file-writing access, it returns copyable Markdown instead of claiming it saved a wiki.

## Design and checks

Created using Anthropic's [skill-creator guidance](https://github.com/anthropics/skills/tree/main/skills/skill-creator). `ghost-writer` generalizes an existing personal ghost skill's source-grounding, register selection, drafting, and editing workflow; its personal corpus and preset persona are intentionally excluded.

Each skill includes representative prompts and expected outcomes in `evals/evals.json`. These are regression scenarios for future skill runs, not a claim of benchmarked voice quality. Voice fidelity requires feedback from the person whose writing is being modeled.

Run file-writing evaluation scenarios only in disposable workspaces. For scenarios describing an existing wiki, provide synthetic index/topic/source fixtures matching the prompt before running the skill. Never use the skills repository or real private notes as an evaluation destination.

## Orb setup

Amp runs the executable `.agents/setup` when preparing an orb. It ensures Python 3 is available for lightweight validation, installing it only if missing. The skills themselves require no runtime dependencies, services, secrets, or resume hook.

To check the evaluation JSON syntax from the repository root:

```bash
for file in .agents/skills/*/evals/evals.json; do
  python3 -m json.tool "$file" > /dev/null || exit 1
done
```

This checks JSON syntax, not skill behavior or writing quality.
