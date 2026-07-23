# Logging: access, security, and audit logs

**Category:** Observability  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Emit and retain structured logs for access, security events, and audit trails so operators and reviewers can reconstruct who did what, when.

## Scope

- Access logs (API / session entry points)
- Security logs (authn failures, policy denies, anomaly signals)
- Audit logs (append-oriented sensitive actions: review, publish, payment, secrets)
- Correlation ids across request and workflow

## Out of scope

- Metrics and dashboards — Telemetry and monitoring
- Exception aggregation — Error tracking
- Product analytics for founders — Analytics modules

## Inputs

| Input | Description |
|---|---|
| Event | Action, actor, tenant, resource, outcome |
| Classification | Access / security / audit |
| Retention class | Per compliance policy |

## Outputs

| Output | Description |
|---|---|
| Structured log records | Queryable by tenant and time |
| Audit trail | Tamper-evident where required |

## Compatibility

Secrets and PII must be redacted. Audit logs required for catalog lifecycle and expert review decisions.

## Verification

- Sensitive actions produce audit entries
- Cross-tenant log access denied
- Redaction covers tokens and secret values
