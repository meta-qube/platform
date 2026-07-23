# Authentication: OAuth 2.0, OpenID, SSO

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Establish who a user or service is before any tenant or platform action. Supports OAuth 2.0, OpenID Connect, and SSO so startups and the platform share one identity baseline.

## Scope

- OAuth 2.0 authorization flows for apps and APIs
- OpenID Connect identity claims and userinfo
- SSO across platform surfaces and tenant apps where configured
- Token issuance, validation, and refresh

## Out of scope

- Passkeys and MFA challenges — Passkeys and MFA
- Session storage and operator console — Session management
- External IdP adapter catalog — Identity provider connectors

## Inputs

| Input | Description |
|---|---|
| Client / app registration | Redirect URIs, scopes, client type |
| IdP configuration | Issuer, keys, SSO bindings |
| User credentials or federated assertion | Password, social, or enterprise IdP |

## Outputs

| Output | Description |
|---|---|
| Access / ID tokens | Bound to subject, tenant, and scopes |
| Authenticated principal | Stable subject id and claims for RBAC |

## Compatibility

Required for most tenant runtimes. Must compose with RBAC before authorizing catalog or business actions.

## Verification

- Token signature and audience checks
- SSO round-trip for configured IdPs
- No cross-tenant subject reuse without explicit link
