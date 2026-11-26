# ESPACIO API Gateway

- **Owner Role:** Backend & DevOps / SRE
- **Tech Stack:** Spring Cloud Gateway (Java 21)
- **Workspace Dependencies:** `packages/contracts`
- **Related Jira Tickets:** `GPWP-38, GPWP-42, GPWP-43`

## Responsibility
Single entry point behind AWS ALB / Nginx. Enforces strict CORS allow-lists, Redis-backed rate limiting, Keycloak JWT relay, correlation ID injection (`X-Correlation-ID`), and OWASP security headers across QA & PROD.
