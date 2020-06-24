# Ambassador Pattern

- Similar to [sidecar pattern](./sidecar_pattern.md). Only difference is that every request comes through container, also called `ambassador` or sometime called `proxy container`
- Main application can not be contacted by outside world (UI, clients, and/or remote service) without the ambassador
- Ambassador works as a proxy and routes all network requests to the main application

## When to use

- When multiple services developed in multiple languages/frameworks and need to build common-client connectivity 
- When legacy application is being supported
- When we want to standardize and extend instrumentation

## When to avoid

- If efficient network is priority and latency can affect various operations and could not be handled
- If connectivity features are consumed by single language of client. Better option would be to create client library and share with teams
- When connectivity features can not be generalized and require deeper integration with client application

## Best practices

- Keep the latency overhead in mind
- Consider whether to implement a circuit breaker or retry the ambassador, because it might not be safe to do so unless all operations are idempotent
- Consider how do we package and deploy the proxy