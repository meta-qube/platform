# Event bus

| Field | Value |
|---|---|
| Category | Orchestration |
| Status | Draft |
| Last updated | 2026-07-24 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Publish and subscribe to domain and integration events inside the platform so modules react loosely without direct coupling.

## Scope

- Topics / streams and subscriptions
- Publish API for domain and integration events
- At-least-once delivery to subscribers
- Filtering by type, tenant, and keys

## Out of scope

- Durable enqueue of work units — Task queue
- Atomic “DB write then publish” — Transactional outbox
- External HTTP callbacks — Webhook dispatcher

## Inputs

| Input | Description |
|---|---|
| Event envelope | Type, key, payload, tenant, causation ids |
| Subscription | Handler binding and filter |
| Retention / replay policy | Where supported |

## Outputs

| Output | Description |
|---|---|
| Delivered events | To matching subscribers |
| Delivery failures | For retry / dead-letter hooks |

## Compatibility

Preferred backbone for choreography-style sagas and cross-module notifications. Tenant isolation enforced on publish and subscribe.

## Verification

- Subscriber receives events for its tenant only
- Outbox-backed publish survives producer crash
- Poison handler does not block the bus indefinitely
