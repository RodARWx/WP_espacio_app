# ESPACIO Mobile Wrapper (iOS & Android)

- **Owner Role:** Frontend
- **Tech Stack:** Capacitor 6 + @capacitor-mlkit/barcode-scanning
- **Workspace Dependencies:** `apps/shell`, `@espacio/auth-store`
- **Related Jira Tickets:** `GPWP-21, GPWP-22, GPWP-24`

## Responsibility
Native mobile shell wrapping `apps/shell` build with system-browser Keycloak PKCE (`espacio://auth/callback`) and native camera MLKit QR scanning for `ListingQrCode` and `VisitCheckInToken`.
