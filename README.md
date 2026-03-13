# theskills.directory

The community directory for Agent Skills — find, share and rate skills for Claude, Copilot, Cursor, VS Code and Codex.

🌐 [theskills.directory](https://theskills.directory)

---

## What are Agent Skills?

Skills are folders of instructions (SKILL.md files) that give AI agents specialised knowledge and repeatable workflows. The same skill works across Claude, GitHub Copilot, VS Code, Cursor and OpenAI Codex.

---

## Submitting a Skill

### Option 1 — GitHub PR (developers)
1. Fork this repo
2. Create a folder: `skills/your-skill-name/`
3. Copy the template from `template/SKILL.md`
4. Fill in all fields and open a pull request

### Option 2 — Web form (everyone)
Submit at [theskills.directory/submit](https://theskills.directory/submit)

---

## SKILL.md Template
```yaml
---
# ⚠️ IMPORTANT: Keep description on ONE line only — multi-line breaks the skill silently
name: your-skill-name
description: One single line description of what this skill does and when to use it
version: 1.0.0
last_updated: 2026-03-13
compatible_agents:
  tested:
    - claude
  untested:
    - copilot
    - cursor
    - vscode
    - codex
categories:
  - development
job_roles:
  - developer
author: Your Name
github: your-github-username
twitter_x: your-x-handle
license: apache-2.0
---
```

---

## Required Fields

| Field | Description |
|-------|-------------|
| `name` | Unique identifier, lowercase, hyphens only |
| `description` | Single line only — this is what agents read to decide whether to load the skill |
| `version` | Start at `1.0.0`, increment when you update |
| `last_updated` | Format: YYYY-MM-DD |
| `compatible_agents` | Split into `tested` and `untested` (see template) |
| `categories` | See list below |
| `job_roles` | See list below |
| `author` | Your name |
| `github` | Your GitHub username |
| `twitter_x` | Your X handle (optional) |
| `license` | We recommend `apache-2.0` |

---

## Categories

`development` `writing` `data-analysis` `research` `design` `marketing` `education` `productivity` `devops` `security` `testing` `documentation`

## Job Roles

`developer` `designer` `marketer` `teacher` `student` `data-analyst` `product-manager` `writer` `devops-engineer` `researcher`

## Compatible Agents

`claude` `copilot` `cursor` `vscode` `codex`

---

## Quality Standards

- Description must be a **single line** — multi-line breaks YAML silently with no error message
- List agents under `tested` only if you have actually tested on that platform
- Include trigger phrases — exactly what to say to invoke the skill
- No API keys, passwords, or sensitive data
- Note any known limitations or platform-specific behaviour

---

## License

Apache 2.0 — skills you submit are open source and free to use across all platforms.

---

## Community

- 🌐 [theskills.directory](https://theskills.directory)
- 𝕏 [@skillsdirectory](https://x.com/skillsdirectory)
- Submit a skill: [theskills.directory/submit](https://theskills.directory/submit)
