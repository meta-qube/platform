# RBAC and catalog rights

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23

| Field | Value |
|---|---|
| `name` | RBAC and catalog rights |
| `version` | 0.1.0-draft |

## Purpose

Authorize actions with role-based access control for platform and tenant apps, including rights specific to the Module Catalog (draft, review, publish, deploy).

## Scope

- Roles, permissions, and bindings (user/group → role → tenant/resource)
- Catalog rights: read, draft, review, verify, publish, deprecate
- Runtime rights: operate workflows, manage customers, refunds, etc. (as bound by modules)
- Permission checks at API and domain boundaries

## Inputs

- Authenticated principal and tenant
- Role and permission definitions
- Resource identifiers (module id, startup id, customer id, …)

## Outputs

- Authorization decisions (allow/deny)
- Effective permission set for UI and APIs
- Audit events for denied privileged actions

## Constraints

- Authentication is a prerequisite; this module does not authenticate
- Catalog lifecycle transitions must also respect expert review gates ([ADR-0004](../adr/0004-expert-review-gate.md))
- Least privilege by default for new tenants

## Compatibility

Composable with all business modules that declare required permissions in their contracts.

## Verification

- Matrix tests: role × action × resource
- Catalog publish denied without review rights
- Privilege escalation attempts denied and audited
