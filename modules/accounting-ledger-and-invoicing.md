# Accounting ledger and invoicing

**Category:** Business  
**Status:** Draft  
**Last updated:** 2026-07-24  

## Purpose

Record money movement in a tenant ledger and produce accounting-grade invoices/credit notes so payments are reflected in books, not only in the processor.

## Scope

- Double-entry or equivalent ledger entries
- Invoice and credit note documents
- Mapping from payment events to journal lines
- Export hooks for accounting SaaS
- Tax lines as posted (source of truth may be Payments tax calc)

## Out of scope

- Card capture and provider APIs — Payments, payment provider adapters
- Plan catalog — Pricing and packaging
- Full statutory reporting per country (may need expert modules)

## Inputs

| Input | Description |
|---|---|
| Payment / refund / payout events | From Payments |
| Invoice request | Customer, lines, tax, currency |
| Chart of accounts config | Tenant account map |

## Outputs

| Output | Description |
|---|---|
| Ledger entries | Immutable postings |
| Invoices / credit notes | Documents and PDFs/links |
| Export batches | For external accounting tools |

## Compatibility

Complements Payments: Payments charges; this module books. Invoice numbering and retention follow jurisdiction rules.

## Verification

- Payment success posts balancing ledger entries
- Refund posts compensating entries / credit note
- Invoice totals match payment tax and currency
