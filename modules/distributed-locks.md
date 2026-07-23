# Distributed locks

**Category:** Orchestration  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Provide mutual exclusion across runtime instances so only one worker performs a critical section (singleton schedule, exclusive migration, leader step).

## Scope

- Acquire / renew / release with TTL
- Lock keys scoped by tenant and resource
- Fencing or token checks against stale holders
- Observability of wait and hold times

## Out of scope

- Business workflow state — Workflow engine
- Queue fairness — Task queue
- Long-lived leader election product features beyond lock primitives

## Inputs

| Input | Description |
|---|---|
| Lock key | Resource identity |
| TTL / lease | Hold duration and renewals |
| Owner token | Instance / worker id |

## Outputs

| Output | Description |
|---|---|
| Lock grant or denial | Whether critical section may run |
| Fence token | Optional token for write protection |

## Compatibility

Required for singleton schedulers and exclusive Globalstorage migrations. Must not deadlock workflows; TTLs mandatory.

## Verification

- Expired lock can be taken by another owner
- Stale owner cannot complete after fence advance
- Cross-tenant key collision impossible by construction
