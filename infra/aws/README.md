# AWS Cloud Infrastructure & High Availability

- **Owner Role:** DevOps / SRE
- **Tech Stack:** AWS ALB / Nginx Load Balancer, ECS/EC2 Auto Scaling, RDS/S3, Secrets Manager
- **Workspace Dependencies:** `infra/docker`
- **Related Jira Tickets:** `GPWP-28, GPWP-38, GPWP-58, GPWP-62`

## Responsibility
QA & PROD High-Availability deployment blueprints with multi-AZ redundancy, automated health checks (`/actuator/health/readiness`), and S3 storage for 2D sketches & PDF invoices.
