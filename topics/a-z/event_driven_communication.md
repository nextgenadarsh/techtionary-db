# Event Driven Communication

- Implement a service in a way that it publishes an event whenever a service updates its data, and another service subscribes to this event
- Whenever dependent service receives an event, it updates its data

## Event Manager

- a program running on a service or a mediator helping manage all the events of subscribers and publishers
- help form a queue and wait for events
- Eg: Azure Service Bus Queue

