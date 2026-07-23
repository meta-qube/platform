# Secrets and credentials vault

| Field | Value |
|---|---|
| Category | Identity, Security & access |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |
| Name | Secrets and credentials vault |
| Version | 0.1.0-draft |

## Purpose

Store and issue secrets and third-party credentials outside application code: API keys, OAuth client secrets, webhook signing keys, integration tokens.

## Scope

- Secret create, rotate, revoke, and version
- Scoped access for runtime and compiler-deployed integrations
- Inventory of which module/tenant uses which secret
- Encryption at rest and least-privilege read paths

## Inputs

- Secret payload or generate-on-create request
- Owner (tenant, module, environment)
- Access policy (which workloads may read)

## Outputs

- Secret references (ids) for config binding — not raw values in git
- Short-lived or audited read grants to runtime
- Rotation and access audit trail

## Constraints

- Never commit secrets to module artifacts or startup packages
- Cross-tenant read denied
- Aligns with threat model: unsafe integration credentials ([Architecture](../handbook/architecture.md))

## Compatibility

Required dependency for Authentication clients, Identity provider connectors, Payment provider adapters, and other integration modules.

## Verification

- Raw secret absent from logs and deployment records
- Rotation invalidates previous versions within SLA
- Unauthorized read denied
