# Passkeys and MFA / 2FA

| Field | Value |
|---|---|
| Category | Identity, Security & access |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Strengthen authentication with phishing-resistant passkeys and multi-factor / two-factor challenges after primary identity proof.

## Scope

- WebAuthn / passkey registration and assertion
- TOTP and other approved second factors
- Step-up MFA for sensitive actions
- Recovery paths that do not weaken primary controls

## Out of scope

- Primary OAuth / OIDC / SSO — Authentication
- Session lifetime after factors succeed — Session management

## Inputs

| Input | Description |
|---|---|
| Authenticated or pending subject | From authentication flow |
| Factor enrollment | Passkey, authenticator, or recovery material |
| Policy | Which actions require MFA / passkey |

## Outputs

| Output | Description |
|---|---|
| Factor-verified assertion | Proof that required factors passed |
| Enrollment state | Registered factors per subject |

## Compatibility

Composes with authentication; may be required by compliance or multilayer policy for admin, payments, or catalog publish.

## Verification

- Passkey ceremony against registered credentials
- MFA challenge replay and brute-force limits
- Recovery cannot bypass policy without audit
