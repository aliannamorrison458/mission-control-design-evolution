# 0002 - Implementation Package (v0.2)

Status: Accepted
Date: 2026-03-26
Supersedes: 0001 (top-level design baseline)

## Objective

Translate the v0.1 architecture into an executable rollout package for Mission Control.

## Scope

1. Board Group and Board bootstrap templates
2. AI-first scheduling policy pack
3. Heartbeat and daily digest operating policy
4. 14-day execution plan with acceptance checks

## Deliverables

- `docs/templates/mission-control-bootstrap.yaml`
- `docs/policies/ai-first-scheduling-policy.md`
- `docs/policies/heartbeat-digest-policy.md`
- `docs/playbooks/14-day-rollout.md`

## Operating Defaults

- Planning window: rolling 72h
- Task granularity: 2–6 hours
- Estimation: P50 / P80 (commit on P80)
- Prioritization: WSJF-Lite
- External-risk actions: approval required

## Acceptance Criteria

- Four board groups created and actively used
- At least one lead and one worker agent per board
- Daily digest runs without manual intervention
- Dashboard supports group-oriented operating view
- Weekly review produces measurable KPI deltas

## Risks / Mitigations

- Over-automation noise -> alert thresholds + escalation levels
- Large tasks stuck in progress -> forced decomposition policy
- Approval bottleneck -> fixed approval windows + pre-aggregation

## Next Iteration (v0.3)

- KPI contract and target-setting guide
- Capacity model per value stream
- Failure recovery runbook
