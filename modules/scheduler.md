# Scheduler

| Field | Value |
|---|---|
| Category | Orchestration |
| Status | Draft |
| Last updated | 2026-07-24 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Trigger work on a clock — cron, one-shot timers, and delayed wakeups — for workflows, reports, dunning, and maintenance jobs.

## Scope

- Cron and calendar expressions
- One-shot and delayed timers
- Timezone-aware schedules per tenant
- Missed-run policy (skip, catch-up, coalesce)

## Out of scope

- Executing the job body — Task queue
- Process graphs — Workflow engine
- Distributed mutual exclusion of the run — Distributed locks

## Inputs

| Input | Description |
|---|---|
| Schedule spec | Cron, delay, or run-at |
| Target | Workflow start, task enqueue, or event |
| Tenant / ownership | Who owns the schedule |

## Outputs

| Output | Description |
|---|---|
| Fire events | Due schedule triggers |
| Schedule records | Next run, last run, status |

## Compatibility

Must respect tenant quiesce / rollback windows. Compliance may restrict schedule regions and data access at fire time.

## Verification

- No duplicate singleton fires under multi-instance runtime
- Timezone and DST behavior documented and tested
- Disable schedule stops future fires
