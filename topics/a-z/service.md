# Service

- Piece of code, a program, or software
- Refers to a functionality exposed for consumption by other systems
- Can be consumed by client directly, client may be website or app
- Can be with or without database support at the backend
- Exposed over HTTP(S) transport protocol as general practice
- Services can be spread across different physical machines
- Services may or may not be deployed on same or single server
- Services access single database

## Characteristics of good service

- Standard data formats like JSON and XML
- Standard communication protocol like SOAP and REST over HTTP(S)
- Loose coupling

## Effective communication between services

- Use [API Gateway](./api_gateway.md)
- [Event-driven pattern](./event_driven_communication.md)
- [Event-Sourcing pattern](./event_sourcing_pattern.md)

