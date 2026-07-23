# Retry policies

| Field | Value |
|---|---|
| Category | APIs & reliability |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Declare when and how failed operations are retried (backoff, jitter, max attempts, retryable errors) so transient faults recover without flooding dependencies.

## Scope

- Retryable vs non-retryable error classification
- Exponential / linear backoff with jitter
- Max attempts and overall deadline
- Per-connector and per-workflow policy packs

## Out of scope

- Cutting traffic to a sick dependency — Circuit breaker
- Deduplicating successful side effects — idempotency (separate concern)
- Payment-product “retries” as dunning — Business / Payments module

## Inputs

| Input | Description |
|---|---|
| Failed operation | Error class, attempt number |
| Retry policy | Backoff, caps, allow-list of errors |
| Deadline | Caller timeout budget |

## Outputs

| Output | Description |
|---|---|
| Retry schedule | Delay until next attempt or give up |
| Exhausted failure | Terminal error for outbox / workflow |

## Compatibility

Must not retry non-idempotent calls unless the callee guarantees safety. Prefer outbox + idempotency keys for side effects.

## Verification

- Non-retryable errors fail once
- Backoff respected under load
- Interaction with open circuit breaker: no retry storm
