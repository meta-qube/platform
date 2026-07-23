# Secrets and credentials vault

| Field | Value |
|---|---|
| Category | Identity, Security & access |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Store and issue secrets and integration credentials outside application code, with scoped access for platform services and tenant runtimes.

## Scope

- Secret create, rotate, revoke
- Scoped retrieval for runtime workloads
- Client secrets, API keys, webhook signing secrets, DB credentials
- Inventory and ownership metadata

## Out of scope

- End-user passwords and passkeys — Authentication, Passkeys and MFA
- Policy text for retention of personal data — Compliance policy

## Inputs

| Input | Description |
|---|---|
| Secret payload | Value + type + owner |
| Access scope | Service, tenant, environment |
| Rotation policy | TTL and rotate-on-use rules |

## Outputs

| Output | Description |
|---|---|
| Secret reference | Opaque id for config bindings |
| Short-lived material | Issued to authorized runtime only |

## Compatibility

Required by payment, email, messaging, and IdP connectors. Secrets must never appear in module artifacts or git.

## Verification

- No secret values in logs or compiler outputs
- Cross-tenant retrieve denied
- Rotation invalidates prior versions on schedule
