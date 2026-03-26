# 0001 - AI-First One-Person Company Top-Level Design (v0.1)

Status: Draft
Date: 2026-03-26

## Context

A one-person company needs to maximize execution throughput while keeping strategic control.
Traditional planning is static and human-heavy, creating bottlenecks.

## Decision

Adopt an AI-first operating model with OpenClaw Mission Control as the system of record:

1. Value streams organized as Board Groups: Growth, Sales, Delivery, Ops/Finance.
2. Work decomposed into small, evidence-backed tasks.
3. Dynamic scheduling via rolling 72h commitment window.
4. Human-in-the-loop for high-risk approvals only.
5. Group-centric dashboarding for operational control.

## Architecture

- Organization
  - Board Groups (value streams)
    - Boards (execution units)
      - Tasks (2-6h granularity)
      - Agents (lead + workers)

## Scheduling Model

Use WSJF-Lite style ranking:

`Score = (Business Value × Time Criticality × Risk Reduction) / Effort`

Use P50/P80 estimates and commit on P80.

## Governance

Mandatory approvals for:
- Payments
- Legal/contract changes
- External irreversible actions
- High brand-risk publication

## KPIs

- Commitment reliability (P80)
- Blocked-time duration
- Aging tasks (>72h)
- Replan frequency
- Automation coverage
- Cashflow cycle

## Consequences

### Positive
- Faster feedback loops
- Better owner focus on strategic decisions
- Higher auditability and repeatability

### Trade-offs
- Requires disciplined task decomposition
- Needs tuning for alert thresholds and scoring weights

## Next

- Add v0.2 implementation package
- Add Board/Group templates
- Add heartbeat/digest policy pack

