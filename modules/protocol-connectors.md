# Protocol connectors: REST, GraphQL, gRPC

| Field | Value |
|---|---|
| Category | APIs & reliability |
| Status | Draft |
| Last updated | 2026-07-23 |
| Authors group | — |
| Leader | — |
| Advisers | — |

## Purpose

Expose and consume APIs over REST, GraphQL, and gRPC with shared schema validation, routing, and tenancy so modules and integrations speak consistent protocols.

## Scope

- REST endpoints and HTTP semantics
- GraphQL schemas and query/mutation execution bounds
- gRPC services and protobuf contracts where used
- Protocol selection per module / integration surface

## Out of scope

- Domain schema authorship — Schemas (API and domain contracts)
- Inbound webhook fan-in — Webhook dispatcher
- Reliability wrappers — Circuit breaker, Retry policies

## Inputs

| Input | Description |
|---|---|
| API contract | OpenAPI / GraphQL SDL / protobuf |
| Binding config | Paths, methods, auth requirements |
| Tenant context | Isolation and rate limits |

## Outputs

| Output | Description |
|---|---|
| Callable surface | Routed endpoints / services |
| Client stubs / connectors | For outbound calls to external APIs |

## Compatibility

Must align with Metarhia protocol layer (HTTP, WebSocket, metacom). GraphQL and gRPC optional per startup package.

## Verification

- Contract validation on publish
- Authz enforced per protocol path
- Timeout and payload size limits applied
