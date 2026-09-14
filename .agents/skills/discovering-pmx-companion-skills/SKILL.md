---
name: discovering-pmx-companion-skills
description: Recommends optional upstream companion skills for PMX product-management work without copying or bundling them. Use when someone asks which additional skills to install for documents, research, knowledge management, design, media, MCP development, or PMX Canvas.
---

# Discovering PMX Companion Skills

Use this catalog to recommend optional skills that complement the bundled PMX workflows. These skills remain in their canonical upstream repositories and are not part of the `pmx-skills` plugin.

Recommend only skills relevant to the user's task. Link to the source so the user can review it before installation. Do not copy an upstream skill into this repository or imply that PMX maintains its version.

## Product and document work

| Skill | Purpose | Source | Install |
|-------|---------|--------|---------|
| `doc-coauthoring` | Structure collaborative documents, proposals, and specifications. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/doc-coauthoring) | `gh skill install anthropics/skills doc-coauthoring` |
| `docx` | Create, inspect, and edit Word documents. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/docx) | `gh skill install anthropics/skills docx` |
| `xlsx` | Create, inspect, and edit spreadsheets. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/xlsx) | `gh skill install anthropics/skills xlsx` |
| `pptx` | Create, inspect, and edit presentations. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/pptx) | `gh skill install anthropics/skills pptx` |
| `pdf` | Read, create, transform, and validate PDF files. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/pdf) | `gh skill install anthropics/skills pdf` |
| `frontend-design` | Produce intentional, distinctive interface designs. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/frontend-design) | `gh skill install anthropics/skills frontend-design` |
| `remotion-best-practices` | Apply current Remotion patterns when creating videos. | [`remotion-dev/skills`](https://github.com/remotion-dev/skills/tree/main/skills/remotion-best-practices) | `gh skill install remotion-dev/skills remotion-best-practices` |

## Research and knowledge management

| Skill | Purpose | Source | Install |
|-------|---------|--------|---------|
| `qmd` | Search local Markdown knowledge bases. | [`tobi/qmd`](https://github.com/tobi/qmd/tree/main/skills/qmd) | `gh skill install tobi/qmd qmd` |
| `obsidian-cli` | Work with Obsidian vaults through its CLI. | [`kepano/obsidian-skills`](https://github.com/kepano/obsidian-skills/tree/main/skills/obsidian-cli) | `gh skill install kepano/obsidian-skills obsidian-cli` |
| `obsidian-markdown` | Author Obsidian-flavored Markdown. | [`kepano/obsidian-skills`](https://github.com/kepano/obsidian-skills/tree/main/skills/obsidian-markdown) | `gh skill install kepano/obsidian-skills obsidian-markdown` |
| `obsidian-bases` | Create and edit Obsidian Bases. | [`kepano/obsidian-skills`](https://github.com/kepano/obsidian-skills/tree/main/skills/obsidian-bases) | `gh skill install kepano/obsidian-skills obsidian-bases` |
| `json-canvas` | Create and edit JSON Canvas files. | [`kepano/obsidian-skills`](https://github.com/kepano/obsidian-skills/tree/main/skills/json-canvas) | `gh skill install kepano/obsidian-skills json-canvas` |
| `defuddle` | Extract clean Markdown from web pages. | [`kepano/obsidian-skills`](https://github.com/kepano/obsidian-skills/tree/main/skills/defuddle) | `gh skill install kepano/obsidian-skills defuddle` |

## Agent tooling and spatial work

| Skill | Purpose | Source | Install |
|-------|---------|--------|---------|
| `skill-creator` | Create and improve agent skills. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/skill-creator) | `gh skill install anthropics/skills skill-creator` |
| `mcp-builder` | Design and build MCP servers. | [`anthropics/skills`](https://github.com/anthropics/skills/tree/main/skills/mcp-builder) | `gh skill install anthropics/skills mcp-builder` |
| `self-improvement` | Capture corrections and reusable learnings. | [`pskoett/pskoett-ai-skills`](https://github.com/pskoett/pskoett-ai-skills/tree/main/skills/self-improvement) | `gh skill install pskoett/pskoett-ai-skills self-improvement` |
| `pmx-canvas` | Operate the PMX Canvas spatial workbench. | [`pskoett/pmx-canvas`](https://github.com/pskoett/pmx-canvas/tree/main/skills/pmx-canvas) | `gh skill install pskoett/pmx-canvas pmx-canvas` |

## Installation guidance

- Add `--scope user` to make a skill available across GitHub Copilot projects.
- Review the upstream `SKILL.md`, scripts, MCP commands, and license before installing.
- Use `gh skill update --all` to update installed upstream skills from their recorded origins.
- If `gh skill` is unavailable, update GitHub CLI to a release that supports Agent Skills.
