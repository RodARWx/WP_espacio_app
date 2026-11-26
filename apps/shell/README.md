# ESPACIO Microfrontend Host Shell

- **Owner Role:** Frontend
- **Tech Stack:** React 19 + TypeScript + Vite + @module-federation/vite
- **Workspace Dependencies:** `@espacio/ui`, `@espacio/auth-store`, `@espacio/api-client`
- **Related Jira Tickets:** `GPWP-37, GPWP-49, GPWP-51, GPWP-54`

## Responsibility
Top-level host application owning navigation, global layout, Keycloak OIDC PKCE login, `@espacio/auth-store` singleton initialization, CSS design tokens, Sentry.io `ErrorBoundary` per remote, and dynamic remote MFE federation.
