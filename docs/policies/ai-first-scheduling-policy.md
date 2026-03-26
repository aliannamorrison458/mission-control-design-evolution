# AI-First Scheduling Policy

## 1) Scheduling Cadence

- Re-rank queue every 2-4 hours.
- Commit window is rolling 72 hours.
- Anything outside 72 hours is tentative.

## 2) Priority Function (WSJF-Lite)

Score each task:

`Score = (BusinessValue * TimeCriticality * RiskReduction) / Effort`

Where:
- BusinessValue: 1-5
- TimeCriticality: 1-5
- RiskReduction: 1-5
- Effort: estimated hours (P50)

Tie-breakers:
1. Dependency-unblocking tasks first
2. Tasks nearing SLA/deadline
3. Tasks with required approvals queued

## 3) Estimation Standard

Each task must include:
- P50 (most likely)
- P80 (safe commitment)

Commitment baseline uses P80.

## 4) Task Size Rules

- Target size: 2-6 hours.
- > 8h must be split before execution.
- > 24h may not enter `in_progress` directly.

## 5) WIP Limits

Per board defaults:
- In Progress WIP: max 3
- Review WIP: max 5

Exceeding limits triggers automatic de-prioritization of new starts.

## 6) Escalation Rules

Auto-escalate to owner when:
- Blocked > 8h (P2)
- Blocked > 24h (P1)
- Approval pending > 24h
- SLA breach risk in next 12h

## 7) Done Contract

A task can move to done only when all are present:
- Deliverable artifact
- Verification evidence
- Next action or closure note
