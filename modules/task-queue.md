# Task queue

| Field | Value |
|---|---|
| Category | Orchestration |
| Status | Draft |
| Last updated | 2026-07-24 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Enqueue and run background units of work with concurrency limits, retries, and worker pools so request paths stay fast and heavy work stays isolated.

## Scope

- Enqueue, claim, ack / nack of tasks
- Queues / priorities / concurrency per tenant or workload
- Dead-letter handling hooks
- Worker execution sandbox boundaries where required

## Out of scope

- When tasks become due by clock — Scheduler
- Multi-step process state — Workflow engine
- Publish-subscribe fan-out — Event bus

## Inputs

| Input | Description |
|---|---|
| Task payload | Type, args, tenant, idempotency key |
| Queue policy | Priority, concurrency, timeout |
| Worker capability | Which workers may claim the task |

## Outputs

| Output | Description |
|---|---|
| Task result | Success payload or failure |
| Queue metrics | Depth, age, failure rate |

## Compatibility

Used by media processing, outbox publishers, and workflow step runners. Sandbox modules must not escape worker isolation.

## Verification

- At-least-once delivery with idempotent handlers
- Tenant fairness under load
- Poison messages move to dead-letter per policy
