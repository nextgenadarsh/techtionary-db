# Aggregator Pattern

- It aggregates or combines the information and returns the final response
- Mix the responses of two or more services, apply any business logic and then return combined response
- Can be implemented with the help of composite microservices
- We can also use API gateway to aggregate the data and return it to the consumer if business logic need not apply

## When to use

- Multiple backend services are required to process or perform a client request
- The client has unstable network or significant latency in the network

## When to avoid

- We need to make a single call to same service so that multiple calls can be reduced. In this case, batch operation can be implemented.
- Low network latency.

## Best practices

- Data segregation is one of the best practices to fllow
- Manage services as a client-faced service and internal service