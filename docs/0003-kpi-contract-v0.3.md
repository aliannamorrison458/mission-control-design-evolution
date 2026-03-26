# 0003 - KPI Contract & Weekly Operating Review (v0.3)

Status: Accepted
Date: 2026-03-26
Depends on: 0001, 0002

## Purpose

Define hard KPI contracts and a weekly review loop so the AI-first system continuously self-calibrates.

## KPI Contract (per Board Group)

Each group must maintain:
1. North-star KPI (1)
2. Health KPIs (2-3)
3. Guardrail KPI (1)

All KPIs must include:
- Definition
- Formula
- Data source
- Target
- Alert threshold
- Owner (agent role)

## Suggested KPI Set

### Growth
- North-star: Qualified leads/week
- Health: CTR, conversion to SQL
- Guardrail: CAC trend

### Sales
- North-star: Closed revenue/week
- Health: Stage progression, win rate
- Guardrail: Discount leakage

### Delivery
- North-star: On-time delivery rate
- Health: First-pass acceptance, rework hours
- Guardrail: Critical defect count

### Ops/Finance
- North-star: Runway (months)
- Health: DSO, overdue ratio
- Guardrail: Incident recovery time

## Weekly Review Protocol (60 min)

1. KPI delta scan (15m)
   - What improved/declined vs prior week?
2. Bottleneck analysis (15m)
   - Where work aged, blocked, or churned?
3. Policy tuning (15m)
   - Adjust WSJF weights, thresholds, WIP limits.
4. Commitment reset (15m)
   - Set 1-3 outcomes for next week.

## Decision Rules

- If guardrail violated -> freeze new initiatives in that group until recovered.
- If North-star misses 2 consecutive weeks -> re-scope board objectives.
- If replan frequency > threshold -> reduce WIP and shrink task size.

## Artifacts

- Weekly review note (template)
- Updated thresholds and policy deltas
- Top 3 process debt items
