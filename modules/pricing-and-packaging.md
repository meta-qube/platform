# Pricing and packaging

**Category:** Business  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Define products, plans, packages, and prices the compiler and runtime use for offers, checkout, and subscriptions.

## Scope

- Products, plans, add-ons, and packages
- Price points: one-time, recurring, usage tiers
- Trials, discounts, coupons
- Packaging constraints (what can be sold together)

## Out of scope

- Charging and collection — Payments
- Ledger posting — Accounting ledger and invoicing
- CRM deal stages — Customer operations / CRM

## Inputs

| Input | Description |
|---|---|
| Catalog draft | Products, plans, prices, currency |
| Entitlements | Features unlocked by package |
| Experiment flags | A/B price or package variants |

## Outputs

| Output | Description |
|---|---|
| Sellable catalog | Versioned prices and packages |
| Checkout selection | Resolved line items for Payments |
| Entitlement map | For product access control |

## Compatibility

Must align with startup business model and legal constraints (e.g. jurisdiction-specific offers). Versioned prices; no silent in-flight plan mutation.

## Verification

- Resolve package → line items deterministically
- Deprecated prices not sold without migration path
- Entitlements match paid package
