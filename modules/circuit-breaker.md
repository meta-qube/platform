# Circuit breaker

| Field | Value |
|---|---|
| Category | APIs & reliability |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Stop calling a failing dependency for a cool-down period so cascading failures do not take down the runtime; allow probe traffic when recovering.

## Scope

- Closed / open / half-open states per dependency
- Failure and latency thresholds
- Fallback behavior when open (fail fast, cached, or alternate path)
- Metrics hooks for open rate and recovery

## Out of scope

- How individual calls are retried — Retry policies
- Durable event deferral — Transactional outbox

## Inputs

| Input | Description |
|---|---|
| Dependency key | Service, connector, or host |
| Call outcome | Success, failure, timeout |
| Breaker policy | Thresholds, window, cool-down |

## Outputs

| Output | Description |
|---|---|
| Call permit or reject | Whether the call may proceed |
| Breaker state | Closed, open, half-open |

## Compatibility

Apply to payment providers, email, messaging, and CRM connectors. Policy may differ per risk tag.

## Verification

- Opens after configured failure rate
- Rejects quickly while open
- Half-open probe restores or re-opens correctly
