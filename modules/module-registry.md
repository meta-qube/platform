# Module registry

**Category:** Catalog  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Store and serve meta-module definitions, versions, contracts, compatibility rules, and review status for the Module Catalog — the source of truth Compiler and Runtime resolve against.

## Scope

- Module records: id, version, owner, category, contracts
- Lifecycle state storage (draft through deployed / rolled back)
- Search, list, and get-by-id for compiler and runtime
- Dependency and compatibility metadata
- Artifacts and configuration bindings per version

## Out of scope

- Automated test execution — Test runner
- Marking versions obsolete — Deprecation and supersede
- Expert review UX — Expert Review Console (architecture container)

## Inputs

| Input | Description |
|---|---|
| Module record | Schema fields per [meta-modules](../handbook/meta-modules.md) |
| Lifecycle transition | Draft → … → published / deployed |
| Query | Search by category, status, compatibility |

## Outputs

| Output | Description |
|---|---|
| Canonical module versions | Resolved for compile / deploy |
| Compatibility graph data | For selection checks |
| Review status | For gates and UI |

## Compatibility

Single registry for platform catalog; tenants consume published versions, they do not fork silently. Aligns with [ADR-0002](../adr/0002-meta-module-as-composition-unit.md).

## Verification

- Immutable published version bytes / artifacts
- Unauthorized publish denied
- Compiler resolves only allowed statuses for deploy
