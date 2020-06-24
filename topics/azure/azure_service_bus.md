# Azure Service Bus

- is `Event Manager` to manage all events
- cloud service shared by multiple users based on namespaces

## Services provided by Azure Service Bus

### Brokered communication

- This service is also known as `hired service`.
- ensures that our messages are delivered, event though both the sender and receiver are not online
- is a `messaging platform`, with components such as queues, topics, subscriptions, and so on
- works similar to postal service in real world

### Non-brokered communication

- sender sends information and depends on receiver to receive communication and pass message back to sender
- similar to making a phone call in real world

## Components

### Queues

- act like brokers, in that they allow `unidirectional communication`

### Topics

- `similar to queues` but single topic can have `multiple subscriptions`

### Relays

- `does not store` any messages like queues and topics
- provides `bidirectional` communication and pass messages to application

### Notification Hubs

- distributes messages from the server application to client devices across the platform

