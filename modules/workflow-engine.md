# Workflow engine

**Category:** Orchestration  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Execute multi-step business processes as durable workflows — definitions, instances, waits, and completions — so compiler-selected flows run reliably in Operations Runtime.

## Scope

- Workflow definitions and versioning
- Instance lifecycle: start, pause, resume, complete, fail
- Steps, gates, human/expert approval waits
- Correlation with tenant, startup package, and module versions

## Out of scope

- Cross-service compensation patterns — Saga
- Cron / time triggers alone — Scheduler
- Raw job execution without process graph — Task queue

## Inputs

| Input | Description |
|---|---|
| Workflow definition | Steps, transitions, timeouts |
| Start payload | Tenant, actor, business keys |
| Signals / events | External completions, webhooks, approvals |

## Outputs

| Output | Description |
|---|---|
| Workflow instance | State, history, current wait |
| Side-effect intents | Tasks, events, connector calls |

## Compatibility

Compiler binds runtime workflows to selected business modules (payments, CRM, support). High-risk transitions may require expert review gates.

## Verification

- Crash recovery resumes without duplicate critical side effects when composed with outbox/idempotency
- Tenant isolation of instances
- Version upgrade does not corrupt in-flight instances without migration rules
