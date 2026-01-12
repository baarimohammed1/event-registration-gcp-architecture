# Event Registration + Ticketing on Google Cloud
### Architecture, Tradeoffs, and Database Design

## Overview
This project documents the design of a production-style Google Cloud architecture for an event registration and ticketing platform. The system is designed to handle traffic spikes during ticket releases, maintain transactional integrity for registrations, and minimize operational overhead.

The focus of this project is **cloud architecture decision-making**, not application feature completeness. It demonstrates how requirements translate into infrastructure choices, tradeoffs, and deployment strategy on Google Cloud.

## Architecture
![Architecture Diagram](docs/architecture-diagram.png)

**High-level flow:**
Users → HTTPS Load Balancer → Cloud Run (Event API) → Cloud SQL (MySQL)

Supporting services include Cloud Storage for event assets, Secret Manager for secure configuration, and Cloud Logging & Monitoring for observability.

## Key Design Goals
- Handle sudden traffic spikes during event launches
- Maintain strong consistency for ticket inventory
- Minimize infrastructure management overhead
- Use managed cloud services where possible
- Keep costs low during idle periods

## Documentation
- Requirements: `docs/requirements.md`
- Architecture details: `docs/architecture.md`
- Design decisions & tradeoffs: `docs/decision-record.md`
- Database schema: `docs/database-schema.md`
- Implementation plan: `docs/implementation-plan.md`
- Evidence checklist: `docs/screenshots-checklist.md`

## Future Improvements
- Authentication and authorization (e.g., Firebase Auth)
- Asynchronous workflows using Pub/Sub for confirmations
- Rate limiting and WAF rules via Cloud Armor
- CI/CD with Cloud Build and Artifact Registry
- Multi-region disaster recovery strategy
