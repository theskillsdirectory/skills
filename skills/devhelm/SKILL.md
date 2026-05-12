---
name: devhelm
description: Monitor uptime, manage incidents, configure alerting, and query dependency status with DevHelm
version: 1.0.0
last_updated: 2026-05-12
compatible_agents:
  tested:
    - cursor
  untested:
    - claude
    - copilot
    - codex
categories:
  - devops
  - monitoring
job_roles:
  - devops-engineer
  - developer
  - product-manager
author: DevHelm
github: https://github.com/devhelmhq/skill
license: apache-2.0
---

## What this skill does

Enables AI coding agents to manage uptime monitoring, incident response, alerting, and dependency status tracking through DevHelm. The skill provides agents with the knowledge to use the DevHelm CLI, SDKs, MCP server, and Terraform provider to configure monitors, respond to incidents, set up alert channels, and query the status of third-party services your application depends on.

## When to use it

- You need to create or update uptime monitors for your web services, APIs, or infrastructure
- An incident has fired and you want to acknowledge, escalate, or resolve it from your editor
- You want to configure alert channels (Slack, email, webhooks, PagerDuty) for a workspace
- You need to check the current status of a third-party dependency (e.g. AWS, Stripe, GitHub)
- You are setting up monitoring-as-code with the DevHelm Terraform provider or CLI config files
- You want to query monitor history, uptime percentages, or response-time trends

## Trigger phrases

- "Create a monitor for my API endpoint"
- "Set up uptime monitoring for this service"
- "Check if AWS is having issues right now"
- "Show me all monitors that are currently down"
- "Acknowledge the open incident"
- "Add a Slack alert channel for critical incidents"
- "What's the uptime for my production API this month?"
- "Configure monitoring for this project with Terraform"
- "List all my monitors and their status"
- "Set up a status page for our service"

## Example

**User prompt:**
> Create an HTTP monitor that checks https://api.example.com/health every 60 seconds from US and EU regions, and alert me on Slack if it goes down.

**Agent response using DevHelm CLI:**
```bash
# Create the monitor
devhelm monitors create \
  --name "Production API Health" \
  --url "https://api.example.com/health" \
  --frequency 60 \
  --regions us-east,eu-west \
  --method GET \
  --expected-status 200

# Set up Slack alerting
devhelm alert-channels create \
  --type slack \
  --name "Engineering Alerts" \
  --webhook-url "$SLACK_WEBHOOK_URL"
```

**Agent response using Terraform:**
```hcl
resource "devhelm_monitor" "api_health" {
  name             = "Production API Health"
  url              = "https://api.example.com/health"
  frequency        = 60
  regions          = ["us-east", "eu-west"]
  method           = "GET"
  expected_status  = 200
}

resource "devhelm_alert_channel" "slack" {
  type        = "slack"
  name        = "Engineering Alerts"
  webhook_url = var.slack_webhook_url
}
```

## Tools and integrations

| Tool | Package | Install |
|------|---------|---------|
| CLI | `devhelm` | `npm install -g devhelm` |
| MCP Server | `devhelm-mcp-server` | `pip install devhelm-mcp-server` |
| Python SDK | `devhelm` | `pip install devhelm` |
| JS/TS SDK | `@devhelm/sdk` | `npm install @devhelm/sdk` |
| Terraform | `devhelm/devhelm` | Terraform Registry |
| GitHub Action | `devhelmhq/setup-devhelm` | GitHub Marketplace |

## Notes

- Authentication requires a DevHelm API token set via `DEVHELM_API_TOKEN` environment variable or `devhelm auth login`
- The CLI supports 73 commands across 15 resource topics including monitors, incidents, alert-channels, status-pages, and more
- The MCP server enables AI agents (Cursor, Claude Desktop) to interact with DevHelm directly through tool calls
- All tools follow the same REST API, so workflows are portable across CLI, SDK, Terraform, and MCP
- Free tier available at [devhelm.io](https://devhelm.io) — no credit card required to start monitoring
