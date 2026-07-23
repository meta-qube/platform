# Payment provider adapters

**Category:** Business  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Integrate external payment processors (Stripe and similar) behind a stable adapter contract so the Payments module stays provider-agnostic.

## Scope

- Adapter interface for authorize, capture, refund, payout, webhooks
- Provider-specific request/response mapping
- Webhook signature verification
- Sandbox vs live mode binding per tenant

## Out of scope

- Business payment state machine — Payments
- Plan and price definitions — Pricing and packaging
- Bookkeeping — Accounting ledger and invoicing

## Inputs

| Input | Description |
|---|---|
| Adapter config | Provider, mode, credential refs |
| Payment operation | Normalized intent from Payments |
| Provider webhook | Raw signed payload |

## Outputs

| Output | Description |
|---|---|
| Normalized provider result | Status, ids, errors |
| Verified webhook events | For Payments / outbox consumers |

## Compatibility

Compiler selects adapters allowed for tenant jurisdiction and currency. Multiple adapters may coexist (e.g. cards vs payouts).

## Verification

- Webhook signature fail rejects payload
- Sandbox end-to-end with Payments
- Credential rotation does not require code change
