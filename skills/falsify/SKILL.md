---
name: falsify
description: Installs a 5-stage scientific thinking protocol on AI agents — falsify first, then believe; evidence-graded conclusions, no verdict without a falsifiable hypothesis.
version: 1.0.0
last_updated: 2026-08-28
compatible_agents:
  tested:
    - claude
    - codex
  untested:
    - copilot
    - cursor
    - vscode
    - gemini
categories:
  - research
  - development
  - productivity
job_roles:
  - developer
  - data-analyst
  - researcher
  - product-manager
author: Baixing
github: 263311487-ux
twitter_x: ""
license: MIT
---

## What this skill does

falsify installs a 5-stage scientific thinking protocol on any AI agent: Axioms → Hypotheses → Adversarial → Verify → Converge. It stops agents from giving confident answers they cannot falsify, and grades every conclusion by evidence strength.

## When to use it

- Before an agent commits to a confident conclusion, design decision, or root-cause claim
- When a claim needs verification, red-teaming, or evidence grading
- For high-stakes or irreversible decisions where overconfidence is costly

## Trigger phrases

- "Verify this claim before concluding..."
- "What could falsify this hypothesis?"
- "Red-team this analysis..."
- "Is this conclusion evidence-graded?"

## Example

Instead of: "The slowdown is caused by the new caching layer."
falsify forces: hypothesis → falsification test → evidence grade → only then a verdict, with uncertainty explicitly labeled.

## Notes

- Single Markdown skill; installs via `npx falsify-skill` or `npx skills add 263311487-ux/falsify`
- Full source: https://github.com/263311487-ux/falsify (includes 28 eval cases and academic grounding)
- Distilled from 70+ community sources and cognitive-science/causal-inference literature
