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

Identity, Security & access:
- [Authentication: OAuth 2.0, OpenID, SSO](modules/authentication.md)
- [Passkeys and MFA / 2FA](modules/passkeys-and-mfa.md)
- [Multilayer security policy](modules/multilayer-security-policy.md)
- [Session management, session console](modules/session-management.md)
- [RBAC and catalog rights](modules/rbac-and-catalog-rights.md)
- [Secrets and credentials vault](modules/secrets-and-credentials-vault.md)
- [Compliance policy: GDPR, data residency](modules/compliance-policy.md)
- [Identity provider connectors](modules/identity-provider-connectors.md)

Infrastructure:
- Load balancer
- CDN
- Rate limiting
- Service discovery

Orchestration:
- [Workflow engine](modules/workflow-engine.md)
- [Saga (long-running distributed transactions)](modules/saga.md)
- [Scheduler](modules/scheduler.md)
- [Task queue](modules/task-queue.md)
- [Distributed locks](modules/distributed-locks.md)
- [Event bus](modules/event-bus.md)

APIs & reliability:
- [Protocol connectors: REST, GraphQL, gRPC](modules/protocol-connectors.md)
- Webhook dispatcher
- Schemas (API and domain contracts)
- [Transactional outbox](modules/transactional-outbox.md)
- [Circuit breaker](modules/circuit-breaker.md)
- [Retry policies](modules/retry-policies.md)

Data & storage:
- Distributed database: Globalstorage
  - Search and indexing
  - Full-text search
  - Continuous backup and restore
  - Continuous migration
  - Continuous calculations
- [File and media storage](modules/file-and-media-storage.md)
- [Media processing](modules/media-processing.md)

Observability:
- [Logging: access, security, and audit logs](modules/logging.md)
- [Telemetry and monitoring](modules/telemetry-and-monitoring.md)
- [Error tracking](modules/error-tracking.md)

Channels:
- Chat engine
- Chatbots
- Landing page
- Feeds (news channel)
- [Email: delivery, receiving, campaigns](modules/email.md)
- [Messaging integrations: Telegram, etc.](modules/messaging-integrations.md)
- [Notification hub: email, SMS, push, in-app](modules/notification-hub.md)
- [Calendar](modules/calendar.md)
- [Calendar sync connectors](modules/calendar-sync-connectors.md)

Surfaces:
- Landing page
- Feeds (news channel)
- Brand and UI shells
- Admin and founder portal

Business:
- [Payments](modules/payments.md)
  - Types: one-time, subscriptions, usage-based
  - Features: retries, refunds, payouts, referrals
  - Tax / VAT, invoices, dunning, multi-currency
- [Payment provider adapters](modules/payment-provider-adapters.md)
- [Pricing and packaging](modules/pricing-and-packaging.md)
- [Accounting ledger and invoicing](modules/accounting-ledger-and-invoicing.md)

Customer operations:
- Product and customer lifecycle
  - Customer onboarding
  - Subscription management
  - Feedback
  - Feature requests and bug reports
- CRM pipeline and sales flow
- Support ticketing and SLA
- Parental control

Legal & trust:
- Legal drafts: ToS, privacy policy, contracts

Analytics:
- Metrics and analytics dashboard
- Report generation

AI & agents:
- AI / LLM gateway
- RAG knowledge base
- Tool-calling agents
- Security assistant

Compiler:
- [Startup wizard](modules/startup-wizard.md)
- [Pitch wizard](modules/pitch-wizard.md)
- Risk and verification reports
- Validation and experiment plans
- Compatibility rules and risk tags

Catalog:
- [Module registry](modules/module-registry.md)
- [Test runner](modules/test-runner.md)
- [Deprecation and supersede](modules/deprecation-and-supersede.md)

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
