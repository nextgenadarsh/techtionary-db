# API Gateway

- Used to establish communication between microservices
- Provides simple interfaces and makes the process of consuming services simpler
- Uses high performance network to provide serious throughput
- Hides the actual APIs from clients and redirects calls to actual APIs from these clients

## Responsibilities

- Accepting API calls and routing them to our backends
- Verifying API keys, JWT tokens, and certificate
- Supporting Auth through Azure AD and the OAuth 2.0 access token
- Enforcing usage quotas and rate limits
- Transforming our API on the fly, without code modifications
- Caching backend responses, wherever they are set up
- Logging all metadata for analytics purpose

## API Gateway benefits for microservices

- Allows to invoke services throught API gateway
- Reduce round trips between the client and application
- Client can access different APIs in one place, as segregated by the gateway