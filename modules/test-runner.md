# Test runner

**Category:** Catalog  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Execute automated verification suites for meta-modules and startup packages — contract tests, compatibility checks, and sandbox runs — before review and publish.

## Scope

- Run module `verification` suites declared on the record
- Contract and compatibility test harness
- Sandbox execution of module artifacts where safe
- Report pass/fail to registry and CI
- Regression runs on dependency changes

## Out of scope

- Storing module metadata — Module registry
- Human expert judgment — expert review gate
- Production tenant load tests (separate ops concern)

## Inputs

| Input | Description |
|---|---|
| Module version / package | Under test |
| Test suite refs | From module `verification` field |
| Environment | Sandbox credentials and fixtures |

## Outputs

| Output | Description |
|---|---|
| Test report | Cases, failures, artifacts |
| Gate signal | Allow / block lifecycle transition |

## Compatibility

Required before Verified / Published for modules with automated checks. High-risk tags still escalate to experts even if tests pass.

## Verification

- Known-good module suite passes
- Known-broken contract fails the gate
- Sandbox cannot reach other tenants’ data
