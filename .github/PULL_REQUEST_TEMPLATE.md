## Summary
<!-- Describe what this PR changes and why. -->

**Related Jira Ticket(s):** `GPWP-XX`  
**Target Branch:** `develop` (or `qa` / `main` for release promotion only)

## Scope of Changes
- [ ] `apps/backend` or `apps/api-gateway` (Java 21 / Spring Boot 3)
- [ ] `apps/shell` or `apps/mf-*` (React Microfrontends)
- [ ] `apps/public-qr`, `apps/web-ssr`, `apps/mobile`, or `apps/desktop`
- [ ] `packages/*` (Shared UI, Auth, API Client, Domain Utils, Wasm, Contracts)
- [ ] `infra/*` (Docker, AWS, Cloudflare, Keycloak, n8n, Observability)
- [ ] `docs/*` (Architecture Diagrams, ADRs, Confluence Sync)

## Architecture, SDD, ODD & OWASP Checklist
- [ ] Commits follow Conventional Commits in English (`feat(...)`, `fix(...)`, `docs(...)`, `chore(...)`).
- [ ] **SDD:** OpenAPI / GraphQL / Domain Event contracts in `packages/contracts` updated before implementation.
- [ ] **Hexagonal / MVVM:** Domain layer has zero framework imports; frontend business logic lives in ViewModel hooks/stores.
- [ ] **OWASP Top 10:** Input validation, RBAC (`@PreAuthorize`), parameterized queries, and zero hardcoded secrets verified.
- [ ] **ODD:** Structured JSON logs, `X-Correlation-ID` propagation, and Sentry instrumentation preserved.
- [ ] Unit / Functional / E2E tests added or updated and passing locally.

## Dual Approval Gate (`GPWP-56`)
- [ ] **Software Architect Approval**
- [ ] **QA / Tech Lead Approval**
