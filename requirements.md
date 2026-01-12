## Functional Requirements
1. Users can browse available events.
2. Users can register for one or more tickets for an event.
3. Event capacity must not be exceeded.
4. Admin users can create and update events.
5. Admin users can view registrations per event.

## Non-Functional Requirements
1. **Scalability**  
   The system must handle sudden traffic spikes during event releases without manual intervention.

2. **Availability**  
   The platform should remain available during zonal infrastructure failures.

3. **Consistency**  
   Registration and ticket inventory updates must be strongly consistent.

4. **Security**  
   Secrets and credentials must not be hardcoded. Access must follow least-privilege principles.

5. **Cost Efficiency**  
   Infrastructure should scale down when idle to minimize ongoing costs.

6. **Maintainability**  
   The system should minimize operational burden such as patching and server maintenance.

## Assumptions
- Payment processing is mocked or out of scope.
- Email notifications may be asynchronous or simulated.
- Initial deployment targets a single region.
