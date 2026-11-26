# ESPACIO Architecture Decision Records (ADRs 001–017)

Canonical documentation is maintained in Confluence:  
[04. Database Design & Architecture Decision Records (ADRs)](https://sistemas-uce.atlassian.net/wiki/spaces/GPWP/pages/9076737)

| ID | Decision | Status | Jira |
| :--- | :--- | :--- | :--- |
| ADR-001 | Hexagonal Architecture (Ports & Adapters) + DDD | Accepted | GPWP-11 |
| ADR-002 | Polyglot Persistence (MySQL 8.4 + MongoDB + Redis) | Accepted | GPWP-11 |
| ADR-003 | Externalized IAM with Keycloak (OAuth2 / OIDC + PKCE) | Accepted | GPWP-11 |
| ADR-004 | Unified React + TypeScript Client with Capacitor & Electron | Accepted | GPWP-11 |
| ADR-005 | Static Jamstack Landing Page with Astro | Accepted | GPWP-11 |
| ADR-006 | Stripe PaymentIntents, Signed Webhooks & Refunds API | Accepted | GPWP-11 |
| ADR-007 | Deterministic Invariants (`INV-01`–`INV-05`) & Role-Scoped Governance | Accepted | GPWP-11 |
| ADR-008 | Next.js SSR Evaluation (Superseded/Extended by ADR-016) | Extended | GPWP-11 |
| ADR-009 | Headless CMS Integration (Strapi / Contentful) with Astro Landing | Accepted | GPWP-11 |
| ADR-010 | Multi-Protocol Communication (REST, Webhooks, WebSockets, GraphQL & Runtime MCP) | Accepted | GPWP-11 |
| ADR-011 | Vector DB (`Qdrant` / `pgvector`) & AWS Cloud Deployment | Accepted | GPWP-11 |
| ADR-012 | Unified Mono Repo (`pnpm` + Turborepo + Maven Workspaces) | Accepted | GPWP-41 |
| ADR-013 | Microfrontends Architecture (Shell Host + Vite Module Federation Remotes) | Accepted | GPWP-41 |
| ADR-014 | Client-Side WebAssembly (`.wasm`) Module via Rust + `wasm-pack` | Accepted | GPWP-41 |
| ADR-015 | 4th Polyglot Database (Qdrant / `pgvector` HNSW Schema & RAG Guardrails) | Accepted | GPWP-41 |
| ADR-016 | Next.js Optional Hybrid Rendering Strategy (SSG, ISR, SSR, CSR) | Accepted (Optional) | GPWP-41 |
| ADR-017 | Edge Security, API Gateway, Load Balancing, High Availability & ODD Telemetry (QA & PROD) | Accepted | GPWP-41 |
