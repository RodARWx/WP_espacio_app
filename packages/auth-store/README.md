# @espacio/auth-store — Shared Auth & RBAC Singleton

- **Owner Role:** Frontend & Architecture
- **Tech Stack:** TypeScript + Zustand + oidc-client-ts
- **Workspace Dependencies:** None (Leaf package)
- **Related Jira Tickets:** `GPWP-24, GPWP-37, GPWP-51`

## Responsibility
Module Federation singleton store managing Keycloak OIDC PKCE tokens (memory-only on web), silent refresh, `realm_access.roles` (`ROLE_TENANT`, `ROLE_LANDLORD`, `ROLE_ADMIN`), and platform auth adapters.
