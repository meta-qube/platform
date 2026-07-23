# Meta Qube Platform

> Compile ideas. Run operations.

Meta Qube Platform turns founder input into metadata that configures reliable, customizable meta-modules and runs the resulting business operations in the cloud.

Expert-reviewed modules let startups reuse proven tools instead of rebuilding from scratch, with lower security risk, fewer errors, and faster assembly.

## Subsystems

- [Startup Compiler](#startup-compiler) — guided classification and assembly of startup packages from meta-modules.
- [Operations Runtime](#operations-runtime) — cloud execution of workflows, agents, integrations, and business processes.
- [Module Catalog](#module-catalog) — registry of declarative meta-modules with contracts, compatibility, and review status.

### Startup Compiler

Guided classification and assembly. The compiler collects founder answers, selects compatible meta-modules, and produces a launch-ready startup configuration:

- positioning
- product structure
- MVP scope
- business model
- pricing
- landing page
- CRM pipeline
- sales flow
- payment flow
- support flow
- technical architecture
- API integrations
- UI applications
- legal drafts
- pitch structure
- risk report
- validation plan
- metrics dashboard
- runtime workflows
- integration map

### Operations Runtime

Cloud execution of business processes from day one. We use [Metarhia Stack](https://github.com/metarhia/Docs):

```text
API layer          → endpoints, units, schema validation
Domain layer       → app state, workflows, business rules
Data access layer  → PostgreSQL, Redis, Globalstorage
Protocol layer     → metacom, HTTP, WebSocket, webhooks
Infrastructure     → logging, scheduling, multithreading, sandbox
```

### Module Catalog

A catalog of reusable **meta-modules** with declarative DSL-style configuration.

Identity & access:
- Auth: OAuth 2.0, OpenID, SSO
- Passkeys, MFA / 2FA
- Multilayer security policy
- Session management, session console
- RBAC + catalog rights

Infrastructure:
- Load balancer
- CDN integration
- Rate limiting
- Service discovery

Runtime primitives:
- Workflow engine
- Saga
- Scheduler
- Task queue
- Distributed locks
- Event bus
- Webhook dispatcher
- Protocol connectors: REST, GraphQL, gRPC
- Schemas

Data:
- Distributed database: Globalstorage
  - Search and indexing
  - Full-text search
  - Continuous backup/restore
  - Continuous migration
  - Continuous calculations

Observability:
- Logging: access logs, security logs, audit logs
- Telemetry and monitoring
- Error tracking

Communication & content:
- Chat engine
- Chatbots
- Landing page
- Feeds (news channel)
- Email delivery, receiving, campaigns
- External messaging integration: Telegram, etc.
- Calendar

Business:
- Payments
  - Types: one-time, subscriptions, usage-based
  - Features: retries, refunds, payouts, referrals
- Product and customer
  - Customer onboarding
  - Subscription management
  - Feedback
  - Feature requests and bug reports
- Report generation
- Parental control

AI & agents:
- AI integration
- Security assistant

Compiler:
- Startup wizard
- Pitch wizard

Catalog:
- Module registry
- Test runner

Module lifecycle:

```text
Draft → Reviewed draft → Generated → Reviewed module → Verified → Published → Deployed → Updated / Rolled Back
```

## Handbook

Extended records (no duplicate of this README):

- [Handbook index](handbook/index.md)
- [Subsystems](handbook/subsystems.md) — interfaces and responsibilities
- [Architecture](handbook/architecture.md) — containers, bounded contexts, data flows, NFRs
- [Glossary](handbook/glossary.md)
- [Meta-modules](handbook/meta-modules.md) — record schema, compatibility, verification
- [ADRs](adr/README.md)

## Related repositories

- [Meta Qube manifest](https://github.com/meta-qube/manifest) — product definition: compiler, runtime, modules
- [Metarhia Docs](https://github.com/metarhia/Docs) — application server, API, domain, and data layers
- [meta-qube.com](https://meta-qube.com) — public product site
