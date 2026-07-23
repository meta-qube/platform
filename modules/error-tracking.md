# Error tracking

**Category:** Observability  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Capture, group, and triage runtime exceptions and failed jobs so engineers and agents can fix defects without digging only through raw logs.

## Scope

- Exception capture from API, workers, and sandboxed modules
- Fingerprinting / grouping of similar errors
- Release and module-version tagging
- Notify hooks for new or regressing issues

## Out of scope

- Full audit trail — Logging
- SLI dashboards and uptime — Telemetry and monitoring

## Inputs

| Input | Description |
|---|---|
| Error event | Stack, message, context, tenant |
| Release metadata | Module versions, deploy id |
| Ownership | Routing to team or agent |

## Outputs

| Output | Description |
|---|---|
| Issue groups | Aggregated error fingerprints |
| Triage signals | New, regression, resolved |

## Compatibility

Must scrub secrets and tokens from stacks. Sandbox module errors tagged with module id and review status.

## Verification

- Known test exception appears as a group
- PII/secret scrubbing on payloads
- Cross-tenant issue visibility denied
