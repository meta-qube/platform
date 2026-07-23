# Deprecation and supersede

**Category:** Catalog  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Mark module versions as deprecated and point consumers at superseding versions so the catalog can evolve without silent breaking changes or abandoned pins.

## Scope

- Deprecation metadata: since version, reason, sunset date
- Supersede links: old version → replacement version(s)
- Compiler warnings / blocks on deprecated selections
- Migration hints for in-production startups
- Query filters: hide deprecated by default in new compiles

## Out of scope

- Registry CRUD of module bodies — Module registry
- Running migration jobs — workflow / runtime per tenant
- Automatic forced upgrades without policy

## Inputs

| Input | Description |
|---|---|
| Deprecation request | Module version, reason, sunset |
| Supersede mapping | Replacement module version(s) |
| Policy | Warn vs block for new compiles |

## Outputs

| Output | Description |
|---|---|
| Deprecation record | On the module version |
| Compiler signals | Warning or selection block |
| Migration hints | For operators / founders |

## Compatibility

Published versions stay readable for existing deploys; new compiles prefer superseding versions. Breaking removals require sunset + review.

## Verification

- Deprecated module warns or blocks on new compile per policy
- Supersede target exists and is published
- Existing deployed pin still resolves until migrated
