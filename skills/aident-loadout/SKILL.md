---
# ⚠️ IMPORTANT: Keep description on ONE line only — multi-line breaks the skill silently with no error
name: aident-loadout
description: Connect AI agents to 1,000+ apps and 400+ Skills via Aident Loadout MCP so they can run real workflows across Gmail, Slack, Notion, Linear, and more
version: 1.0.0
last_updated: 2026-10-12
compatible_agents:
  tested:
    - claude
    - cursor
    - codex
  untested:
    - copilot
    - vscode
categories:
  - development
  - productivity
job_roles:
  - developer
author: Aident AI
github: ljhskyso
license: MIT
---

## What this skill does

Gives AI agents a managed way to discover and use Aident Loadout — connect to 1,000+ apps and 400+ Skills (Gmail, Slack, Linear, Notion, Firecrawl, Fal, and more), execute actions with live schemas, and keep audit history. Product site: https://aident.ai. Source skill package: https://github.com/Aident-AI/aident-skill. MCP endpoint: https://loadout.aident.ai/mcp.

## When to use it

- You want an agent to work across real apps (email, chat, docs, tickets, research tools) through one Loadout connection
- You need MCP-based app access for Claude, Cursor, or Codex
- You are setting up or updating Aident Loadout in an agent environment

## Trigger phrases

- "Set up Aident Loadout"
- "Connect my agent to Gmail / Slack / Notion via Loadout"
- "Add the Aident MCP server"
- "Follow https://aident.ai/SETUP.md"
- "Help me use Aident Loadout skills"

## Example

**User:** Set up Aident Loadout for this agent.

**Agent:** Follows https://aident.ai/SETUP.md (or adds MCP with `claude mcp add --transport http aident https://loadout.aident.ai/mcp`), then uses the installed aident-skill for day-to-day Loadout usage across connected apps.

## Notes

- Setup: Follow https://aident.ai/SETUP.md, or run `claude mcp add --transport http aident https://loadout.aident.ai/mcp`.
- Website: https://aident.ai — sign up there for Loadout access and credits.
- Keep credentials in Aident Vault; do not put API keys in this skill file.
- License of the published skill package is MIT (matches this submission).
