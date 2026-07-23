# RBAC and catalog rights

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Authorize actions with role-based access control, including rights specific to Module Catalog lifecycle (draft, review, publish, deploy).

## Scope

- Roles, permissions, and role bindings per tenant / platform
- Resource-scoped checks (startup, module, review, deploy)
- Catalog rights: author, reviewer, publisher, operator
- Separation of duties for expert review vs publish

## Out of scope

- Authentication of the subject — Authentication
- Layered policy orchestration — Multilayer security policy

## Inputs

| Input | Description |
|---|---|
| Principal | Subject, groups, tenant |
| Action + resource | e.g. `catalog.publish` on module id |
| Role assignments | Platform and tenant bindings |

## Outputs

| Output | Description |
|---|---|
| Authorization decision | Allow / deny |
| Effective permissions | For UI and API gating |

## Compatibility

Catalog publish and expert review require distinct rights. Must align with [ADR-0004 expert review gate](../adr/0004-expert-review-gate.md).

## Verification

- Least privilege defaults
- Reviewer cannot self-publish high-risk modules without policy exception
- Tenant A roles never apply to tenant B resources
