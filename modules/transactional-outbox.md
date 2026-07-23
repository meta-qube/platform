# Transactional outbox

**Category:** APIs & reliability  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Persist outbound integration events in the same database transaction as business state, then publish them asynchronously so domain changes and side effects stay consistent.

## Scope

- Outbox table / stream per tenant or bounded context
- Atomic write of business record + outbox message
- Poller or log-tail publisher to event bus / webhooks
- Delivery status, retries, and poison-message handling hooks

## Out of scope

- Event bus topology — Orchestration / Event bus
- Idempotent consumers — separate idempotency concerns
- Circuit breaking of downstream — Circuit breaker

## Inputs

| Input | Description |
|---|---|
| Domain transaction | Business write that must emit an event |
| Outbox payload | Event type, key, body, headers |
| Publish target | Event bus, webhook dispatcher, queue |

## Outputs

| Output | Description |
|---|---|
| Durable outbox record | At-least-once candidate for publish |
| Published event | Delivered to target with delivery metadata |

## Compatibility

Required for payment, CRM, and webhook-heavy modules. Composes with saga/workflow when multi-step consistency is needed.

## Verification

- Crash between commit and publish still delivers exactly the outbox set
- No publish without corresponding business commit
- Tenant isolation of outbox rows
