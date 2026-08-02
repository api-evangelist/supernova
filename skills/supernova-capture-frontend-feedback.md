---
name: Capture frontend feedback
description: >-
  Collect design-system friction points during frontend development — missing
  context, conflicts, reformulations, and corrections — and send them back to
  Supernova so the design system's AI context improves over time.
api: mcp/supernova-mcp.yml
operations:
  - sn_collect_agent_feedback
method: searched
source: https://github.com/Supernova-Studio/agent-skills
license: MIT
install: npx skills add supernova-studio/agent-skills --skill capture-frontend-feedback
---

# Capture frontend feedback

This is Supernova's officially published Agent Skill (from
`supernova-studio/agent-skills`). It is captured here verbatim in intent; install the
canonical version with `npx skills add supernova-studio/agent-skills --skill capture-frontend-feedback`.

## Purpose

While an AI agent builds frontend code against a Supernova-managed design system, it
inevitably hits friction: a token or component it cannot find, guidance that conflicts,
a prompt it had to reformulate, or an output a human corrected. This skill captures
those signals and returns them to Supernova, closing the feedback loop so the design
system's AI context gets sharper on the next run.

## Requirements

- Feedback collection must be enabled in your Supernova **Context**.
- Access to the Supernova MCP endpoint provisioned for your workspace.

## Steps

1. During a frontend task, watch for friction against the design system: missing
   context, conflicting guidance, reformulated requests, or human corrections.
2. Summarize the friction point concisely (what was expected vs. what the system provided).
3. Call the MCP tool `sn_collect_agent_feedback` with the captured feedback.
4. Continue the task using the best available design-system context.

## Operations used

- `sn_collect_agent_feedback` — records design-system feedback back to Supernova.
