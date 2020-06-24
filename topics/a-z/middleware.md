# Middleware

- Handle, process, and modify incoming HTTP requests
- Handle, process, and change outgoing HTTP responses
- Interrupt the middleware pipeline by returning an early response
- Focuses on single purpose, to be compliant with single responsibility principle
- Uses the concept of chaining. Takes a request and passes to next middleware
- Order is important when creating middleware pipeline