# MFE Remote: Scheduling, Escrow & Invoices

- **Owner Role:** Frontend
- **Tech Stack:** React 19 + TypeScript + Vite Module Federation Remote
- **Workspace Dependencies:** `@espacio/ui`, `@espacio/auth-store`, `@espacio/api-client`, `@espacio/domain-utils`
- **Related Jira Tickets:** `GPWP-37, GPWP-49, GPWP-51`

## Responsibility
Federated remote exposing `TimeSlot` calendar with live WebSocket/Redis 10-minute lock countdown, Stripe `AttendanceDeposit` checkout, dynamic `VisitCheckInToken` QR pass (`QrPassModal`), PDF `Invoice` viewer, and 100% `Refund` tracker.
