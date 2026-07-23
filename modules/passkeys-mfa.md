# Passkeys and MFA / 2FA

**Category:** Identity, Security & access  
**Status:** Draft  
**Last updated:** 2026-07-23

| Field | Value |
|---|---|
| `name` | Passkeys and MFA / 2FA |
| `version` | 0.1.0-draft |

## Purpose

Strengthen authentication with phishing-resistant passkeys (WebAuthn) and second-factor methods (TOTP, backup codes, and similar).

## Scope

- Passkey registration and assertion
- MFA enrollment, challenge, and recovery
- Step-up authentication for sensitive actions
- Policy hooks for when MFA is required

## Inputs

- Authenticated or partially authenticated principal
- Tenant MFA policy (required, optional, role-based)
- Device / authenticator registration data

## Outputs

- MFA-satisfied authentication state
- Registered authenticator metadata (not secrets in clear text)
- Audit events for enroll, challenge, recovery

## Constraints

- Primary identity still comes from [Authentication](authentication.md) or passkey-as-primary where enabled
- Recovery flows must not bypass [Multilayer security policy](multilayer-security-policy.md)
- Credential material stored via vault or hardware-backed APIs — never in app config

## Compatibility

Composable after password or federated login; may also act as primary factor when passkeys-only is configured.

## Verification

- WebAuthn ceremony tests (register/assert)
- MFA bypass attempts rejected
- Recovery path rate-limited and audited
