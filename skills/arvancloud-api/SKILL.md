---
name: arvancloud-api
description: Operate ArvanCloud APIs, DNS records, Cloud Server/IaaS, Object Storage, VOD/Live, CDN/Security, and Let's Encrypt DNS-01 certificates via acme.sh dns_arvan.
version: 1.0.0
last_updated: 2026-09-12
compatible_agents:
  tested:
    - claude
    - cursor
  untested:
    - copilot
    - vscode
    - codex
categories:
  - development
  - devops
job_roles:
  - developer
  - devops-engineer
author: erfnzdeh
github: erfnzdeh
license: mit
---

## What this skill does

Teaches an agent how to drive ArvanCloud's product APIs correctly: DNS records, Cloud Server / IaaS, Object Storage, CDN/Security, VOD/Live, and Let's Encrypt wildcard certificates via acme.sh `dns_arvan`. Each product has its own base URL and (for Object Storage) a different auth scheme. This skill keeps those details from being guessed.

Canonical source: https://github.com/erfnzdeh/arvancloud-agent-skill

Install:

```bash
npx skills add erfnzdeh/arvancloud-agent-skill
```

## When to use it

Use this whenever someone needs to manage anything on ArvanCloud — listing, creating, updating or deleting DNS records, adding or inspecting domains, spinning up or listing cloud servers, checking quota or usage, working with buckets, or issuing and renewing certificates.

## Trigger phrases

- "List my ArvanCloud DNS records"
- "Create an A record on ArvanCloud"
- "Issue a Let's Encrypt wildcard with dns_arvan"
- "Spin up an ArvanCloud cloud server"
- "Create an ArvanCloud object storage bucket"
- "Check ArvanCloud quota / usage"
- Any task involving `napi.arvancloud.ir`, `ecc.{region}.arvancloudapis.ir`, `storage.arvanapis.ir`, or an `Apikey` authorization header

## Example

**User:** "Add an A record for `app.example.com` pointing at my new ArvanCloud server."

**Agent:** Resolves the API key env var, looks up the domain, finds or creates the server's public IP, then creates the DNS record through the CloudDNS API using the correct `Apikey` header.

## Notes

- Unofficial and community-maintained. Not affiliated with ArvanCloud.
- Never store API keys in the skill. Read them from an environment variable.
- Per-user state belongs in `~/.config/arvan/config.json`.
- Verify live OpenAPI specs before relying on endpoint counts or paths.
- Full instructions, IaaS notes, and DNS/TLS reference files live in the GitHub repo.
