# Saga (long-running distributed transactions)

**Category:** Orchestration  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Coordinate long-running distributed transactions across modules and integrations with explicit steps and compensations when a later step fails.

## Scope

- Saga definition: forward steps + compensation steps
- Orchestration or choreography binding to workflow / events
- Compensation triggers and idempotent undo actions
- Visibility of saga state for ops and audit

## Out of scope

- Generic process engine features — Workflow engine
- Single-DB local transactions
- Circuit breaking of a dependency — Circuit breaker

## Inputs

| Input | Description |
|---|---|
| Saga definition | Steps, compensations, timeouts |
| Business transaction id | Correlation key |
| Step outcomes | Success / failure from participants |

## Outputs

| Output | Description |
|---|---|
| Saga instance state | Running, compensating, completed, failed |
| Compensation commands | Undo intents to participants |

## Compatibility

Preferred for payment + fulfillment + CRM multi-module flows. Compensation must be declared; silent partial commit is not allowed for financial risk tags.

## Verification

- Failure mid-saga runs compensations in order
- Compensation retries are idempotent
- Audit log records forward and compensate actions
