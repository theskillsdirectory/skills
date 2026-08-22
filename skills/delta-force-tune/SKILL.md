---
name: delta-force-tune
description: Windows system-layer frame-rate optimization for Delta Force (三角洲行动) driven by an AI agent — 22 reversible optimizations, health checks, and A/B auto-tuning, with no game-file or anti-cheat interaction.
version: 1.0.0
last_updated: 2026-08-22
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
author: jiaxindeyang
github: jiaxindeyang-a11y
license: mit
---

## What this skill does

Optimizes Windows system-layer settings for better Delta Force frame rates: power
plans, HAGS, game mode, background recording, MMCSS, network throttling, services,
and more. Every change is backed up before writing and can be fully restored. An
A/B experiment script compares candidate tuning groups against a measured baseline
and keeps or reverts them based on frame data.

The engine lives in the companion repository
https://github.com/jiaxindeyang-a11y/delta-force-tune (MIT, clean-room
implementation). This skill orchestrates it: the agent detects, explains, gets
consent, applies, and reports.

## When to use it

- User reports Delta Force stuttering, low FPS, frame drops, or asks for frame-rate optimization.
- User asks for Windows-level game optimization on Windows 10/11 and wants it reversible.
- User wants a data-driven A/B comparison of tuning groups.

## Trigger phrases

- "三角洲行动卡顿 / 掉帧 / 帧数低 / 画面优化 / 帧率优化"
- "Delta Force is stuttering / low FPS / optimize my frame rate"
- "帮我优化三角洲行动的帧率"

## Example

**User**: "游戏掉帧很严重，帮我优化一下三角洲行动"

**Agent**:
1. Runs `delta-optimizer.ps1 -Detect -Json` (read-only) and reports hardware, game
   path, and which of the 22 optimizations already apply.
2. Explains recommended items and side effects, then asks for explicit consent.
3. Runs `delta-optimizer.ps1 -Apply -Preset balanced -Force -Json` after consent.
4. Reports per-item ok/failed/skipped, which items need a reboot, and the backup
   location for restore.

## Notes

- Red lines: never modify game files, never inject into the game process, never
  touch anti-cheat, never disable virtualization, never do GPU model spoofing.
- Admin is required for ~14 of the 22 items; non-admin sessions fail loudly instead
  of silently succeeding.
- Every reversible change is backed up to `%LocalAppData%\DeltaOptimizer\backup`;
  restore with `-Restore`.
- A/B tuning needs Microsoft PresentMon and a fixed in-game scene (same
  map/quality/route); the tool never downloads or runs installers for you.
- No fixed FPS promises — results vary by hardware.
