## Database Schema

### events
- event_id (PK)
- title
- description
- start_time
- location
- capacity_total
- capacity_remaining
- price_cents
- created_at

### users
- user_id (PK)
- email (unique)
- name
- created_at

### registrations
- registration_id (PK)
- event_id (FK)
- user_id (FK)
- ticket_count
- status
- created_at

## Integrity Considerations
- Registrations decrement capacity using transactions.
- Constraints prevent overselling tickets.
- Foreign keys ensure relational integrity.
