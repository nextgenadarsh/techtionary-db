# API Gateway Pattern

## Pros

- The client can get complete data by making minimal requests to the services
- We can handle multiple-format responses, such as JSON, XML, and so on
- Authentication and logging can also be managed with this pattern
- We can reduce round trips between client and application
- Helps us access different APIs in one place, as exposed by the gateway

## Cons

- Chances of performance degradation since most of manipulation and transposing of responses happens at the API Gateway itself
- Chances of having single points of failure
- Needs extra attention and coding to manage routes
- Adds more complexity to the system

## Best practices

- We should implement logging and monitoring at a central place of the API Gateway
- For aggregate services, it is good to have a combined logic in API Gateway to return client-specific responses. However when the aggregate service has complex business logic or you have a specific requirement then you can proceed without API Gateway