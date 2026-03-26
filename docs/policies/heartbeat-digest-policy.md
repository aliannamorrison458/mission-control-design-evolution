# Heartbeat & Daily Digest Policy

## Heartbeat (every 30-60 min)

Purpose: detect drift early and keep queues healthy.

Checks per run:
1. New blockers
2. Aging tasks (>72h no progress)
3. Review/approval congestion
4. Gateway/agent health anomalies
5. KPI anomaly flags (throughput drop, error spikes)

Actions:
- Re-rank queue using scheduling policy
- Raise escalation event if thresholds crossed
- Emit compact status note for affected board groups

## Daily Digest (1x per day)

For each board group, publish:
- Completed today
- Risks now
- Top 3 next actions tomorrow

Formatting rule:
- Keep digest under 12 lines per group.
- Include links to evidence/tasks.

## Quiet Hours

Default quiet window: 23:00-08:00 local time.
Only P1 alerts may break quiet hours.

## Owner Attention Budget

Design for <= 30 minutes/day of owner review:
- 2 fixed approval windows
- 1 digest review window
- everything else async unless escalated
