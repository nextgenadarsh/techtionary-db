# Representational State Transfer (REST)

- Software architecture style that applies some constraints to a web service
- Identifies a set of resource-centric rules that describe the roles and interaction between constraints of a distributed hypermedia system, instead of focusig on implementation of components
- REST is media and protocol agnostic

## Constraints of REST

- Uniform interface - `resource-based`
- Stateless
- Cacheable
- Client-server separation
- Layered system
- Code on demand

## Richardson maturity model

- Purpose is to measure the maturity of APIs by prividing some general criteria

### Classification steps/levels

- Level 0: The swamp of Plain Old XML
  - Uses single or generic URI and one VERB like GET
  - Wrap each request message within a massive envelope
  - Eg: SOAP web services

- Level 1: Resources
  - Uses multiple URIs associated with different resources

- Level 2: HTTP Verbs
  - Introduces use of HTTP verbs to enhance information that is transferred on request
  - GET: Retrieve information about resource
  - POST: Creates a new item related to resource
  - PUT: Replaces an item related to resource
  - PATCH: Updated an item related to resource
  - DELETE: Deletes an item related to resource

- Level 3: HATEOAS
  - Implements HATEOAS which provides resource's URI inside its response