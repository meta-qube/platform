# Calendar

**Category:** Channels  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Provide tenant calendars, events, and availability for scheduling product flows (demos, support slots, founder rituals) inside the platform.

## Scope

- Calendars and events CRUD
- Attendees, reminders, time zones
- Availability / free-busy queries
- Hooks to notify on create/update/cancel

## Out of scope

- Sync with Google/Microsoft/etc. — Calendar sync connectors
- Generic notification routing — Notification hub
- Full CRM meeting intelligence — Customer operations / CRM

## Inputs

| Input | Description |
|---|---|
| Event | Time range, attendees, calendar id |
| Availability query | Users/resources and window |
| Reminder policy | Offsets and channels |

## Outputs

| Output | Description |
|---|---|
| Calendar records | Events and calendars |
| Reminder intents | To notification hub / scheduler |
| Free-busy results | For booking UIs |

## Compatibility

Works standalone for in-platform calendars; sync connectors optional per startup package.

## Verification

- Time zone display consistent with stored UTC
- Attendee visibility respects ACLs
- Cancel removes or marks pending reminders
