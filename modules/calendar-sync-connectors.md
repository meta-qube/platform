# Calendar sync connectors

**Category:** Channels  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Synchronize platform calendars with external providers (Google Calendar and similar) so events and availability stay aligned.

## Scope

- OAuth-linked provider connectors
- Push and/or poll sync of events
- Mapping between platform and external event ids
- Conflict and deletion propagation rules

## Out of scope

- In-platform calendar product — Calendar
- Generic IdP login — Identity provider connectors
- Email invites as the only channel — Email

## Inputs

| Input | Description |
|---|---|
| Provider account link | OAuth tokens via vault |
| Sync direction | In, out, or bidirectional |
| Calendar selection | Which calendars to sync |

## Outputs

| Output | Description |
|---|---|
| Synced events | Mirrored create/update/delete |
| Sync status | Lag, errors, last success |

## Compatibility

Optional module; requires user consent and compliance fit. Bidirectional sync must declare conflict winners.

## Verification

- Round-trip create/update/delete in sandbox provider
- Token refresh without user re-prompt when allowed
- Disconnect revokes sync and stored refresh material per policy
