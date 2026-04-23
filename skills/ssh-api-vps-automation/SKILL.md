---
name: ssh-api-vps-automation
description: Use SSH ~ Api to operate Linux VPSes through a structured HTTP/OpenAPI layer instead of raw SSH, including sessions, commands, files, setup, tunnels, and system operations.
version: 1.0.0
last_updated: 2026-04-22
compatible_agents:
  tested: []
  untested:
    - claude
    - copilot
    - cursor
    - vscode
    - codex
categories:
  - devops
  - development
job_roles:
  - devops-engineer
  - developer
author: Vibhek Soni
github: vibheksoni
license: mit
---

## What this skill does

This skill teaches an agent how to use SSH ~ Api as a structured Linux server automation layer. Instead of improvising over raw SSH, the agent fetches the OpenAPI spec, reads the guide, creates a session, stores `session_id`, uses the documented endpoint groups, and disconnects cleanly.

Repository:

- `https://github.com/vibheksoni/ssh-api`

## When to use it

Use this skill when you want an agent to work on a Linux VPS through a stable HTTP API for:

- command execution
- file upload and download
- system inspection
- service management
- distro-aware package installation
- SSH tunnels
- firewall operations

## Trigger phrases

- "Use SSH ~ Api to inspect this VPS"
- "Deploy these files through SSH ~ Api"
- "Diagnose this Linux server through the API"
- "Use the repo's OpenAPI SSH layer instead of raw SSH"

## Example

Typical workflow:

1. Fetch `http://HOST:PORT/openapi.json`
2. Read `SSH_API_GUIDE.md`
3. `POST /session/connect`
4. Store `session_id`
5. Use `command/*`, `file/*`, `system/*`, `setup/*`, `tunnel/*`, and `firewall/*`
6. `POST /session/disconnect/{session_id}`

## Notes

- Prefer structured API calls over inventing raw shell flows
- Detect the remote platform before distro-sensitive setup work
- Treat destructive routes and firewall changes as privileged actions
- `config.json` in the SSH ~ Api repo is local-only and should not be committed
