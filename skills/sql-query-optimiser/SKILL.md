---
# ⚠️ IMPORTANT: Keep description on ONE line only — multi-line breaks the skill silently with no error
name: sql-query-optimiser
description: Analyses and optimises SQL queries for performance, readability and production safety
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
  - data-analysis
job_roles:
  - developer
  - data-analyst
author: theskillsdirectory
github: theskillsdirectory
twitter_x: skillsdirectory
license: apache-2.0
---

## What this skill does

Reviews SQL queries and suggests improvements for performance, readability, and safety. Identifies common issues like missing indexes, N+1 patterns, unoptimised joins, and queries that could cause problems in production.

## When to use it

- You've written a query and want a second opinion before running it in production
- A query is running slowly and you need to diagnose why
- You want your SQL reformatted to a consistent style
- You're learning SQL and want explained improvements

## Trigger phrases

- "Optimise this SQL query"
- "Review my SQL"
- "Why is this query slow?"
- "Rewrite this query to be more efficient"
- "Check this SQL before I run it in production"

## Example

**Before:**
```sql
