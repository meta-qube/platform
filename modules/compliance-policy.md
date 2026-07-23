# Compliance policy: GDPR, data residency

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Encode compliance constraints — especially GDPR and data residency — so compiler selection and runtime placement respect jurisdiction and processing rules.

## Scope

- GDPR-oriented processing constraints (lawful basis hooks, DSR-ready data maps)
- Data residency and region binding for tenant data
- Retention and deletion policy hooks
- Flags that force expert review on legal/privacy risk

## Out of scope

- Legal document drafts (ToS, privacy text) — catalog Legal & trust modules
- Technical encryption/key custody — Secrets and Credentials Vault, multilayer policy

## Inputs

| Input | Description |
|---|---|
| Tenant jurisdiction | Primary market and residency requirements |
| Data classes | Personal, payment, health, etc. |
| Processing activities | Compile, operate, integrate, export |

## Outputs

| Output | Description |
|---|---|
| Compliance constraints | Region, retention, transfer limits |
| Risk tags / review triggers | For catalog and startup changes |

## Compatibility

Must constrain Globalstorage placement, integrations, and module selection. Incompatible modules (wrong residency) fail compile-time checks.

## Verification

- Residency enforced on store and backup targets
- Export/transfer paths respect policy
- High legal risk escalates to expert review
