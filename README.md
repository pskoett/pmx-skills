# PMX-Skills
Product Management AI Skills

## Skills

| Skill | Purpose |
|-------|---------|
| [first-principle-thinking](.agents/skills/first-principle-thinking/SKILL.md) | Challenge assumptions, identify fundamentals, and build a testable recommendation. |
| [ghost-writer](.agents/skills/ghost-writer/SKILL.md) | Learn a user's voice from their own writing, draft in context, and improve from corrections. |

The skills live in `.agents/skills/` for project discovery. To use them elsewhere, copy the desired skill directory, including its references, into that project's `.agents/skills/` directory. In a compatible client, invoke `/first-principle-thinking` or `/ghost-writer`, or ask for the described task naturally.

### Examples

- **First principles:** "We think we need a new onboarding tool. Challenge that assumption and suggest the smallest experiment that would tell us what to do."
- **Ghost writing:** "Here are three emails I wrote. Learn my voice, then draft a reply using the facts below."
- **Recalibration:** "This sounds too formal. Here is how I would write it. Update my email style to reflect this."

`ghost-writer` starts by requesting user-authored samples. It adapts within the conversation and can save a voice profile at a user-approved private location when asked. Personal samples and profiles do not belong in this shared repository. No personal identity, language, employer, or writing style is preconfigured.

## Design and checks

Created using Anthropic's [skill-creator guidance](https://github.com/anthropics/skills/tree/main/skills/skill-creator). `ghost-writer` generalizes an existing personal ghost skill's source-grounding, register selection, drafting, and editing workflow; its personal corpus and preset persona are intentionally excluded.

Each skill includes representative prompts and expected outcomes in `evals/evals.json`. These are regression scenarios for future skill runs, not a claim of benchmarked voice quality. Voice fidelity requires feedback from the person whose writing is being modeled.
