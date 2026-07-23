# Session management, session console

| Field | Value |
|---|---|
| Category | Identity, Security & access |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Create, track, revoke, and inspect authenticated sessions for users and operators, including a session console for visibility and forced logout.

## Scope

- Session create / renew / expire / revoke
- Binding sessions to device, IP, and auth strength
- Concurrent session limits and idle timeout
- Session console for self-service and admin revoke

## Out of scope

- Token minting protocols — Authentication
- Authorization decisions — RBAC and catalog rights

## Inputs

| Input | Description |
|---|---|
| Authenticated principal | Subject and claims after authn / MFA |
| Session policy | TTL, idle, concurrency |
| Console actions | List, inspect, revoke |

## Outputs

| Output | Description |
|---|---|
| Session record | Id, subject, tenant, metadata, expiry |
| Revocation events | For audit and forced logout |

## Compatibility

Required wherever interactive login exists. Catalog and founder portals share session primitives with tenant isolation.

## Verification

- Revoke invalidates subsequent requests
- Cross-tenant session listing denied
- Console actions audited
