## Architecture Overview

The system is deployed entirely within a single Google Cloud region and uses managed services to reduce operational complexity.

### Core Components

#### HTTPS Load Balancer
- Serves as the public entry point for all client requests.
- Terminates TLS and forwards traffic to Cloud Run.

#### Cloud Run (Event API)
- Hosts the stateless backend API.
- Automatically scales based on request volume.
- Handles event browsing, registration logic, and admin operations.

#### Cloud SQL (MySQL)
- Stores transactional data including events, users, and registrations.
- Provides strong consistency guarantees.
- Supports backups and optional high availability configurations.

#### Cloud Storage
- Stores static assets such as event images and exported data.

#### Secret Manager
- Stores database credentials and sensitive configuration.
- Accessed securely by the Cloud Run service at runtime.

#### Cloud Logging & Monitoring
- Collects logs, metrics, and request traces.
- Enables visibility into system health and performance.

### Networking Model
- Client traffic enters via HTTPS Load Balancer.
- Internal service-to-service communication remains within Google Cloud.
- Database access is restricted to the Cloud Run service.
