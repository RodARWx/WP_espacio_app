# ESPACIO Core Backend API

- **Owner Role:** Backend
- **Tech Stack:** Java 21 LTS + Spring Boot 3.4 (Hexagonal Architecture + DDD)
- **Workspace Dependencies:** `packages/contracts`
- **Related Jira Tickets:** `GPWP-8, GPWP-13..18, GPWP-39, GPWP-40, GPWP-44..48`

## Responsibility
Core domain services across 4 Bounded Contexts (`identity`, `catalog`, `scheduling`, `billing`) with Pure Java domain core (`INV-01`–`INV-05`), MySQL 8.4 + Transactional Outbox, MongoDB Spatial Sheets, Redis Locks/Tokens, Qdrant/pgvector RAG, Stripe ACL, WebSockets/STOMP, GraphQL read facade, and read-only Runtime MCP server.
