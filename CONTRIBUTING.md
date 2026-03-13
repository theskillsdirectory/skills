# Contributing to theskills.directory

Thanks for contributing! Here's how to get your skill added.

## Quick Start

1. Fork this repo
2. Create a folder: `skills/your-skill-name/`
3. Add a `SKILL.md` file — use `template/SKILL.md` as your starting point
4. Open a pull request
5. Once reviewed and approved it goes live on theskills.directory

## Before You Submit

- [ ] Description is a **single line** — multi-line descriptions break YAML silently
- [ ] Tested on at least one agent
- [ ] Trigger phrases included
- [ ] No API keys or sensitive data in the skill
- [ ] License field included in frontmatter

## Folder Structure
```
skills/
  your-skill-name/
    SKILL.md          # Required
    README.md         # Optional — extra docs
    scripts/          # Optional — supporting scripts
```

## What Makes a Good Skill

- **Specific** — does one thing well rather than everything poorly
- **Tested** — you've actually used it and it works
- **Documented** — trigger phrases tell people exactly how to invoke it
- **Honest** — known issues help the community debug problems

## Review Process

All submissions are reviewed before publishing. We check:
- Quality of instructions
- YAML formatting
- No sensitive data
- Accurate compatibility claims

Turnaround is typically 24-48 hours.

## Questions?

Open an issue or post in Discussions.
```

4. Commit message: `Add contributing guide`
5. Click **Commit new file**

---

**After all three steps your repo structure looks like:**
```
theskillsdirectory/skills
├── README.md
├── CONTRIBUTING.md
├── template/
│   └── SKILL.md
└── skills/
    └── sql-query-optimiser/
        └── SKILL.md
