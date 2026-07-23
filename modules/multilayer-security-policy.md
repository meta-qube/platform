# Multilayer security policy

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Define and enforce defense-in-depth rules across identity, API, data, and runtime layers so no single control is the only barrier.

## Scope

- Layered policy model (edge, authn/authz, domain, data)
- Defaults and overrides per tenant / module risk
- Binding policies to actions (login, deploy, payment, review)
- Evaluation order and deny-by-default rules

## Out of scope

- Concrete RBAC roles — RBAC and catalog rights
- Legal/compliance obligations text — Compliance policy
- Secret storage — Secrets and credentials vault

## Inputs

| Input | Description |
|---|---|
| Action context | Who, tenant, resource, operation |
| Policy pack | Layered rules and risk thresholds |
| Signals | Auth strength, network, device, audit flags |

## Outputs

| Output | Description |
|---|---|
| Allow / deny / step-up | Decision for the action |
| Required controls | e.g. MFA, expert review, sandbox |

## Compatibility

Must not contradict compliance residency or catalog review gates. Runtime and compiler both consume the same decision model where possible.

## Verification

- Deny-by-default for unknown actions
- Step-up enforced on high-risk tags
- No silent policy bypass in sandbox or admin paths
