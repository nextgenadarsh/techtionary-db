# Circuit Breakers

- When a dependent service is not available or not in a healthy state, a circuit breaker prevents calls from going to that dependent service, and redirects the flow to an alternate path, for a configured period of time

## States

### Closed

- Initial state of circuit which depicts a normal flow
- If operation fails, the failure counter is increased by 1. If it keeps increasing until threshold, state transitions to Open State
- If operation succeed without any exception or failure, failure count is reset

### Half-Open

- The circuit breaker resets the timeout counter and retries to open the circuit, re-initiating the state change to the Open state
- If dependency service calls succeeds, then instead of the Open state, the circuit breaker component changes the state to Closed so that normal flow of the operation can happen, and the circuit is closed again

### Open

- A circuit has already tripped, and a timeout counter has started
- If timeout counter reached and a circuit still keeps on failing, flow of code enters into Half-Open and exception is returned to application