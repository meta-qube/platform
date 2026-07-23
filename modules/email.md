# Email: delivery, receiving, campaigns

| Field | Value |
|---|---|
| Category | Channels |
| Status | Draft |
| Last updated | 2026-07-24 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Send, receive, and campaign over email for tenant startups — transactional mail, inbound handling, and bulk/campaign sends under policy and deliverability controls.

## Scope

- Outbound transactional delivery
- Inbound receiving and routing (support, parse, webhooks)
- Campaign / bulk send with lists and templates
- Bounce, complaint, and suppression handling

## Out of scope

- Cross-channel orchestration — Notification hub
- Instant messengers — Messaging integrations
- Marketing site content — Surfaces / Landing page

## Inputs

| Input | Description |
|---|---|
| Message or campaign | Template, recipients, payload |
| Domain / sender config | From, DNS, provider binding |
| Inbound address rules | Route to workflow, ticket, or store |

## Outputs

| Output | Description |
|---|---|
| Delivery events | Sent, bounced, complained, opened (if tracked) |
| Inbound messages | Normalized for support / automation |

## Compatibility

Campaign sends must respect unsubscribe and jurisdiction rules. Compiler binds provider adapters per tenant.

## Verification

- Transactional send succeeds in sandbox provider
- Bounce updates suppression list
- Cross-tenant recipient lists isolated
