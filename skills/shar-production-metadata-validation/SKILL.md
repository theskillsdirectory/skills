---
name: shar-production-metadata-validation
description: Validate rights-aware AI-hybrid video-production metadata before release using SHAR Production's local read-only MCP tool.
version: 1.0.0
last_updated: 2026-09-09
compatible_agents:
  tested:
    - codex
  untested:
    - claude
    - copilot
    - cursor
    - vscode
categories:
  - testing
  - documentation
job_roles:
  - developer
author: SHAR Production
github: SHARProduction
license: MIT
---

## What this skill does

This skill defines a safe, deterministic check for production manifests before delivery or release. It uses SHAR Production's local read-only MCP validator to check required metadata, URLs, language metadata, and production constraints. The validator returns a `releasable` boolean and an `errors` array; it never publishes content, changes files, accesses credentials, or makes network requests.

Source and installation: https://github.com/SHARProduction/production-metadata-mcp

## When to use it

Use this skill when a team needs a reproducible pre-release check for rights-aware AI-hybrid video-production metadata.

## Trigger phrases

- "Validate this production manifest before release"
- "Check whether this AI-hybrid production metadata is releasable"
- "Run a rights-aware metadata validation"

## Example

Clone the public source, install its dependencies, and configure the agent to launch `node /absolute/path/to/production-metadata-mcp/server.js`. Call `validate_production_manifest` with one `manifest` object and treat the returned `releasable` value as the deterministic technical check.

## Notes

A passing validation result is not legal advice, rights clearance, or permission to publish. Use only factual production metadata. The source is MIT licensed; the validator's functional test suite passed in the Codex environment on 2026-09-09.