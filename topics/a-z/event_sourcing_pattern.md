# Event-sourcing pattern

- ensures that the service will publish an event whenever the state changes
- we take a business entity as a sequence of state-changing events
- Uses [Event store](./event_store.md)
- we do not need to synchronize the data model and business domain
- improves performance, scalability and responsiveness
- An event represents a set of changes that are made to data