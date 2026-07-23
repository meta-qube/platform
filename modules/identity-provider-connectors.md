# Identity provider connectors

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23  

## Purpose

Integrate external identity providers (social, enterprise, platform IdPs) so authentication can federate without custom code per startup.

## Scope

- Connector configs for common IdPs (OIDC/SAML where supported)
- Mapping external claims to platform principals
- Enable / disable IdPs per tenant
- Credential references for IdP client configuration

## Out of scope

- Core OAuth / OIDC protocol engine — Authentication
- MFA factors after federation — Passkeys and MFA

## Inputs

| Input | Description |
|---|---|
| IdP connector type | e.g. Google, Microsoft, Okta, custom OIDC |
| Client config | Issuer, client id, secret ref, scopes |
| Claim mapping | External → platform subject attributes |

## Outputs

| Output | Description |
|---|---|
| Federated login path | Ready for authentication module |
| Linked subject | Platform user bound to external id |

## Compatibility

Each connector must declare supported protocols and claim guarantees. Compiler only selects connectors allowed for the tenant jurisdiction.

## Verification

- Login and logout (where applicable) against sandbox IdP
- Claim mapping rejects missing required fields
- Secret refs resolve; raw secrets not stored in module config
