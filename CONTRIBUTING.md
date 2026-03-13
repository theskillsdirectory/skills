# Contributing to theskills.directory

Thanks for contributing! This repo is the open source home for Agent Skills — reusable instruction sets for Claude, GitHub Copilot, Cursor, VS Code, and Codex.

---

## How to submit a skill

### Option 1 — Pull Request (recommended)

1. Fork this repository
2. Create a new folder inside `skills/` named after your skill (use kebab-case, e.g. `sql-query-optimiser`)
3. Copy the template from `template/SKILL.md` into your new folder
4. Fill in all fields — see the checklist below before submitting
5. Open a Pull Request

Your folder structure should look like this:
```
skills/
  your-skill-name/
    SKILL.md
```

### Option 2 — Web form

Submit at [theskills.directory/submit](https://theskills.directory/submit) and we'll handle the PR for you.

---

## Submission checklist

Before opening your PR, please confirm:

- [ ] Skill name uses kebab-case (e.g. `my-skill-name`)
- [ ] Description is a **single line** — multi-line breaks the skill silently
- [ ] At least one agent listed under `tested`
- [ ] Trigger phrases are included in the body
- [ ] No API keys, passwords, or sensitive data included
- [ ] `license` field is filled in
- [ ] `version` and `last_updated` fields are filled in
- [ ] This is my own work or properly attributed open source content
- [ ] I have the right to share this under the stated license

---

## Frontmatter field guide

| Field | Required | Notes |
|-------|----------|-------|
| `name` | ✅ | Kebab-case, matches folder name |
| `description` | ✅ | Single line only — no exceptions |
| `version` | ✅ | Start at `1.0.0` |
| `last_updated` | ✅ | Format: YYYY-MM-DD |
| `compatible_agents` | ✅ | Split into `tested` and `untested` |
| `categories` | ✅ | See list below |
| `job_roles` | ✅ | See list below |
| `author` | ✅ | Your name |
| `github` | ✅ | Your GitHub username |
| `twitter_x` | optional | Your X/Twitter handle |
| `license` | ✅ | We recommend `apache-2.0` |

---

## Available categories

`development` `writing` `data-analysis` `research` `design` `marketing` `education` `productivity` `devops` `security` `testing` `documentation`

## Available job roles

`developer` `designer` `marketer` `teacher` `student` `data-analyst` `product-manager` `writer` `devops-engineer` `researcher`

## Available agents

`claude` `copilot` `cursor` `vscode` `codex`

---

## Review process

1. A maintainer will review your PR within 48 hours
2. We may ask for changes if the frontmatter is incomplete or the skill is unclear
3. Once approved and merged, it will appear on theskills.directory automatically

---

## Questions?

Open a GitHub Discussion or reach out on X [@skillsdirectory](https://x.com/skillsdirectory)
