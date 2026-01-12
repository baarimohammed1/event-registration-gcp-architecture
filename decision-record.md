## Decision Record

### Decision 1: Compute Platform

**Options Considered**
- Cloud Run
- Compute Engine (VMs)
- Google Kubernetes Engine (GKE)

**Decision**
Cloud Run was selected.

**Rationale**
- Automatically scales during traffic spikes.
- Eliminates server and OS management.
- Pay-per-request pricing reduces idle costs.

**Tradeoffs**
- Cold start latency is possible.
- Requires stateless application design.

---

### Decision 2: Database Technology

**Options Considered**
- Cloud SQL (MySQL)
- Firestore
- BigQuery

**Decision**
Cloud SQL (MySQL) was selected.

**Rationale**
- Strong transactional consistency.
- Natural relational modeling for events and registrations.
- Familiar SQL semantics.

**Tradeoffs**
- Vertical scaling considerations.
- Higher operational cost than serverless NoSQL at very low traffic.

---

### Decision 3: Storage for Static Assets

**Decision**
Cloud Storage was selected.

**Rationale**
- Highly durable and cost-effective object storage.
- Simple access controls and lifecycle management.

---

### Decision 4: Availability Strategy

**Decision**
Single-region deployment with multi-zone resilience.

**Rationale**
- Balances cost and complexity for an early-stage platform.
- Enables future expansion to multi-region if needed.

**Tradeoffs**
- Regional outage could cause downtime.
