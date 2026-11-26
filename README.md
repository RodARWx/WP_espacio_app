# ESPACIO — Multi-Platform Spatial Evaluation & Verified Visit Scheduling Platform

**Course:** Web Programming 2026–2027 — Universidad Central del Ecuador (Group Project `GPWP`)  
**Confluence Space:** [GPWP — Group Project Documentation](https://sistemas-uce.atlassian.net/wiki/spaces/GPWP)  
**Jira Board:** [GPWP Backlog & Sprints](https://sistemas-uce.atlassian.net/jira/software/projects/GPWP/boards/35)

---

## Architecture Overview

ESPACIO is a multi-platform rental pre-lease platform (Web, Mobile via Capacitor, Desktop via Electron, plus Astro Jamstack public street-QR landing) built on a **Dual Architecture**:
- **Backend:** Java 21 + Spring Boot 3 **Hexagonal Architecture (Ports & Adapters)** + DDD across 4 Bounded Contexts (`identity`, `catalog`, `scheduling`, `billing`) behind a **Spring Cloud API Gateway**.
- **Frontend:** React 19 + TypeScript **Microfrontends (Shell + Vite Module Federation)** using an **MVVM / ViewModel** pattern (`Zustand` + `TanStack Query`), shared Design System tokens, and a Rust **WebAssembly (`.wasm`)** spatial/QR engine.
- **Polyglot Persistence (4 Databases):** MySQL 8.4 (ACID + Transactional Outbox), MongoDB (Spatial Sheets & Audit Logs), Redis (Atomic 10-min `TimeSlot` Locks, Ephemeral QR Tokens & Search Cache), and Vector DB (`Qdrant` / `pgvector` for Embeddings & RAG).
- **Edge, Cloud & Observability (QA & PROD):** Cloudflare (DNS/WAF/SSL Strict) → Load Balancer (AWS ALB / Nginx) → API Gateway → High-Availability Multi-Replica Services on AWS + PaaS Headless CMS (Strapi / Contentful) + Keycloak OIDC/PKCE + Stripe Payments/Refunds + n8n + Sentry.io + Site24x7.

---

## Mono Repo Structure (`GPWP-36 / ARCH-07`)

```text
WP_espacio_app/
├── apps/                        # Deployable applications & platform shells
│   ├── api-gateway/             # Spring Cloud Gateway (routing, CORS, rate limit, security headers)
│   ├── backend/                 # Java 21 + Spring Boot 3 Hexagonal API (REST, Webhooks, WS, GraphQL, MCP, RAG)
│   ├── shell/                   # React 19 + Vite Microfrontend Host Shell (Keycloak PKCE, routing, Sentry)
│   ├── mf-catalog/              # Remote MFE: Dimensional Search, Space-Fit Evaluator, Comparator, AI RAG Drawer
│   ├── mf-booking/              # Remote MFE: TimeSlot Locks, Stripe Escrow Checkout, Dynamic QR Pass, Invoices
│   ├── mf-host/                 # Remote MFE: Landlord Properties (INV-01), TimeSlots, On-Site QR Check-In
│   ├── mf-admin/                # Remote MFE: Admin RBAC Matrix, Escrow Ledger Audit, Observability Health
│   ├── public-qr/               # Astro 5 Jamstack site (street-QR /p/:code + Headless CMS)
│   ├── web-ssr/                 # Optional Next.js Hybrid Rendering app (SSG, ISR, SSR, CSR)
│   ├── mobile/                  # Capacitor 6 mobile wrapper (iOS / Android + MLKit native QR)
│   └── desktop/                 # Electron 33 desktop wrapper (Windows / macOS / Linux + safeStorage)
├── packages/                    # Shared internal libraries & Spec-Driven contracts
│   ├── ui/                      # @espacio/ui — Figma Design System tokens & shared React components
│   ├── auth-store/              # @espacio/auth-store — Singleton Keycloak OIDC PKCE & RBAC store
│   ├── api-client/              # @espacio/api-client — Auto-generated OpenAPI 3.0 TS client + TanStack Query
│   ├── domain-utils/            # @espacio/domain-utils — Pure TS Space-Fit math & QR payload parsers
│   ├── wasm-spatial/            # @espacio/wasm-spatial — Rust + wasm-pack 2D sketch & QR crypto verifier
│   └── contracts/               # SDD Source of Truth: OpenAPI 3.0, GraphQL SDL, Domain Events, MCP schemas
├── infra/                       # Infrastructure as Code, Containers & Observability (QA & PROD)
│   ├── docker/                  # Dockerfiles & docker-compose stacks (local, QA, PROD)
│   ├── aws/                     # AWS ALB/Nginx Load Balancer, HA ECS/EC2, S3, Secrets
│   ├── cloudflare/              # DNS, SSL/TLS Strict, WAF & Rate Limiting policies
│   ├── keycloak/                # espacio-realm export, PKCE clients & RBAC role definitions
│   ├── n8n/                     # Automated notification & operational workflow JSON exports
│   └── observability/           # Sentry.io configs, Site24x7 monitors & k6 load test scripts
├── docs/                        # Versioned architecture diagrams (SVG/PNG) & ADRs (ADR-001..ADR-017)
└── .github/                     # GitHub Actions CI/CD workflows & Dual-Gate PR template
```

---

## GitFlow & Contribution Standards (`GPWP-56 / DEVOPS-07`)

This repository follows strict **GitFlow** aligned with our QA and PROD verification gates:

```text
main (PROD — protected, tagged releases only)
 └── qa (QA / Staging — protected, full CI/CD + E2E + Load Test gate)
      └── develop (Integration — protected, active sprint base)
           ├── feature/GPWP-XX-short-description
           ├── fix/GPWP-XX-short-description
           └── chore/GPWP-XX-short-description
```

### Mandatory Rules
1. **Never commit directly** to `main`, `qa`, or `develop`.
2. Branch off `develop` for all features/docs/chores (`feature/GPWP-<id>-<slug>`) and open a Pull Request back into **`develop`**.
3. Follow **Conventional Commits** in English (e.g., `feat(arch): define monorepo workspace structure (GPWP-36)`).
4. Every PR must pass the **Dual Approval Gate**: **Software Architect** + **QA / Tech Lead**, plus automated CI checks.
5. Promote `develop` → `qa` for QA verification (all 26+1 requirements), and `qa` → `main` only after QA sign-off.

---

## Quick Start (Workspace Tooling)

```bash
# Prerequisites: Node.js 22+, pnpm 9+, Java 21 LTS, Maven 3.9+, Docker Desktop
pnpm install
pnpm run lint
pnpm run test
pnpm run build
```
