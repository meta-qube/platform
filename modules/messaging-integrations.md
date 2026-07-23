# Messaging integrations: Telegram, etc.

| Field | Value |
|---|---|
| Category | Channels |
| Status | Draft |
| Last updated | 2026-07-24 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Connect external messaging platforms (Telegram and similar) so startups can notify users, run bots, and receive messages through the runtime.

## Scope

- Provider connectors (Telegram first; extensible set)
- Outbound messages and inbound updates
- Bot / channel binding per tenant
- Webhook or long-poll receive adapters

## Out of scope

- In-app chat product — Chat engine
- Unified multi-channel fan-out — Notification hub
- Email — Email

## Inputs

| Input | Description |
|---|---|
| Connector config | Bot token ref, webhook URL, allowed chats |
| Outbound payload | Text, media refs, buttons |
| Inbound update | Platform-native event normalized |

## Outputs

| Output | Description |
|---|---|
| Delivered messages | Provider message ids |
| Normalized inbound events | For workflows / chatbots |

## Compatibility

Each connector declares capabilities (bot, channel, groups). Compliance may restrict which messengers a jurisdiction may use.

## Verification

- Sandbox bot round-trip send/receive
- Token never logged; secret ref only
- Tenant bot bindings cannot receive another tenant’s updates
