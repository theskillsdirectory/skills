# theskills.directory

The community directory for Agent Skills — find, share and rate
skills for Claude, Copilot, Cursor, VS Code and Codex.

🌐 theskills.directory
⭐ Star this repo to stay updated

---

## What are Agent Skills?

Agent Skills are folders of instructions (SKILL.md files) that give 
AI agents specialised knowledge and repeatable workflows.

The same skill file works across multiple agents:

| Agent | Platform |
|-------|----------|
| Claude / Claude Code | Anthropic |
| GitHub Copilot | Microsoft / GitHub |
| VS Code | Microsoft |
| Cursor | Anysphere |
| OpenAI Codex | OpenAI |
| Vercel AI | Vercel |

The open standard specification lives at agentskills.io

---

## Submitting a Skill

### Option 1 — GitHub PR (developers)
1. Fork this repo
2. Create a folder: `skills/your-skill-name/`
3. Add a `SKILL.md` file following the template below
4. Open a pull request — it will appear in our admin review queue
5. Once approved it goes live on theskills.directory

### Option 2 — Web form (everyone)
Submit at theskills.directory/submit — no GitHub required

---

## SKILL.md Template
```yaml
---
name: your-skill-name
description: One single line description of what this skill does and when to use it
compatible_agents:
  - claude        # tested ✅ / untested ❓
  - copilot       # tested ✅ / untested ❓
  - cursor        # tested ✅ / untested ❓
  - vscode        # tested ✅ / untested ❓
  - codex         # tested ✅ / untested ❓
categories:
  - development   # What it does — see categories below
job_roles:
  - developer     # Who uses it — see roles below
author: Your Name
github: yourusername
x: yourhandle     # optional
license: apache-2.0
---

# Your Skill Name

[Your instructions here]

## Trigger Phrases
Exactly what to say to invoke this skill:
- "Use the [skill-name] skill to..."
- "[Specific phrase that reliably triggers it]"

## Examples
- Example usage 1
- Example usage 2

## Guidelines
- Guideline 1
- Guideline 2

## Known Issues
- Any platform-specific quirks
- Any known incompatibilities
```

---

## Categories

### What it does
| Slug | Description |
|------|-------------|
| `development` | General coding assistance |
| `testing` | Unit tests, QA, debugging |
| `code-review` | PR review, refactoring |
| `devops` | CI/CD, infrastructure, deployment |
| `data-analysis` | Data processing, SQL, visualisation |
| `writing` | Content creation, copywriting, editing |
| `research` | Web research, summarisation, analysis |
| `document-creation` | Word, PDF, PowerPoint, Excel |
| `productivity` | Task management, automation, scheduling |
| `education` | Teaching, lesson planning, marking |
| `design` | UI/UX, design systems, prototyping |
| `marketing` | SEO, campaigns, social media |

### Who uses it
| Slug | Role |
|------|------|
| `developer` | Software engineers |
| `teacher` | Teachers and educators |
| `marketer` | Marketing professionals |
| `researcher` | Academic or professional researchers |
| `founder` | Business owners and founders |
| `designer` | UI/UX and graphic designers |
| `hr` | HR and people operations |
| `legal` | Legal and compliance |
| `data-analyst` | Data analysts and scientists |

---

## Compatible Agents

| Slug | Platform | Notes |
|------|----------|-------|
| `claude` | Claude.ai | Upload via Settings > Features |
| `claude-code` | Claude Code CLI | Place in .claude/skills/ |
| `copilot` | GitHub Copilot | VS Code Chat Customisations |
| `vscode` | VS Code | Built-in skills support |
| `cursor` | Cursor | Agent mode skills |
| `codex` | OpenAI Codex | .agents/skills directory |

---

## Quality Standards

Before submitting please check:

- [ ] Description is a single line — multi-line breaks YAML silently
- [ ] Tested on at least one agent
- [ ] Trigger phrases included — exactly what to say to invoke it
- [ ] Known issues documented if any
- [ ] No sensitive data or API keys in the skill content
- [ ] License field included

---

## License

Skills in this repo are Apache 2.0 unless the author specifies 
otherwise in the frontmatter. By submitting you confirm you have 
the right to share the skill under the stated license.

---

## Community

- 🌐 Directory: theskills.directory
- 🐦 X: @skillsdirectory
- 💬 Discussions: github.com/theskillsdirectory/skills/discussions
- 🐛 Issues: github.com/theskillsdirectory/skills/issues
