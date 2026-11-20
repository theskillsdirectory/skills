---
name: algorover-research
description: Discover AlgoRover Research strategies, preview and run historical backtests, inspect or cancel tasks, and retrieve research reports through a hosted MCP service.
version: 1.0.0
last_updated: 2026-11-19
compatible_agents:
  tested:
    - cursor
  untested:
    - claude
    - copilot
    - vscode
    - codex
categories:
  - research
  - data-analysis
job_roles:
  - researcher
  - data-analyst
author: AlgoRover / Rivendell Holdings Investment Limited
github: algorover
license: apache-2.0
---

# AlgoRover Research

## Connection and permissions

Use this skill for historical strategy discovery, backtest preparation, personal research tasks, and reports. Configure the host's remote Streamable HTTP MCP connection separately at `https://research.algorover.ai/mcp`, named `algorover-research`.

For Cursor, add the following entry to the client's MCP configuration using its normal settings interface:

```json
{"mcpServers":{"algorover-research":{"url":"https://research.algorover.ai/mcp"}}}
```

Public discovery and preparation are anonymous. Personal runs and reports require an AlgoRover account and browser OAuth with `research:read` and `research:run`. Use the client's authorization interface; credentials belong in the browser, never in chat. Installing this file alone does not establish a connection.

## Trigger phrases

- "Use AlgoRover Research to find historical strategies and show their presets."
- "Prepare a supported 90-day backtest and show me the configuration."
- "Show the report for my completed Research task."
- "Cancel my selected active Research task."

## Workflow

1. Call `search_strategies` with `locale: "zh-CN"` for Chinese and `locale: "en"` for other languages. Preserve that locale in later tools that accept it. Use the returned reference with `get_strategy` for strategy details.
2. Use only versions, presets and markets returned by the service. If preparation is `not_requested`, call `prepare_strategy` and check `get_strategy` at least three seconds apart until ready. Report the returned reason if preparation fails.
3. Call `prepare_backtest` for the selected preset, venue and supported 90- or 365-day window. Present the exact configuration and obtain confirmation before starting.
4. Call `start_backtest` using the returned `prepared_input`, `preparation_ticket` and `request_key` as `idempotency_key`. Reuse that key if retrying an uncertain start. Preserve the actual task identifier.
5. Use `get_backtest` for progress, `get_backtest_result` for completed metrics and `get_backtest_report_download` for requested reports. Use `list_backtests` when the task identifier is unknown. Show actual returned data and links. Preserve the returned report filename; append a numeric suffix before `.zip` if a file already exists.
6. Cancel only the selected active task with `cancel_backtest`, then verify `status: cancelled` using `get_backtest`. Report pending cancellation as pending.

If authorization fails, use the host's reconnect action and resume after the host confirms the connection. Report service errors without inventing results or substituting a local backtest engine. Delete a selected result only on an explicit request. Deleting all Research data requires a separate explicit request, additional authorization and the service's confirmation value.

## Example

For "Prepare a supported 90-day backtest", discover a strategy, inspect its returned presets, prepare the selected configuration and show it to the user. Start a task only after confirmation. Report the returned task ID and later status rather than assuming completion.

## Validation scope and limitations

The Cursor entry under `tested` refers to publisher validation of its native remote MCP connection and discovery of 16 tools. The complete Skill-driven OAuth and backtest workflow in Cursor has not been validated. Other clients are marked untested for this contribution. Separate publisher tests with the official MCP SDK confirmed public strategy queries; Docker's standalone OAuth flow confirmed authorization and three personal endpoints. These are distinct tests, not end-to-end certification for this skill.

Research performs historical analysis only, with no exchange-account connection, trading orders, wallets or deposits. Available strategies and presets depend on the service response. Historical results do not establish future returns. Client model/API charges may apply.

This contribution licenses this instruction document under Apache-2.0. The hosted service, its source code and other assets are outside that license.

- Public documentation: https://github.com/algorover/algorover-research
- Original Skill: https://github.com/algorover/algorover-research-skills
- Support: https://www.algorover.ai/en/help/
- Privacy: https://www.algorover.ai/privacy/
- Service terms: https://www.algorover.ai/terms/
