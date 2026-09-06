# Sample-Based Voice Guide

Use this during onboarding, when a new register appears, or when the user corrects the voice. No preset voice is assumed.

## Extract patterns

For each user-authored sample, note an identifier, language, audience, format, and whether the user considers it representative. Exclude other people's text and boilerplate. Examine:

| Dimension | What to observe |
|-----------|-----------------|
| Rhythm | Sentence lengths and variation, fragments, paragraph lengths |
| Diction | Plain or technical language, recurring vocabulary, contractions |
| Tone | Directness, warmth, formality, humor, how uncertainty is expressed |
| Structure | Where the point appears, narrative versus lists, transitions |
| Mechanics | Capitalization, punctuation, headings, emphasis, emoji |
| Open and close | Greetings, hooks, signoffs, summaries, actual asks |
| Evidence | Examples, citations, numbers, explanation and qualification |
| Context | Differences between replies and new messages, public and private writing |

Pair each inferred rule with supporting sample IDs, scope, observed frequency, and confidence (tentative or well-supported). Do not invent exact corpus statistics from a few excerpts. Avoid reproducing typos deliberately; distinguish informal mechanics from accidental errors and ask if that distinction matters.

Do not automatically ban em dashes, formality, long sentences, greetings, lists, or calls to action. These are user-specific choices. Preserve deliberate features even when they differ from generic writing advice.

## Private profile template

```markdown
# Voice Profile

## Calibration
- Status: provisional / user-confirmed
- Last user-confirmed update:
- Sample IDs and contexts (no raw text by default):
- Missing contexts:

## General preferences
- Rule | evidence or explicit preference | confidence | frequency

## Registers
### [Format / audience / language]
- Rhythm and typical length:
- Vocabulary and tone:
- Structure, opening, and closing:
- Formatting and punctuation:
- Patterns to avoid or use sparingly:
- Evidence and confidence:

## Corrections
- Previous rule → replacement | scope | user confirmation

## Open questions
- Unresolved or conflicting evidence:
```

Only save this at a user-approved private destination. On a later session, load the user-selected profile and check whether it still applies. A profile is editable evidence, not an immutable identity.

## Calibration example (synthetic)

Samples: "The test failed. We’ll retry tomorrow." and "I’ve moved the review to Friday. Please send comments before then."

Reasonable provisional observations: direct status first; short sentences; concrete next steps in coordination messages. Unsupported conclusions: the user never uses humor, writes articles this way, dislikes all greetings, or holds a particular business philosophy.

If the user changes "Please provide your feedback by Friday" to "Send me your notes by Friday", propose plainer request language for this register. Do not conclude that every message needs a deadline.
