# Payments

**Category:** Business  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Charge customers and move money for tenant startups: one-time, subscription, and usage-based billing, plus refunds, payouts, referrals, tax/VAT, invoices, dunning, and multi-currency.

## Scope

- Payment types: one-time, subscriptions, usage-based
- Features: retries, refunds, payouts, referrals
- Tax / VAT, invoices, dunning, multi-currency
- Payment intents, capture, and status machine
- Customer payment methods (via provider adapters)

## Out of scope

- Provider-specific API wiring — Payment provider adapters
- Price catalog and plan packaging — Pricing and packaging
- General ledger / books — Accounting ledger and invoicing
- Platform-wide HTTP retry primitives — Retry policies

## Inputs

| Input | Description |
|---|---|
| Charge / subscription request | Amount or plan, customer, currency |
| Usage records | For metered billing |
| Tax / locale context | Jurisdiction, VAT IDs |
| Provider result | Authorize, capture, fail, dispute |

## Outputs

| Output | Description |
|---|---|
| Payment / subscription records | Status and history |
| Invoice / receipt intents | For accounting and email |
| Dunning / retry schedule | Soft-fail recovery |
| Domain events | Paid, failed, refunded, payout |

## Compatibility

Required for compiler payment flow. Jurisdiction and KYC constraints from compliance policy. High financial risk → expert review on module changes.

## Verification

- Sandbox charge, refund, and failed-card paths
- Idempotent retries do not double-charge
- Multi-currency amounts and tax lines consistent with invoices
