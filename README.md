## Samson Rwakabuguli

Full-stack software engineer in Kampala, Uganda. Ten years building systems that institutions depend on —
national government platforms, health and education information systems, and fintech.

**PHP/Laravel** and **Vue.js/TypeScript** on the web · **Go** for backend services · **PostgreSQL** ·
**Docker/Kubernetes**

---

### Why this profile looks quieter than my CV

Most of what I have built over the last six years lives in **private client and employer repositories** —
government ministries, a health-tech company, and financial platforms. Several of those organisations I have
since rolled off, so I no longer hold access to the repositories, and GitHub stops attributing those
contributions once access ends. The commits are real; the graph simply cannot show them.

Rather than ask you to take that on trust, **I am happy to walk through architecture and code directly on a
call** — design decisions, data models, trade-offs, and the parts I would do differently now.

### What I have actually shipped

**Uganda's National Education Management Information System (EMIS 2.0)** · Go, PHP/Laravel, Vue 3, PostgreSQL,
Kafka, RabbitMQ, Redis
I own the cross-cutting platform layer: authentication and authorisation (Keycloak SSO with hierarchical RBAC
and ABAC), person identity including a Go rewrite with record deduplication, integrations with the national ID
authority and examination bodies, notifications, file management, and a tamper-evident audit trail. Also the
Schools, Ministry and Local Government portals on a shared Vue 3 component library.

**Multi-tenant facility management platform** · 18 Go microservices, Vue 3 + TypeScript, PostgreSQL, Kubernetes
Designed and built the platform for a national government agency, as the technical prototype submitted for a
competitive public tender — 18 Go services plus a biometric matching service, on a 19-module workspace, around
30,000 lines of Go with 149 unit tests. I wrote 89% of the commits, over roughly four and a half weeks.

Single sign-on through OIDC Authorization Code with PKCE (ZITADEL) against an LDAP identity source, with roles
derived from directory attributes. Every service validates tokens by introspection against an authentication
gateway rather than decoding them independently. Tenant isolation is enforced in middleware from JWT claims
rather than in application code, so it cannot be bypassed by an application-level bug — designed for 270
facilities across 16 roles and three authorisation scope tiers. Database-per-service across 17 PostgreSQL
databases, asynchronous audit interception on every mutating request without adding response latency, and
Redis-backed rate limiting. Deployed on Kubernetes (RKE2) with a single wildcard certificate issued by
cert-manager over a DNS-01 challenge, tenant identity injected at the ingress edge, and a five-layer startup
dependency graph coordinated through an idempotent init job. Biometric enrolment and verification against an
ABIS matcher — including a local WebSocket capture agent I wrote so the browser SPA could drive USB fingerprint
hardware it otherwise cannot reach.

**Investment club platform** · Go (Chi, sqlc), PostgreSQL, Redis, Vue 3 + TypeScript
Double-entry ledger accounting, contributions tracking, loan management with amortisation, portfolio risk
monitoring, and provider-agnostic payments. Role-based access through PostgreSQL row-level security,
maker-checker approvals, multi-factor authentication, and an event-driven outbox with idempotency — built to
Uganda's Data Protection Act (2019).

**Donor-funded national digital collaboration platform** · delivered solo, inception through production.

**Earlier** · Led the EMIS 1.0 team at SMS One (Laravel + Vue) integrating national ID and examinations data;
led the technical team on the Ministry of Foreign Affairs Integrated System at GovNet; built a Laravel financial
system for Uganda Red Cross that cut volunteer incentive processing time by more than half via SMS and Mobile
Money.

### What is public here

- **`codebase-rag`** — a local RAG server that indexes codebases and serves code context to AI assistants over
  the Model Context Protocol. Python.
- **`laravel-math-captcha`** — an accessible, dependency-free arithmetic CAPTCHA for Laravel. On Packagist.

### How I work

I use AI coding tools (Claude, Cursor) as a routine part of my workflow, and I am open about it: they change
throughput, not accountability. I specify the work, review every line, and own the result. On one recent
government platform that meant 319 commits in three weeks, solo, from inception deliverables through to
production deployment.

---

📍 Kampala, Uganda · **Available for contract and consulting work**, and open to remote roles
🔗 [samson.rwakabuguli.com](https://samson.rwakabuguli.com) · ✉️ srwakabuguli@gmail.com · 📞 +256 773 449429 | +256 705 449429
