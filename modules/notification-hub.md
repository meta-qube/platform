# Notification hub: email, SMS, push, in-app

| Field | Value |
|---|---|
| Category | Channels |
| Status | Draft |
| Last updated | 2026-07-24 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Route user and system notifications across channels (email, SMS, push, in-app) with preferences, templates, and fallback so modules emit one intent, not many provider calls.

## Scope

- Notification intent API (who, why, template, data)
- Channel selection and fallback order
- User / tenant preference and quiet hours
- Template registry per channel
- Delivery status aggregation

## Out of scope

- Provider-specific email campaigns — Email
- Messenger bots as product surface — Messaging integrations
- Chat threads — Chat engine

## Inputs

| Input | Description |
|---|---|
| Notification intent | Recipient, category, priority, data |
| Preference profile | Allowed channels, locale |
| Template ids | Per-channel content refs |

## Outputs

| Output | Description |
|---|---|
| Channel dispatches | Calls into email, SMS, push, in-app |
| Delivery summary | Per-channel outcomes |

## Compatibility

Modules should prefer the hub over direct provider calls for user messaging. Financial and security alerts may force channel overrides via multilayer policy.

## Verification

- Preference opt-out honored
- Fallback fires when primary channel fails
- No cross-tenant template or recipient leakage
